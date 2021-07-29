<img width="1354" alt="image" src="https://user-images.githubusercontent.com/75510135/127425532-94b5ea9a-8433-4012-96a3-b7e14157a645.png">

# ETCD
<img width="1354" alt="image" src="https://user-images.githubusercontent.com/75510135/127425400-837a2606-105e-4273-9f63-c033e60e694d.png">

<img width="1354" alt="image" src="https://user-images.githubusercontent.com/75510135/127425382-b70918a8-1343-47a4-9de2-ba8ef2f0e658.png">
<img width="1354" alt="image" src="https://user-images.githubusercontent.com/75510135/127425415-70e27f6c-fd16-410f-a487-a7035d7b98af.png">

<img width="1354" alt="image" src="https://user-images.githubusercontent.com/75510135/127425428-300d9e39-06fe-49e0-a520-4acabd9ebbef.png">

<img width="1354" alt="image" src="https://user-images.githubusercontent.com/75510135/127425456-eeb5c251-4e99-4423-84a0-c513a902c1cb.png">


<img width="1354" alt="image" src="https://user-images.githubusercontent.com/75510135/127425438-ff3809ab-f72f-4d78-8b12-3221fcfdd7aa.png">

<img width="1354" alt="image" src="https://user-images.githubusercontent.com/75510135/127425547-8fd08296-d0ae-4ef9-91d4-12bb53e6a84a.png">
<img width="1354" alt="image" src="https://user-images.githubusercontent.com/75510135/127425559-0e4b9ce8-ed03-491e-94df-b026d43150e1.png">

<img width="1354" alt="image" src="https://user-images.githubusercontent.com/75510135/127425589-27332eaa-81b8-4678-b05e-6e0a90c61651.png">

<img width="1354" alt="image" src="https://user-images.githubusercontent.com/75510135/127425604-73cb5c1c-8817-4f89-a9a1-16c83e67e854.png">

<img width="1354" alt="image" src="https://user-images.githubusercontent.com/75510135/127425618-5be9af0f-7152-420d-837e-11361bf49a61.png">

# ETCD - Commands (Optional)

(Optional) Additional information about ETCDCTL Utility

ETCDCTL is the CLI tool used to interact with ETCD.

ETCDCTL can interact with ETCD Server using 2 API versions - Version 2 and Version 3.  By default its set to use Version 2. Each version has different sets of commands.

For example ETCDCTL version 2 supports the following commands:

    etcdctl backup
    etcdctl cluster-health
    etcdctl mk
    etcdctl mkdir
    etcdctl set


Whereas the commands are different in version 3

    etcdctl snapshot save 
    etcdctl endpoint health
    etcdctl get
    etcdctl put


To set the right version of API set the environment variable ETCDCTL_API command

export ETCDCTL_API=3


When API version is not set, it is assumed to be set to version 2. And version 3 commands listed above don't work. When API version is set to version 3, version 2 commands listed above don't work.


Apart from that, you must also specify path to certificate files so that ETCDCTL can authenticate to the ETCD API Server. The certificate files are available in the etcd-master at the following path. We discuss more about certificates in the security section of this course. So don't worry if this looks complex:

    --cacert /etc/kubernetes/pki/etcd/ca.crt     
    --cert /etc/kubernetes/pki/etcd/server.crt     
    --key /etc/kubernetes/pki/etcd/server.key


So for the commands I showed in the previous video to work you must specify the ETCDCTL API version and path to certificate files. Below is the final form:


    kubectl exec etcd-master -n kube-system -- sh -c "ETCDCTL_API
    
 ETCD for Beginners

    Take me to the Video Tutorial

In this section, we will take a quick look at introduction to ETCD for beginners.

    What is ETCD?
    What is a Key-Value Store?
    How to get started quickly with ETCD?
    How to operate ETCD?

What is a ETCD?

 - ETCD is a distributed reliable key-value store that is simple, secure & Fast.

What is a Key-Value Store

    Traditionally, databases have been in tabular format, you must have heared about SQL or Relational databases. They store data in rows and columns

    relational-dbs

    A Key-Value Store stores information in a Key and Value format.

    key-value

Install ETCD

    Its easy to install and get started with ETCD.

        Download the relevant binary for your operating system from github releases page (https://github.com/etcd-io/etcd/releases)

        For Example: To download ETCD V3.3.11, run the below curl command
          
        $ https://github.com/etcd-io/etcd/releases/download/v3.3.11/etcd-v3.3.11-linux-amd64.tar.gz

        Extract it.

        $ tar xvzf etcd-v3.3.11-linux-amd64.tar.gz 

        Run the ETCD Service

        $ ./etcd

        When you start ETCD it will by default listens on port 2379

        The default client that comes with ETCD is the etcdct client. You can use it to store and retrieve key-value pairs.

        Syntax: To Store a Key-Value pair
        $ ./etcdctl set key1 value1

        Syntax: To retrieve the stored data
        $ ./etcdctl get key1

        Syntax: To view more commands. Run etcdctl without any arguments
        $ ./etcdctl

        etcdctl

    K8s Reference Docs:
        https://kubernetes.io/docs/concepts/overview/components/
        https://etcd.io/docs/
        https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/

    
 # KUBE_API SERVER
 <img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429562-21f54326-ad31-495b-91de-f8334180d463.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429601-8e45b850-7e85-4877-8fe7-7e2d7d0557f6.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429618-b0861548-f2f5-485e-b779-cdb33d48cb3b.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429640-94ac7fdf-6bc8-4ecc-8213-f864e567e006.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429650-a454aaaf-7c18-4dcf-92c1-b452d16b5699.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429659-23337734-9aa4-449f-a4c1-543ee28b8339.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429670-ff81fd5b-6e70-4abb-b70c-2cb66269967e.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429676-2b7c4375-085d-4cd0-96b6-954891c6d92e.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429691-7c3b4a22-6813-437a-b1f3-c470d3121dd1.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429703-be45a852-8c53-41be-baaf-a7c90586dbbf.png">

# KUBE_CONTROLLER MANAGER
<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429733-d5e4c5ff-e6b2-41c8-8f51-e100e7187cde.png">
<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429770-4edab03e-8f8a-40aa-af3a-1522412b4d6e.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429784-82238c1d-3841-4a6b-a537-680ea8d2ec0d.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429795-7d211f91-ae8c-4928-a5e8-c6966365781a.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429818-6e4aa9a2-f5b1-40fa-86df-7f704c0ae526.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429831-b42ee6f7-c1ba-4e1e-813a-0b0acc0990fd.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429841-c8cb84c0-690e-47c9-a474-98b326f60453.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429850-ca44600c-85ad-4253-b550-12a646313466.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429860-95edbd7f-8508-48e6-850f-8aa13da93c61.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429869-9fc7d56c-2ad6-4fc0-8978-08742d9457f8.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429879-2a6693a2-466b-4f9e-bc9f-c81275bc35b5.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429889-1bfa6875-6a2c-455d-83e0-e922614148de.png">

# KUBE_SCHEDULER
<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429918-b02ff436-6ed0-4e7b-9cb8-38a042adf4fb.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429925-cd0e5708-810b-485d-b775-d74c3be4280e.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429941-6d758f5c-3b43-4674-a9a4-1b420cb26a23.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429961-5782e378-d018-4bef-977c-ba1657a605e1.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429978-fdcb01b6-4d18-470c-9dee-5935c46fe63e.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127429987-ca4e5857-580d-47c5-9f23-632b2f02c54d.png">
<img width="991" alt="image" src="https://user-images.githubusercontent.com/75510135/127430030-e05d6b89-d049-44e9-b27b-da803e24625a.png">


<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127430002-778ef61a-a61a-45af-b1b1-2b133efe0bc9.png">


<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127430049-8c4702d2-b4ac-4565-9fb9-ec00bf5a6c1a.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127430064-ca1b0441-2f21-48b1-be1f-b3e32a5e53f5.png">

# KUBeLET
<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127430099-9bfd6bd2-4b9f-45b1-8c9a-48ae23bc449d.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127430114-8fff1548-d8fd-41d3-b56a-64a3c0d5067a.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127430131-a4aa1cd4-6f61-4d23-9293-d74cd86f0111.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127430142-0e13e65c-2397-41a1-879e-dc95c5e34b37.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127430158-aae2c8dd-4d67-46d0-a5d2-51e5d2b38258.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127430175-3e8f268e-7510-4ff7-99a3-492246259ca9.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127430199-cc7533db-b161-4b46-9996-ef2fd5f70c36.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127430214-1bbe2c04-bda9-47fd-93da-c6918a0e6e9d.png">

<img width="1337" alt="image" src="https://user-images.githubusercontent.com/75510135/127430231-8dcf1168-410e-4857-afad-83309ebf9082.png">

# Pods


    POD introduction
    How to deploy pod?

Kubernetes doesn't deploy containers directly on the worker node.

<img width="765" alt="image" src="https://user-images.githubusercontent.com/75510135/127445216-656f8909-8115-4bd8-bf9e-370bd5c12d33.png">

<img width="641" alt="image" src="https://user-images.githubusercontent.com/75510135/127445273-d7ff4956-d0e4-45cd-b875-10759756b08c.png">

<img width="696" alt="image" src="https://user-images.githubusercontent.com/75510135/127445318-7c392b9b-ba16-4710-8174-e964ef4a7acb.png">

<img width="697" alt="image" src="https://user-images.githubusercontent.com/75510135/127445351-99ee8e92-f7cf-4bf2-9529-952c8f7f48c5.png">

- POD definition and creation in yml file

<img width="741" alt="image" src="https://user-images.githubusercontent.com/75510135/127446139-989bb454-6cf2-4fce-9fa2-b2b3086ead4f.png">

<img width="715" alt="image" src="https://user-images.githubusercontent.com/75510135/127446364-a9cf5b9c-d5db-4bec-9485-104e6e4214df.png">

- eg:

<img width="872" alt="image" src="https://user-images.githubusercontent.com/75510135/127450092-cf988c62-428c-4a99-b94b-75ab39bc57d9.png">

- cmd to run

```
 kubectl create -f pods.yml
 kubectl get pods
 kubectl describe pods myapp-pod
 kubectl describe pod podName | grep -i image
 kubectl get pods -o wide
 kubectl delete pods myapp-pod
 ```
 
- alternate way to run a pod
<img width="833" alt="image" src="https://user-images.githubusercontent.com/75510135/127456649-afcecf0f-7830-479a-a341-95f5a0c72fde.png">


* basics $ kubectl get pods -o wide
NAME    READY   STATUS    RESTARTS   AGE     IP          NODE             NOMINATED NODE   READINESS GATES
nginx   1/1     Running   0          3m25s   10.1.1.89   docker-desktop   <none>           <none>


*  to create pod yaml from runnning container
   * kubectl run redis --image=redis123 --dry-run=client -o yaml > pod.yaml
 
  
  
  
  # Replication controller / Replica Set

  take a look at the below

    Replication Controller
    ReplicaSet

  <img width="785" alt="image" src="https://user-images.githubusercontent.com/75510135/127460848-8e7a4570-4a08-4ad4-b8bd-79ab99d73c01.png">

  <img width="709" alt="image" src="https://user-images.githubusercontent.com/75510135/127460889-5198cb50-6ca6-4b27-8c60-7031947ffb0f.png">

  <img width="729" alt="image" src="https://user-images.githubusercontent.com/75510135/127460936-1ae9cde4-ffc0-4ccf-8c06-608af527c613.png">

  <img width="685" alt="image" src="https://user-images.githubusercontent.com/75510135/127460977-1f8283f7-33a4-478c-9107-3a7f97b2e94d.png">

  <img width="748" alt="image" src="https://user-images.githubusercontent.com/75510135/127461016-f2468457-0d9d-49ba-a0ad-12d9de61b03f.png">

  <img width="638" alt="image" src="https://user-images.githubusercontent.com/75510135/127461051-d72a41d4-5e73-4e4d-8968-d245a51c099f.png">

  <img width="691" alt="image" src="https://user-images.githubusercontent.com/75510135/127461095-42e16639-16aa-4e6b-961b-5b3a25df52bb.png">

  <img width="705" alt="image" src="https://user-images.githubusercontent.com/75510135/127461139-4b6492bd-4460-4c16-b6e3-f1a5c90cc439.png">

  <img width="835" alt="image" src="https://user-images.githubusercontent.com/75510135/127461179-564e4cbc-44a1-42b8-8fa2-49d84367cad9.png">

  <img width="812" alt="image" src="https://user-images.githubusercontent.com/75510135/127461256-a1661582-4bd7-4bad-8135-3799cb47cf1a.png">

  <img width="765" alt="image" src="https://user-images.githubusercontent.com/75510135/127461287-9eb800f2-17d7-4b99-af8b-ce2725073916.png">

   ```
   kubectl apply -f replica-sets.yaml
   kubectl get rc,pods
   kubetcl replace -f replica-sets.yaml
   kubectl scale --replicas=4 replicaset myapp-replicaset
   kubectl delete rc myapp-replicaset --cascade=false
    ```
    
    
    
    
  
  
  
  
  
  
  
  
  
  




















