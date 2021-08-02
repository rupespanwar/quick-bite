# Security
<img width="856" alt="image" src="https://user-images.githubusercontent.com/75510135/127757844-111e6b11-f604-450b-acb1-b6502c9d9f49.png">

# Kubernetes Security Primitives
<img width="693" alt="image" src="https://user-images.githubusercontent.com/75510135/127758037-8ffd92c1-ac6f-4102-b9ed-c4a13a7c5f3d.png">

<img width="839" alt="image" src="https://user-images.githubusercontent.com/75510135/127758047-7dc7141a-f267-43f3-8266-1d9070d6ded6.png">

<img width="827" alt="image" src="https://user-images.githubusercontent.com/75510135/127758054-a83bd37a-3da9-4098-a763-8494f00ba3b3.png">

<img width="777" alt="image" src="https://user-images.githubusercontent.com/75510135/127758060-a4e4877a-5439-4766-8c85-4171ffb6419e.png">

<img width="756" alt="image" src="https://user-images.githubusercontent.com/75510135/127758065-42c5a1a2-79d6-485b-ab41-9f184189dbde.png">

# Authentication
<img width="896" alt="image" src="https://user-images.githubusercontent.com/75510135/127758313-14287fb1-1121-4455-8dd4-15e9146ef760.png">

<img width="904" alt="image" src="https://user-images.githubusercontent.com/75510135/127758321-0e4c342b-fc1a-4624-ae7f-55d837f4bfb4.png">

<img width="904" alt="image" src="https://user-images.githubusercontent.com/75510135/127758324-1222cbbc-2df1-4331-97a2-33f0ae62007e.png">

<img width="878" alt="image" src="https://user-images.githubusercontent.com/75510135/127758334-4ddcab55-d96a-4c79-b144-e8e522aa0215.png">

<img width="838" alt="image" src="https://user-images.githubusercontent.com/75510135/127758339-e96a4100-65b9-4289-a754-44357ca2b808.png">

<img width="896" alt="image" src="https://user-images.githubusercontent.com/75510135/127758348-3df8179e-c07a-450b-a9b3-ee4dc7765a37.png">

<img width="890" alt="image" src="https://user-images.githubusercontent.com/75510135/127758351-8857339d-64b9-45e9-8f1a-032decdd7762.png">

<img width="856" alt="image" src="https://user-images.githubusercontent.com/75510135/127758355-3935b4a8-cf63-4212-8abb-46b2c83c160a.png">

<img width="882" alt="image" src="https://user-images.githubusercontent.com/75510135/127758358-df1c2ee9-b60b-481c-b9d2-69ef7ce111cd.png">

<img width="888" alt="image" src="https://user-images.githubusercontent.com/75510135/127758364-74e411b2-5e88-4e55-a8fc-4f503f3b4249.png">

# Article on Setting up Basic Authentication
Setup basic authentication on Kubernetes (Deprecated in 1.19)

    Note: This is not recommended in a production environment. This is only for learning purposes. Also note that this approach is deprecated in Kubernetes version 1.19 and is no longer available in later releases

Follow the below instructions to configure basic authentication in a kubeadm setup.

Create a file with user details locally at /tmp/users/user-details.csv

    # User File Contents
    password123,user1,u0001
    password123,user2,u0002
    password123,user3,u0003
    password123,user4,u0004
    password123,user5,u0005


Edit the kube-apiserver static pod configured by kubeadm to pass in the user details. The file is located at /etc/kubernetes/manifests/kube-apiserver.yaml


    apiVersion: v1
    kind: Pod
    metadata:
      name: kube-apiserver
      namespace: kube-system
    spec:
      containers:
      - command:
        - kube-apiserver
          <content-hidden>
        image: k8s.gcr.io/kube-apiserver-amd64:v1.11.3
        name: kube-apiserver
        volumeMounts:
        - mountPath: /tmp/users
          name: usr-details
          readOnly: true
      volumes:
      - hostPath:
          path: /tmp/users
          type: DirectoryOrCreate
        name: usr-details


Modify the kube-apiserver startup options to include the basic-auth file


    apiVersion: v1
    kind: Pod
    metadata:
      creationTimestamp: null
      name: kube-apiserver
      namespace: kube-system
    spec:
      containers:
      - command:
        - kube-apiserver
        - --authorization-mode=Node,RBAC
          <content-hidden>
        - --basic-auth-file=/tmp/users/user-details.csv

Create the necessary roles and role bindings for these users:


    ---
    kind: Role
    apiVersion: rbac.authorization.k8s.io/v1
    metadata:
      namespace: default
      name: pod-reader
    rules:
    - apiGroups: [""] # "" indicates the core API group
      resources: ["pods"]
      verbs: ["get", "watch", "list"]
     
    ---
    # This role binding allows "jane" to read pods in the "default" namespace.
    kind: RoleBinding
    apiVersion: rbac.authorization.k8s.io/v1
    metadata:
      name: read-pods
      namespace: default
    subjects:
    - kind: User
      name: user1 # Name is case sensitive
      apiGroup: rbac.authorization.k8s.io
    roleRef:
      kind: Role #this must be Role or ClusterRole
      name: pod-reader # this must match the name of the Role or ClusterRole you wish to bind to
      apiGroup: rbac.authorization.k8s.io

Once created, you may authenticate into the kube-api server using the users credentials

curl -v -k https://localhost:6443/api/v1/pods -u "user1:password123" 

# TLS Certificates

    What are TLS certificates?
    How does kubernetes use certificates?
    How to generate them?
    How to configure them?
    How to view them?
    How to troubleshoot issues related to certificates

<img width="885" alt="image" src="https://user-images.githubusercontent.com/75510135/127766484-8a3a4f31-0e9c-4085-9e20-d2fca3e927ae.png">

<img width="893" alt="image" src="https://user-images.githubusercontent.com/75510135/127766488-09af8f5c-4a4e-468e-a85c-319914ef99a7.png">

<img width="919" alt="image" src="https://user-images.githubusercontent.com/75510135/127766499-40287625-f1de-4bf2-8c24-c343141a3c83.png">

<img width="874" alt="image" src="https://user-images.githubusercontent.com/75510135/127766504-89ca09c4-10fe-4204-bda7-bf273154de47.png">

<img width="867" alt="image" src="https://user-images.githubusercontent.com/75510135/127766512-5ed03b09-023d-424a-9d01-e041ef8484c2.png">

<img width="876" alt="image" src="https://user-images.githubusercontent.com/75510135/127766518-48d2ba1b-756b-41ed-bae9-e5adb14a15fd.png">

<img width="906" alt="image" src="https://user-images.githubusercontent.com/75510135/127766521-e941c3a0-f4a3-455c-9125-50ce69ae7aaa.png">

<img width="899" alt="image" src="https://user-images.githubusercontent.com/75510135/127766531-e248b1ff-1c90-40f0-a770-9d8705613d58.png">

<img width="876" alt="image" src="https://user-images.githubusercontent.com/75510135/127766542-b48e838b-0fbf-40b2-b737-b6ea5061015c.png">

<img width="864" alt="image" src="https://user-images.githubusercontent.com/75510135/127766547-6cd24a73-c446-4b80-8e88-a2d7544b8952.png">

<img width="887" alt="image" src="https://user-images.githubusercontent.com/75510135/127766555-5d1dba8e-1075-4290-ae24-d76bf078f6f6.png">

<img width="508" alt="image" src="https://user-images.githubusercontent.com/75510135/127766560-f83ba61d-eae1-4fc0-b35f-104f84dfe7f8.png">

<img width="894" alt="image" src="https://user-images.githubusercontent.com/75510135/127766567-f8a2b1e4-a4b3-46a8-9152-571adfb983b3.png">

<img width="861" alt="image" src="https://user-images.githubusercontent.com/75510135/127766575-e61ca23a-ad40-4ff7-8138-929521f336c4.png">

# Certificate creation
<img width="755" alt="image" src="https://user-images.githubusercontent.com/75510135/127770346-cf85432f-aa8e-4cbd-86a1-ea3b7b5caba2.png">

<img width="788" alt="image" src="https://user-images.githubusercontent.com/75510135/127770356-5bf22c95-f7af-46fb-8ae6-3422941614e0.png">

<img width="676" alt="image" src="https://user-images.githubusercontent.com/75510135/127770359-47016b30-56e4-4479-9141-be8497a05423.png">


<img width="776" alt="image" src="https://user-images.githubusercontent.com/75510135/127770370-9b1a734f-d9fb-4323-8dba-da0e6bd5e48e.png">
<img width="780" alt="image" src="https://user-images.githubusercontent.com/75510135/127770377-93b2efcb-bbe3-468b-a2dc-47d8254f2949.png">
<img width="747" alt="image" src="https://user-images.githubusercontent.com/75510135/127770391-d6f494e1-702f-4c98-a195-1add9d69d407.png">
<img width="744" alt="image" src="https://user-images.githubusercontent.com/75510135/127770400-7f2ddc32-700c-41fe-a1fa-16c25073ef42.png">
<img width="666" alt="image" src="https://user-images.githubusercontent.com/75510135/127770407-4b6a5478-8fff-4801-aada-7165b725a22c.png">
<img width="793" alt="image" src="https://user-images.githubusercontent.com/75510135/127770412-86f04d15-8117-4b92-ba4c-344fe0849597.png">
<img width="791" alt="image" src="https://user-images.githubusercontent.com/75510135/127770417-7a4453d3-1ea8-4350-b894-619e92bb8f32.png">
<img width="782" alt="image" src="https://user-images.githubusercontent.com/75510135/127770426-1fa68751-f6cf-4891-bdf7-cb15efb79372.png">
<img width="790" alt="image" src="https://user-images.githubusercontent.com/75510135/127770431-5180602f-9c29-4373-88e5-7485113675e7.png">
<img width="799" alt="image" src="https://user-images.githubusercontent.com/75510135/127770435-07f021a2-8faf-43da-b98f-9ca2acdf76ca.png">
<img width="771" alt="image" src="https://user-images.githubusercontent.com/75510135/127770442-2b43dff6-1342-49dc-84fb-e73df1af5cf3.png">

# View Certificate Details
<img width="793" alt="image" src="https://user-images.githubusercontent.com/75510135/127770902-5984f555-6087-4d99-aed9-904e7f463b08.png">
<img width="639" alt="image" src="https://user-images.githubusercontent.com/75510135/127770907-04d56b15-3bfb-4ad2-baae-e200978ef950.png">
<img width="675" alt="image" src="https://user-images.githubusercontent.com/75510135/127770914-53ae7c79-9d4f-4812-9362-b3867c5f69f9.png">
<img width="795" alt="image" src="https://user-images.githubusercontent.com/75510135/127770919-9426e182-b849-4c90-9166-09ccad084fff.png">
<img width="791" alt="image" src="https://user-images.githubusercontent.com/75510135/127770925-d399082f-7752-4542-8c34-8c5e9b18e4e5.png">
<img width="803" alt="image" src="https://user-images.githubusercontent.com/75510135/127770927-a5c3db33-c0b8-4d9c-8b82-f946abc51ffd.png">
<img width="781" alt="image" src="https://user-images.githubusercontent.com/75510135/127770936-23a47ab2-f25d-4e02-a626-d04b0b315d1b.png">

                Identify the certificate file used for the kube-api server
                cat /etc/kubernetes/manifest/kube-apiserver.yaml

                Identify the Certificate file used to authenticate kube-apiserver as a client to ETCD Server
                cat /etc/kubernetes/manifest/kube-apiserver.yaml Answer: /etc/kubernetes/pki/apiserver-etcd-client.crt

                Identify the key used to authenticate kubeapi-server to the kubelet server
                /etc/kubernetes/pki/apiserver-kubelet-client.key 

                Identify the ETCD Server Certificate used to host ETCD server
                cat Look for cert file option in the file /etc/kubernetes/manifests/etcd.yaml  > /etc/kubernetes/pki/etcd/server.crt 

                Identify the ETCD Server CA Root Certificate used to serve ETCD Server
                cat  /etc/kubernetes/manifests/etcd.yaml > /etc/kubernetes/pki/etcd/ca.crt

                Common Name (CN) configured on the Kube API Server Certificate
                openssl x509 -in /etc/kubernetes/pki/apiserver.crt -text > look for issuer

                 name of the CA who issued the Kube API Server Certificate
                 openssl x509 -in /etc/kubernetes/pki/apiserver.crt -text > look for Alternative name


                 alternate names is not configured on the Kube API Server Certificate
                 openssl x509 -in /etc/kubernetes/pki/etcd/server.crt -text >  look at Alternative Names

                 Common Name (CN) configured on the ETCD Server certificate
                 openssl x509 -in /etc/kubernetes/pki/etcd/server.crt -text > look for Subject CN

                 Common Name (CN) configured on the ETCD Server certificate
                 openssl x509 -in /etc/kubernetes/pki/apiserver.crt -text > check on the Expiry date

                from the issued date, is the Kube-API Server Certificate valid for
                File: /etc/kubernetes/pki/apiserver.crt
                openssl x509 -in /etc/kubernetes/pki/ca.crt -text' > look for validity


                Check it out! Someone recently modified the /etc/kubernetes/manifests/etcd.yaml 
                vi /etc/kubernetes/manifests/etcd.yaml  > Inspect the --cert-file option

                ETCD has its own CA. The right CA must be used for the ETCD-CA file in /etc/kubernetes/manifests/kube-apiserver.yaml. /var/answers/kube-apiserver.yaml 


# Certificate API
<img width="845" alt="image" src="https://user-images.githubusercontent.com/75510135/127772064-bb014e32-632f-485f-bed3-46e3aa1be56a.png">

<img width="829" alt="image" src="https://user-images.githubusercontent.com/75510135/127772073-2819362c-55c8-4b28-95ff-bd94dd6ae447.png">

<img width="835" alt="image" src="https://user-images.githubusercontent.com/75510135/127772082-b6ae0f8e-a72d-45aa-8142-c0cfc19aecc8.png">

<img width="662" alt="image" src="https://user-images.githubusercontent.com/75510135/127772089-5e3c3d0f-d21b-4b53-866a-792cff34e595.png">
<img width="819" alt="image" src="https://user-images.githubusercontent.com/75510135/127772098-6eb1e44a-6d11-462a-9f78-3366170526ab.png">
<img width="792" alt="image" src="https://user-images.githubusercontent.com/75510135/127772109-b26666e7-4c68-48ac-873b-f5917c87ca88.png">

                A new member akshay joined our team. He requires access to our cluster. The Certificate Signing Request
                .csr & .key

                Create a CertificateSigningRequest object with the name akshay with the contents of the akshay.csr
                kubectl create -f /var/answers/akshay-csr.yaml

                Check csr status
                kubectl get csr

                Approve csr
                kubectl certificate approve akshay

                Check approval requests
                 kubectl get csr

                 Check the details about the CSR request. Preferebly in YAML.
                 kubectl get csr agent-smith -o yaml

                 Reject the request
                 kubectl certificate deny agent-smith 

                 Delete the csr request
                 kubectl delete csr agent-smith
                 
 # KubeConfig
 <img width="823" alt="image" src="https://user-images.githubusercontent.com/75510135/127779200-19fae2bd-720b-4d58-aadc-85e9af46fcfa.png">

<img width="820" alt="image" src="https://user-images.githubusercontent.com/75510135/127779207-070acd69-2437-490c-950e-9c72474e5fb7.png">

<img width="831" alt="image" src="https://user-images.githubusercontent.com/75510135/127779218-5e75bb98-92c7-4c59-9525-9885284d1b99.png">
<img width="836" alt="image" src="https://user-images.githubusercontent.com/75510135/127779230-5e74011f-bf2d-47bb-8c22-90c8a8ddc83d.png">

<img width="839" alt="image" src="https://user-images.githubusercontent.com/75510135/127779241-cf9382e7-ac1b-46ef-8ba0-b4de15da6bbf.png">
<img width="804" alt="image" src="https://user-images.githubusercontent.com/75510135/127779247-689332e1-0e8a-4e88-9c3c-b61fee94cb7a.png">
<img width="841" alt="image" src="https://user-images.githubusercontent.com/75510135/127779257-40efae2e-e42f-4f2f-9cb3-f80c0aac7520.png">
<img width="685" alt="image" src="https://user-images.githubusercontent.com/75510135/127779262-f9a4202e-4975-4631-91b6-b8aaa176977c.png">
<img width="850" alt="image" src="https://user-images.githubusercontent.com/75510135/127779271-4351db39-2bd2-4c5a-a271-d751fadc0ac4.png">
<img width="831" alt="image" src="https://user-images.githubusercontent.com/75510135/127779280-78d615a4-ce90-4723-b59f-90b6728b97d5.png">

                kube config file under /root/.kube
                 ls -l /root/.kube

                Cluster info, cluster/users/context
                kubectl config view 

                To view config other than .kube path
                kubectl config view --kubeconfig my-kube-config 

                Set the current context to research
                kubectl config --kubeconfig=/root/my-kube-config use-context research

                Replace the contents in the default kubeconfig file with the content from my-kube-config file
                mv .kube/config .kube/config.bak $ cp /root/my-kube-config .kube/config 

                If the path to certificate is incorrect in the kubeconfig file. Fix it. All users  certificates are stored at /etc/kubernetes/pki/users
                $ kubectl get pods master $ ls dev-user.crt dev-user.csr dev-user.key master $ vi /root/.kube/config master $ grep dev-user.crt /root/.kube/config client-certificate: /etc/kubernetes/pki/users/dev-user/dev-user.crt master $ pwd /etc/kubernetes/pki/users/dev-user master $ kubectl get pods No resources found in default namespace. 

# API Group
<img width="834" alt="image" src="https://user-images.githubusercontent.com/75510135/127790728-5026cb7f-f714-4bd9-9cfe-dfc72fb3bf53.png">

<img width="847" alt="image" src="https://user-images.githubusercontent.com/75510135/127790742-5eb66d36-bbd5-46d5-b986-e80e8cc19539.png">

<img width="825" alt="image" src="https://user-images.githubusercontent.com/75510135/127790748-09d813f6-d9cd-4092-996b-48ef079251f3.png">

<img width="669" alt="image" src="https://user-images.githubusercontent.com/75510135/127790755-e40cd57c-0b0a-4d50-8e0d-9886bc00627a.png">

<img width="852" alt="image" src="https://user-images.githubusercontent.com/75510135/127790761-31bfab41-7735-4648-8d6a-7ff27eeb739b.png">

<img width="839" alt="image" src="https://user-images.githubusercontent.com/75510135/127790769-7d2a2a50-4521-48d1-927f-f8a039b8632f.png">

<img width="846" alt="image" src="https://user-images.githubusercontent.com/75510135/127790784-8e93e6fd-ec69-4d83-81fb-46010bc78f9d.png">

# Authorization
<img width="832" alt="image" src="https://user-images.githubusercontent.com/75510135/127790809-8ea71eff-8565-4b4c-a882-0dd5c8650b2d.png">

<img width="567" alt="image" src="https://user-images.githubusercontent.com/75510135/127790818-27b13a92-7594-4451-ad83-40c414da5a07.png">

<img width="835" alt="image" src="https://user-images.githubusercontent.com/75510135/127790825-ff8bb327-b180-4a77-af04-12751036ddaa.png">

<img width="842" alt="image" src="https://user-images.githubusercontent.com/75510135/127790832-958e2770-8b48-49d4-9344-b11733190975.png">

<img width="831" alt="image" src="https://user-images.githubusercontent.com/75510135/127790846-bdf5d7fc-39a2-43d9-9be9-f31e93ac5334.png">

<img width="839" alt="image" src="https://user-images.githubusercontent.com/75510135/127790857-51accc9a-bd06-44e9-b855-3bd5b565504b.png">

<img width="837" alt="image" src="https://user-images.githubusercontent.com/75510135/127790873-01d62ac3-5917-4677-808a-667d9fc7a3ce.png">

<img width="807" alt="image" src="https://user-images.githubusercontent.com/75510135/127790885-fe1e160d-21e5-4e3a-8b41-8540ffaf6729.png">

# RBAC
<img width="783" alt="image" src="https://user-images.githubusercontent.com/75510135/127790921-b940bd47-a422-4523-a466-f52299b0293a.png">

<img width="599" alt="image" src="https://user-images.githubusercontent.com/75510135/127790928-63dba7ca-eecb-40c7-9526-f1aea565acb6.png">

<img width="813" alt="image" src="https://user-images.githubusercontent.com/75510135/127790934-a5888fd2-4f63-4d83-a5d2-bf0472704229.png">
<img width="539" alt="image" src="https://user-images.githubusercontent.com/75510135/127790943-07292994-02c6-423a-829d-1bc3e158dace.png">
<img width="658" alt="image" src="https://user-images.githubusercontent.com/75510135/127790952-fcf6ecc1-a8b7-4aab-98eb-432fc64cbc9d.png">
<img width="723" alt="image" src="https://user-images.githubusercontent.com/75510135/127790959-405404e4-0135-48d0-8898-4cc1aaa3fbde.png">
<img width="682" alt="image" src="https://user-images.githubusercontent.com/75510135/127790963-54f66527-98d2-405d-9b06-a2e27dbd2126.png">
<img width="690" alt="image" src="https://user-images.githubusercontent.com/75510135/127790971-174a5bcd-0e21-475c-8082-eb45bd432411.png">
<img width="799" alt="image" src="https://user-images.githubusercontent.com/75510135/127790981-b3acda43-5984-4894-bb99-4ff40c39df26.png">
                <img width="826" alt="image" src="https://user-images.githubusercontent.com/75510135/127790988-ae52cf6d-b337-4bc6-922b-68df465aec60.png">

                identify the authorization modes configured on the cluster.
                kubectl describe pod kube-apiserver-controlplane -n kube-system > look for --authorization-mode=Node,RBAC

                How many roles exist in the default namespace
                kubectl get roles
                kubectl get roles --all-namespaces

                the resources the kube-proxy role in the kube-system namespace is given access to
                kubectl describe role kube-proxy -n kube-system

                Which account is the kube-proxy role assigned to
                kubectl describe rolebinding kube-proxy -n kube-system 

                A user dev-user is created. User's details have been added to the kubeconfig file. Inspect the permissions granted to the user. Check if the user can list pods in the default namespace
                kubectl get pods --as dev-user

                Create the necessary roles and role bindings required for the dev-user to create, list and delete pods in the default namespace.
                kubectl create -f /var/answers/developer-role.yaml

                dev-user is trying to get details about the dark-blue-app pod in the blue namespace. Investigate and fix the issue.
                $ kubectl get roles,rolebindings -n blue
                $ kubectl describe role developer -n blue
                $ kubectl edit role developer -n blue (update the resourceNames)

# Cluster Roles
<img width="707" alt="image" src="https://user-images.githubusercontent.com/75510135/127791744-98f1b76f-016d-41aa-ae5d-cad76894d809.png">
<img width="827" alt="image" src="https://user-images.githubusercontent.com/75510135/127791755-7f5cc099-bd24-4828-af1d-5127a4e4f4cd.png">
<img width="626" alt="image" src="https://user-images.githubusercontent.com/75510135/127791764-7e4dfce8-9ba6-4f07-ad41-bc2e311ae6ad.png">
<img width="833" alt="image" src="https://user-images.githubusercontent.com/75510135/127791782-4b4e5868-b0f1-48a1-9670-8092fe9ed7a8.png">
<img width="839" alt="image" src="https://user-images.githubusercontent.com/75510135/127791797-823d16ff-eb51-494e-a1cd-3f4e4121257f.png">
<img width="844" alt="image" src="https://user-images.githubusercontent.com/75510135/127791816-d9006934-e4bf-47a5-99d7-62252e5f72a1.png">

                How many ClusterRoles do you see defined in the cluster
                $ kubectl get clusterroles --no-headers | wc -l (or)
                $ kubectl get clusterroles --no-headers -o json | jq '.items | length'

                How many ClusterRoleBindings exist on the cluster
                $ kubectl get clusterrolebindings --no-headers | wc -l (or)
                $ kubectl get clusterrolebindings --no-headers -o json | jq '.items | length'

                What namespace is the cluster-admin clusterrole part o

                What user/groups are the cluster-admin role bound to
                kubectl describe clusterrolebinding cluster-admin

                What level of permission does the cluster-admin role grant?
                kubectl describe clusterrole cluster-admin

                A new user michelle joined the team. She will be focusing on the nodes in the cluster. Create the required ClusterRoles and ClusterRoleBindings so she gets access to the nodes.
                kubectl create -f /var/answers/michelle-node-admin.yaml

                michelle's responsibilities are growing and now she will be responsible for storage as well. Create the required ClusterRoles and ClusterRoleBindings to allow her access to Storage.
                kubectl create -f /var/answers/michelle-storage-admin.yaml

                Grant the dev-user permissions to create deployments in the blue namespace.
                kubectl create -f /var/answers/dev-user-deploy.yaml





































