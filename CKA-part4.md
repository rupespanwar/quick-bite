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

