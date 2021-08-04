<img width="631" alt="image" src="https://user-images.githubusercontent.com/75510135/127624609-00f5a29c-4606-4b8b-85a7-07f25f113a50.png">
<img width="796" alt="image" src="https://user-images.githubusercontent.com/75510135/127626373-c2dd3ac7-3f5d-4f47-9176-3e6081a2eed5.png">

<img width="728" alt="image" src="https://user-images.githubusercontent.com/75510135/127626398-77a6fce8-f164-453f-a6c5-1ae9171a4405.png">
<img width="797" alt="image" src="https://user-images.githubusercontent.com/75510135/127626429-cc3de3d1-ae8a-4a42-bf3d-80ea4e85b5ab.png">

<img width="764" alt="image" src="https://user-images.githubusercontent.com/75510135/127626488-771ea9f8-f341-480b-af51-c9ac5d536e95.png">

<img width="747" alt="image" src="https://user-images.githubusercontent.com/75510135/127626511-0f9524ab-c74c-4425-9251-6a6ff607194e.png">

<img width="800" alt="image" src="https://user-images.githubusercontent.com/75510135/127626534-6c1ad4e5-6a87-4212-96c2-1098c735989f.png">

<img width="807" alt="image" src="https://user-images.githubusercontent.com/75510135/127626554-acc16836-2067-47c5-93d2-fa3246667b19.png">

<img width="813" alt="image" src="https://user-images.githubusercontent.com/75510135/127626601-ec10d994-3078-4cbe-97c4-a4f76166b709.png">

<img width="786" alt="image" src="https://user-images.githubusercontent.com/75510135/127626639-e1a29d6e-a512-472f-9bf5-9a39378b8470.png">

<img width="771" alt="image" src="https://user-images.githubusercontent.com/75510135/127626665-64a13599-29f9-4304-9045-939a71cb1354.png">

        kubectl create -f deployment-definition.yaml
        kubectl get deployments
        kubectl apply -f deployment-definition.yaml
        kubectl set image deployment/myapp-deployment nginx=nginx:1.9.1
        kubectl rollout status deployment/myapp-deployment
        kubectl rollout history deployment/myapp-deployment
        kubectl rollout undo deployment/myapp-deployment

        curl-test.sh
        for i in {1..35}; do
           kubectl exec --namespace=kube-public curl -- sh -c 'test=`wget -qO- -T 2  http://webapp-service.default.svc.cluster.local:8080/info 2>&1` && echo "$test OK" || echo "Failed"';
           echo ""
        done

         kubectl describe deploy frontend | grep Image
         kubectl describe deploy frontend | grep StrategyType:
         kubectl set image deployment/deploymentName containerName=newImage/webapp-color:v2


Configure Applications

Configuring applications comprises of understanding the following concepts:

    Configuring Command and Arguments on applications

    Configuring Environment Variables

    Configuring Secrets
    
 <img width="771" alt="image" src="https://user-images.githubusercontent.com/75510135/127632502-fb3e2795-820d-4820-941d-40b57255e7ed.png">

 <img width="806" alt="image" src="https://user-images.githubusercontent.com/75510135/127632602-33c67f3c-f9f6-43b1-ad2c-1af844d48a93.png">

<img width="819" alt="image" src="https://user-images.githubusercontent.com/75510135/127632630-b6503af3-d6ce-4cba-b92d-51499c5e117c.png">

<img width="802" alt="image" src="https://user-images.githubusercontent.com/75510135/127632656-93398b6b-4e19-473e-ab8e-b85cfb2b22b9.png">

<img width="845" alt="image" src="https://user-images.githubusercontent.com/75510135/127632755-2214aaee-8c81-41ee-afd8-b632e13a796e.png">

<img width="818" alt="image" src="https://user-images.githubusercontent.com/75510135/127632853-57247347-19a4-43ab-a22a-a3c67a94cf58.png">

![image](https://user-images.githubusercontent.com/75510135/127644944-5035a569-4bac-4969-a1d8-cecbbf75db92.png)
![image](https://user-images.githubusercontent.com/75510135/127645011-3a634d02-d4d6-4e7c-8683-7da4a80f0bca.png)

* Create a pod with the ubuntu image to run a container to sleep for 5000 seconds

                                apiVersion: v1
                                kind: Pod
                                metadata:
                                  name: ubuntu-sleeper-pod
                                spec:
                                 containers:
                                 - name: ubuntu-sleeper
                                   image: ubuntu-sleeper
                                   command: ["sleep","5000"]
                                //   args: ["5000"]
  

 # Configure Environment Variables In Applications

![image](https://user-images.githubusercontent.com/75510135/127650614-b264f7e9-ae5b-454e-a8a4-98b04a38f9a6.png)
![image](https://user-images.githubusercontent.com/75510135/127650673-94e4f3e0-b60c-470b-9fee-a0cd2685c938.png)
![image](https://user-images.githubusercontent.com/75510135/127650730-bd323e68-c391-4865-ba1e-61f570f104d3.png)
![image](https://user-images.githubusercontent.com/75510135/127650798-d7329bed-b087-40df-a47c-db8bf36d5b9a.png)
    kubectl create configmap app-config --from-literal=APP_COLOR=blue --from-literal=APP_MODE=prod
    kubectl create configmap app-config --from-file=app_config.properties (Another way)

![image](https://user-images.githubusercontent.com/75510135/127650969-731aec36-1ac9-4001-a733-03e840f62f0f.png)

![image](https://user-images.githubusercontent.com/75510135/127651084-5e69c7c5-4c59-4984-8e24-a46856cab6f9.png)

![image](https://user-images.githubusercontent.com/75510135/127651150-37b1d1f0-8eb9-4d5c-a341-3f7eb42647af.png)

![image](https://user-images.githubusercontent.com/75510135/127651202-b0ebea5f-cdac-4cc8-8574-03eb73338d1e.png)

![image](https://user-images.githubusercontent.com/75510135/127651242-af1e88a5-b364-4032-9c86-0c5c79f42779.png)

![image](https://user-images.githubusercontent.com/75510135/127651268-df726b6f-c2d4-4bda-89b0-cde5f0a3cdd4.png)

![image](https://user-images.githubusercontent.com/75510135/127651344-e26dcf44-ce0b-463d-b6fb-49a53ac46321.png)
![image](https://user-images.githubusercontent.com/75510135/127651299-ec962704-bd37-478a-bfdd-3fd256dee769.png)

        kubectl get cm
        kubectl create configmap webapp-config-map --from-literal=APP_COLOR=darkblue
        kubectl get pods webapp-color -o yaml > new-webapp.yaml
        kubectl delete pods webapp-color
        Update pod definition file, under spec.containers section update the below.
        - envFrom:
          - configMapRef:
             name: webapp-config-map
        kubectl create -f new-webapp.yaml


# Secrets
<img width="753" alt="image" src="https://user-images.githubusercontent.com/75510135/127661115-0cf75fc7-c656-4d3b-bf23-57791a63daf2.png">

<img width="747" alt="image" src="https://user-images.githubusercontent.com/75510135/127661149-cfe12a91-b54e-414a-80a8-7db7b9cb291b.png">

<img width="757" alt="image" src="https://user-images.githubusercontent.com/75510135/127661176-f6a9a496-5c30-4a03-b675-fe5d58309043.png">

<img width="762" alt="image" src="https://user-images.githubusercontent.com/75510135/127661200-44b970bb-0233-4827-8479-a3b221f9d7cb.png">

<img width="772" alt="image" src="https://user-images.githubusercontent.com/75510135/127661224-e78cbb87-6dc9-47de-8d1a-372cd0572a91.png">

<img width="740" alt="image" src="https://user-images.githubusercontent.com/75510135/127661246-c9de3890-8584-4703-9097-f69b245302cd.png">

<img width="771" alt="image" src="https://user-images.githubusercontent.com/75510135/127661289-81dc4d92-c564-453c-b0e6-1c3a561e5ff7.png">

<img width="631" alt="image" src="https://user-images.githubusercontent.com/75510135/127661309-a4461e28-350e-4197-ac9c-77b5f89b971c.png">
<img width="764" alt="image" src="https://user-images.githubusercontent.com/75510135/127661327-17b87273-2705-4ae0-99d4-f154c16a87ef.png">

<img width="733" alt="image" src="https://user-images.githubusercontent.com/75510135/127661360-94fddb4b-7bb2-4477-a97e-bcc09add2b6c.png">

<img width="769" alt="image" src="https://user-images.githubusercontent.com/75510135/127661406-7e97c4be-4793-49df-8b46-31370f725b75.png">

<img width="767" alt="image" src="https://user-images.githubusercontent.com/75510135/127661449-32d807a1-7c7f-463d-b443-0b034a8e9605.png">
<img width="671" alt="image" src="https://user-images.githubusercontent.com/75510135/127661479-33baadc5-65cc-4fd6-adbc-5c3350c89609.png">
<img width="723" alt="image" src="https://user-images.githubusercontent.com/75510135/127661502-cc0d14e1-fa1e-49b1-897e-9301c51186ea.png">

# Multi-Container PODs


<img width="467" alt="image" src="https://user-images.githubusercontent.com/75510135/127722176-0e411c0c-c91a-4573-b6eb-c43bbd7eafd4.png">

<img width="601" alt="image" src="https://user-images.githubusercontent.com/75510135/127722183-bbb8e1e0-3463-4207-a4c8-37c56e4a0163.png">

<img width="676" alt="image" src="https://user-images.githubusercontent.com/75510135/127722194-4fa6ffa3-db79-464d-b1c7-7b28a7e06fec.png">

<img width="711" alt="image" src="https://user-images.githubusercontent.com/75510135/127722205-1d68f636-6562-4880-b56f-2953f3d644e8.png">

# InitContainers

In a multi-container pod, each container is expected to run a process that stays alive as long as the POD's lifecycle. For example in the multi-container pod that we talked about earlier that has a web application and logging agent, both the containers are expected to stay alive at all times. The process running in the log agent container is expected to stay alive as long as the web application is running. If any of them fails, the POD restarts.


But at times you may want to run a process that runs to completion in a container. For example a process that pulls a code or binary from a repository that will be used by the main web application. That is a task that will be run only  one time when the pod is first created. Or a process that waits  for an external service or database to be up before the actual application starts. That's where initContainers comes in.


An initContainer is configured in a pod like all other containers, except that it is specified inside a initContainers section,  like this:


    apiVersion: v1
    kind: Pod
    metadata:
      name: myapp-pod
      labels:
        app: myapp
    spec:
      containers:
      - name: myapp-container
        image: busybox:1.28
        command: ['sh', '-c', 'echo The app is running! && sleep 3600']
      initContainers:
      - name: init-myservice
        image: busybox
        command: ['sh', '-c', 'git clone <some-repository-that-will-be-used-by-application> ; done;']


When a POD is first created the initContainer is run, and the process in the initContainer must run to a completion before the real container hosting the application starts. 

You can configure multiple such initContainers as well, like how we did for multi-pod containers. In that case each init container is run one at a time in sequential order.

If any of the initContainers fail to complete, Kubernetes restarts the Pod repeatedly until the Init Container succeeds.

    apiVersion: v1
    kind: Pod
    metadata:
      name: myapp-pod
      labels:
        app: myapp
    spec:
      containers:
      - name: myapp-container
        image: busybox:1.28
        command: ['sh', '-c', 'echo The app is running! && sleep 3600']
      initContainers:
      - name: init-myservice
        image: busybox:1.28
        command: ['sh', '-c', 'until nslookup myservice; do echo waiting for myservice; sleep 2; done;']
      - name: init-mydb
        image: busybox:1.28
        command: ['sh', '-c', 'until nslookup mydb; do echo waiting for mydb; sleep 2; done;']
        
        
# Cluster Maintenance
<img width="585" alt="image" src="https://user-images.githubusercontent.com/75510135/127731598-9c7f991a-02f9-49e9-932c-2d2e5e415093.png">

<img width="774" alt="image" src="https://user-images.githubusercontent.com/75510135/127732119-d2cfb9c4-f7e9-4198-bea0-b186d3cc9721.png">

<img width="784" alt="image" src="https://user-images.githubusercontent.com/75510135/127732139-047d938b-0918-4117-ae0c-0b186e02040d.png">

                         take node01 out for maintenance 
                         kubectl drain node01 --ignore-daemonsets
                         Configure the node node01 to be schedulable
                         kubectl uncordon node01
                         kubectl drain node02 --ignore-daemonsets --force



# Kubernetes Software Versions
<img width="584" alt="image" src="https://user-images.githubusercontent.com/75510135/127733297-07237e20-35c7-4ab3-9872-7f5487f360db.png">

<img width="769" alt="image" src="https://user-images.githubusercontent.com/75510135/127733304-716bf98f-4f26-423d-844d-2494923d50c2.png">

<img width="425" alt="image" src="https://user-images.githubusercontent.com/75510135/127733311-0a835ff5-caf0-4679-bd1f-47ca7507a0e1.png">

<img width="855" alt="image" src="https://user-images.githubusercontent.com/75510135/127733320-b927dc92-9994-49c4-80ac-c1207513e244.png">

# Cluster upgrade
<img width="1052" alt="image" src="https://user-images.githubusercontent.com/75510135/127755201-e913d019-5ad9-4f26-a694-60f018658714.png">

<img width="908" alt="image" src="https://user-images.githubusercontent.com/75510135/127755215-ca3ee107-16a6-429e-9536-0c481067fb97.png">

<img width="845" alt="image" src="https://user-images.githubusercontent.com/75510135/127755626-a98e2828-ccba-4166-ba7c-ddc8eed52003.png">

<img width="878" alt="image" src="https://user-images.githubusercontent.com/75510135/127755642-57a5dfe8-750f-4805-9d41-a2a954be2e5c.png">

<img width="847" alt="image" src="https://user-images.githubusercontent.com/75510135/127755653-7a1e0cf8-2766-488d-8e29-986335b3f2ce.png">

<img width="844" alt="image" src="https://user-images.githubusercontent.com/75510135/127755661-fe5db2bb-85b2-4835-aa83-95439ba758e0.png">

<img width="826" alt="image" src="https://user-images.githubusercontent.com/75510135/127755674-826f04f9-e026-43ff-8395-c40fd17edcad.png">

<img width="855" alt="image" src="https://user-images.githubusercontent.com/75510135/127755686-d3602bc6-2a11-40c8-bd92-d607a499a260.png">

<img width="848" alt="image" src="https://user-images.githubusercontent.com/75510135/127755705-99d559fe-5565-480a-bde2-1d7ce61ad29b.png">

<img width="843" alt="image" src="https://user-images.githubusercontent.com/75510135/127755711-9741b82b-ea1a-46a3-940e-013930278c09.png">

<img width="855" alt="image" src="https://user-images.githubusercontent.com/75510135/127755715-977b75a1-6d2a-4c05-bd74-4ef8f9d399df.png">

<img width="844" alt="image" src="https://user-images.githubusercontent.com/75510135/127755717-e4621608-bc31-4b0d-a1f5-8bddb826509d.png">

<img width="809" alt="image" src="https://user-images.githubusercontent.com/75510135/127755720-c6bcf6a2-1cbd-4116-ac79-74636c9e3f6b.png">

<img width="855" alt="image" src="https://user-images.githubusercontent.com/75510135/127755722-90cd76e9-cb37-478c-9eb0-087722b137c5.png">

<img width="850" alt="image" src="https://user-images.githubusercontent.com/75510135/127755724-b00a357b-7bac-490f-9555-1f0b83b8a2b0.png">

                        how many nodes can host the applications
                        kubectl get pods -o wide

                        how many applications are hosted on cluster
                        kubectl get deploy

                        latest stable version available for upgrade
                        kubeadm upgrade plan

                        Upgrade master node first , drain it 
                        kubectl drain master --ignore-daemonsets
                        apt install kubeadm=1.18.0-00 
                        kubeadm upgrade apply v1.18.0 
                        apt install kubelet=1.18.0-00

                        sudo apt-get update
                        sudo apt-get install -y kubelet kubeadm kubectl
                        sudo apt-mark hold kubelet kubeadm kubectl

                        Mark the controlplane node as "Schedulable" again
                        kubectl uncordon master 

                        Drain the worker node of the workloads and mark it UnSchedulable
                        kubectl drain node01 --ignore-daemonsets --force
                        apt install kubeadm=1.18.0-00 
                        kubeadm upgrade node 
                        apt install kubelet=1.18.0-00
                         kubectl uncordon node01

                        # replace x in 1.21.x-00 with the latest patch version
                        apt-mark unhold kubeadm && \
                        apt-get update && apt-get install -y kubeadm=1.21.x-00 && \
                        apt-mark hold kubeadm
                        -
                        # since apt-get version 1.1 you can also use the following method
                        apt-get update && \
                        apt-get install -y --allow-change-held-packages kubeadm=1.21.x-00


# Backup & Restore
<img width="840" alt="image" src="https://user-images.githubusercontent.com/75510135/127757225-5391ee42-41ca-4a0b-8314-32179a5abcaf.png">
<img width="845" alt="image" src="https://user-images.githubusercontent.com/75510135/127757229-93f796fb-3ea2-4703-aa21-b33f5dbc6e03.png">


<img width="852" alt="image" src="https://user-images.githubusercontent.com/75510135/127757230-9a5f3752-a45c-4139-a1f4-0d0757df9443.png">

<img width="842" alt="image" src="https://user-images.githubusercontent.com/75510135/127757240-7e0f6db8-6a27-42e9-91a7-d28f23f2db09.png">
<img width="723" alt="image" src="https://user-images.githubusercontent.com/75510135/127757246-2027560c-d239-498b-8cab-11e049648ab8.png">
<img width="829" alt="image" src="https://user-images.githubusercontent.com/75510135/127757250-77053bc0-7e7f-4eb5-b355-1a1ef8f45399.png">
<img width="852" alt="image" src="https://user-images.githubusercontent.com/75510135/127757255-06d64a17-e1f6-41c5-a520-ad1291fecfb2.png">
<img width="852" alt="image" src="https://user-images.githubusercontent.com/75510135/127757260-93c7a9ff-0c85-4d38-ba35-d0b4233abe31.png">
<img width="835" alt="image" src="https://user-images.githubusercontent.com/75510135/127757264-282a19ff-0340-4af4-b389-8c4601557779.png">

<img width="837" alt="image" src="https://user-images.githubusercontent.com/75510135/127757268-98ee3c59-9bb2-4a79-8cdc-d05e52dbd6dd.png">
<img width="831" alt="image" src="https://user-images.githubusercontent.com/75510135/127757274-c490ac2a-041d-4dd0-b097-1e10f23eecf0.png">

Version of ETCD
kubectl logs etcd-master -n kube-system 
kubectl describe pod etcd-controlplance -n kube-system

At what address can you reach the ETCD cluster from the controlplane node,  look for --listen-client-urls
kubectl describe pod etcd-controlplane -n kube-system 

Take a snapshot of the ETCD database using the built-in snapshot functionality
 ETCDCTL_API=3 etcdctl --endpoints=https://[127.0.0.1]:2379 --cacert=/etc/kubernetes/pki/etcd/ca.crt --cert=/etc/kubernetes/pki/etcd/server.crt key=/etc/kubernetes/pki/etcd/server.key snapshot save /tmp/snapshot-pre-boot.db
 
 ETCD_VER=v3.4.9

# choose either URL
GOOGLE_URL=https://storage.googleapis.com/etcd
GITHUB_URL=https://github.com/etcd-io/etcd/releases/download
DOWNLOAD_URL=${GOOGLE_URL}

rm -f /tmp/etcd-${ETCD_VER}-linux-amd64.tar.gz
rm -rf /tmp/etcd-download-test && mkdir -p /tmp/etcd-download-test

curl -L ${DOWNLOAD_URL}/${ETCD_VER}/etcd-${ETCD_VER}-linux-amd64.tar.gz -o /tmp/etcd-${ETCD_VER}-linux-amd64.tar.gz
tar xzvf /tmp/etcd-${ETCD_VER}-linux-amd64.tar.gz -C /tmp/etcd-download-test --strip-components=1
rm -f /tmp/etcd-${ETCD_VER}-linux-amd64.tar.gz

/tmp/etcd-download-test/etcd --version
ETCDCTL_API=3 /tmp/etcd-download-test/etcdctl version

mv /tmp/etcd-download-test/etcdctl /usr/bin

ETCDCTL_API=3 etcdctl --endpoints=https://[127.0.0.1]:2379 --cacert=/etc/kubernetes/pki/etcd/ca.crt \
     --cert=/etc/kubernetes/pki/etcd/server.crt --key=/etc/kubernetes/pki/etcd/server.key \
     snapshot save /opt/snapshot-pre-boot.db
     
 ## Restore
 ETCDCTL_API=3 etcdctl  --data-dir /var/lib/etcd-from-backup \
     snapshot restore /opt/snapshot-pre-boot.db




 








Working with ETCDCTL


etcdctl is a command line client for etcd.


In all our Kubernetes Hands-on labs, the ETCD key-value database is deployed as a static pod on the master. The version used is v3.

To make use of etcdctl for tasks such as back up and restore, make sure that you set the ETCDCTL_API to 3.


You can do this by exporting the variable ETCDCTL_API prior to using the etcdctl client. This can be done as follows:

export ETCDCTL_API=3

On the Master Node:


To see all the options for a specific sub-command, make use of the -h or --help flag.


For example, if you want to take a snapshot of etcd, use:

etcdctl snapshot save -h and keep a note of the mandatory global options.


Since our ETCD database is TLS-Enabled, the following options are mandatory:

--cacert                                                verify certificates of TLS-enabled secure servers using this CA bundle

--cert                                                    identify secure client using this TLS certificate file

--endpoints=[127.0.0.1:2379]          This is the default as ETCD is running on master node and exposed on localhost 2379.

--key                                                      identify secure client using this TLS key file



Similarly use the help option for snapshot restore to see all available options for restoring the backup.

etcdctl snapshot restore -h

For a detailed explanation on how to make use of the etcdctl command line tool and work with the -h flags, check out the solution video for the Backup and Restore Lab.

 
 
