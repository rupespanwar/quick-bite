   
    
    
    
# Deployment 
    
<img width="830" alt="image" src="https://user-images.githubusercontent.com/75510135/127484333-6e3cf97e-4d23-4598-8fe1-6e3ac8fe94c6.png">

<img width="613" alt="image" src="https://user-images.githubusercontent.com/75510135/127484367-1286cda8-31da-4de9-9080-a974bfa4b9ce.png">

<img width="601" alt="image" src="https://user-images.githubusercontent.com/75510135/127484409-bacedb5b-02bd-41d7-9151-afa206cbf3d3.png">

<img width="797" alt="image" src="https://user-images.githubusercontent.com/75510135/127484444-44b520c0-6963-476b-b2b9-5a9cb1495aab.png">

<img width="585" alt="image" src="https://user-images.githubusercontent.com/75510135/127484474-31a6ae5b-db2b-4e3d-85c2-cdbbe1b91231.png">

    
    
              kubectl apply -f basics/deploy-ments.yaml
              kubectl get all
              kubectl delete deploy nginx-deployment


  
    
    
 <img width="976" alt="image" src="https://user-images.githubusercontent.com/75510135/127485775-2f862fc7-4615-44de-9f2a-3660342f4784.png">

   
   #  NameSpace
    
    
 <img width="814" alt="image" src="https://user-images.githubusercontent.com/75510135/127487327-c3af093c-82b8-4a0c-aa95-ba5df06d2e42.png">

 <img width="807" alt="image" src="https://user-images.githubusercontent.com/75510135/127487362-c5da63ab-32e2-44ff-b9a3-21f279312481.png">

<img width="818" alt="image" src="https://user-images.githubusercontent.com/75510135/127487393-bf752476-83dc-4f7c-b637-6d7e075b343d.png">
   
<img width="790" alt="image" src="https://user-images.githubusercontent.com/75510135/127487429-6b3b2c88-1e54-4999-a2a5-772c2e277050.png">

 <img width="828" alt="image" src="https://user-images.githubusercontent.com/75510135/127487467-1bd36cc1-c360-44aa-883a-a16d9778592a.png">

<img width="753" alt="image" src="https://user-images.githubusercontent.com/75510135/127487537-336b5bf2-b0bc-4d93-8992-fb4e86c6f5fd.png">

<img width="845" alt="image" src="https://user-images.githubusercontent.com/75510135/127487565-058c1423-c393-4632-b3fb-439c276ca504.png">

<img width="833" alt="image" src="https://user-images.githubusercontent.com/75510135/127487606-2639003d-b73d-47d7-9890-1091864cf841.png">

<img width="833" alt="image" src="https://user-images.githubusercontent.com/75510135/127487636-73d423c2-3124-418d-a824-d3edad1147d6.png">

<img width="827" alt="image" src="https://user-images.githubusercontent.com/75510135/127487660-7fb52fa7-8c70-49b3-baaf-bf36acc733e5.png">

<img width="824" alt="image" src="https://user-images.githubusercontent.com/75510135/127487704-34908831-9eaa-4266-bbcf-8ca2c5e250fa.png">

<img width="803" alt="image" src="https://user-images.githubusercontent.com/75510135/127487744-4a3bf1e3-ea29-41f4-80dc-3fdc0cb0588f.png">
    
    
    
              kubectl get ns
              kubectl get pods --all-namespaces
              kubectl get pods --namespace=kube-system
              kubectl apply -f basics/name-space.yaml
              kubectl run nginx --image=nginx --namespace=dev
              kubectl apply -f basics/pod-namespace.yml
              kubectl create ns prod
              kubectl config set-context $(kubectl config current-context) --namespace=dev
              kubectl apply -f basics/resource-quota.yml
              kubectl apply -f basics/resource-quota.yml
              kubectl delete ns prod
    
  
  # Service
 <img width="866" alt="image" src="https://user-images.githubusercontent.com/75510135/127499962-819545fb-07ab-40d0-8451-73d733dde8df.png">
<img width="760" alt="image" src="https://user-images.githubusercontent.com/75510135/127500060-e5593bcf-c829-4fea-ab3c-87599c5b61de.png">

<img width="749" alt="image" src="https://user-images.githubusercontent.com/75510135/127500095-6da9bf1b-5c1e-4eca-ba34-decbeaa3b614.png">
<img width="771" alt="image" src="https://user-images.githubusercontent.com/75510135/127500190-7a7073e7-b92b-4ae3-8604-d60f2072b1b1.png">

<img width="806" alt="image" src="https://user-images.githubusercontent.com/75510135/127500245-ec43642d-5258-426f-a34b-104657a1711f.png">

<img width="752" alt="image" src="https://user-images.githubusercontent.com/75510135/127500295-a114b48c-a66b-4fcc-8494-2da76c0b7c93.png">

<img width="837" alt="image" src="https://user-images.githubusercontent.com/75510135/127500327-11805347-e0f6-48ae-a7bf-08fbb423e609.png">

<img width="849" alt="image" src="https://user-images.githubusercontent.com/75510135/127500417-7db1954b-76da-4818-be13-5d7d9a8cab0c.png">

<img width="750" alt="image" src="https://user-images.githubusercontent.com/75510135/127500462-03dab0c1-286b-4158-bdaa-67d945836329.png">

<img width="733" alt="image" src="https://user-images.githubusercontent.com/75510135/127500497-7b903345-e955-4610-99f3-c756e46b3ff5.png">

<img width="762" alt="image" src="https://user-images.githubusercontent.com/75510135/127500540-608925dd-8d06-4eda-a1ef-312d7623d691.png">

 ## Service Load-Balancer
 * in case of node port

<img width="914" alt="image" src="https://user-images.githubusercontent.com/75510135/127499430-2049abeb-8c0a-4dc1-94ce-8e4dd3fffc14.png">

* using supported native load balancer

<img width="915" alt="image" src="https://user-images.githubusercontent.com/75510135/127499690-96e9c3d2-8939-4442-9aad-d169a1a97626.png">

<img width="825" alt="image" src="https://user-images.githubusercontent.com/75510135/127500130-7b900fbc-23b4-41bb-a51c-87672d315aff.png">

# Imperative vs Declarative
<img width="833" alt="image" src="https://user-images.githubusercontent.com/75510135/127530808-b31424bb-2cc1-4841-87fc-105ce8db8785.png">

<img width="795" alt="image" src="https://user-images.githubusercontent.com/75510135/127530896-1d85781c-2496-4c56-a130-e679b8a4e837.png">
<img width="719" alt="image" src="https://user-images.githubusercontent.com/75510135/127531430-f82c5a00-2960-4298-be4e-eff6a1cc85af.png">
<img width="727" alt="image" src="https://user-images.githubusercontent.com/75510135/127531482-473131e1-79cf-4a7e-a497-ed6e2384662b.png">

<img width="798" alt="image" src="https://user-images.githubusercontent.com/75510135/127531698-9e7dc347-76d0-406f-99fb-150aad00ba5e.png">

<img width="739" alt="image" src="https://user-images.githubusercontent.com/75510135/127531956-14df35f7-989a-42c5-8abd-56950352b55f.png">

<img width="721" alt="image" src="https://user-images.githubusercontent.com/75510135/127532160-0e3ce3fe-29e1-4776-859d-1c7576dddfe0.png">

<img width="802" alt="image" src="https://user-images.githubusercontent.com/75510135/127532318-5fa3ddfd-c6d4-4a3d-a068-ab51fee0c681.png">

--dry-run: By default as soon as the command is run, the resource will be created. If you simply want to test your command , use the --dry-run=client option. This will not create the resource, instead, tell you whether the resource can be created and if your command is right.

-o yaml: This will output the resource definition in YAML format on screen.


Use the above two in combination to generate a resource definition file quickly, that you can then modify and create resources as required, instead of creating the files from scratch.

POD
Create an NGINX Pod

kubectl run nginx --image=nginx


Generate POD Manifest YAML file (-o yaml). Don't create it(--dry-run)
kubectl run nginx --image=nginx --dry-run=client -o yaml


Deployment
Create a deployment
kubectl create deployment --image=nginx nginx


Generate Deployment YAML file (-o yaml). Don't create it(--dry-run)
kubectl create deployment --image=nginx nginx --dry-run=client -o yaml


Generate Deployment with 4 Replicas
kubectl create deployment nginx --image=nginx --replicas=4


You can also scale a deployment using the kubectl scale command.
kubectl scale deployment nginx --replicas=4

Another way to do this is to save the YAML definition to a file and modify
kubectl create deployment nginx --image=nginx --dry-run=client -o yaml > nginx-deployment.yaml


You can then update the YAML file with the replicas or any other field before creating the deployment.


Service
Create a Service named redis-service of type ClusterIP to expose pod redis on port 6379

kubectl expose pod redis --port=6379 --name redis-service --dry-run=client -o yaml

(This will automatically use the pod's labels as selectors)

Or

kubectl create service clusterip redis --tcp=6379:6379 --dry-run=client -o yaml (This will not use the pods labels as selectors, instead it will assume selectors as app=redis. You cannot pass in selectors as an option. So it does not work very well if your pod has a different label set. So generate the file and modify the selectors before creating the service)


Create a Service named nginx of type NodePort to expose pod nginx's port 80 on port 30080 on the nodes:
kubectl expose pod nginx --type=NodePort --port=80 --name=nginx-service --dry-run=client -o yaml

# Apply 
<img width="806" alt="image" src="https://user-images.githubusercontent.com/75510135/127535153-c18583d9-2b98-4eb3-827e-380cf1931afa.png">
<img width="778" alt="image" src="https://user-images.githubusercontent.com/75510135/127535501-3df04002-fceb-4fde-bf5b-7b85573130b3.png">


# Scheduling
<img width="684" alt="image" src="https://user-images.githubusercontent.com/75510135/127535951-fd23019b-320a-42fc-b6ab-5c68e5bb92b1.png">

<img width="757" alt="image" src="https://user-images.githubusercontent.com/75510135/127536536-95ba7c1b-06f3-41b0-a9f3-c33ba0fb6a95.png">

<img width="692" alt="image" src="https://user-images.githubusercontent.com/75510135/127536575-ae70aafc-c93a-4d26-bdfd-5b65297d3704.png">

<img width="752" alt="image" src="https://user-images.githubusercontent.com/75510135/127536629-eca4b589-1f47-4c10-bb88-79c185ce9593.png">

<img width="744" alt="image" src="https://user-images.githubusercontent.com/75510135/127536673-ca392734-f2fb-4ccc-80d6-ece0c3543e28.png">

<img width="709" alt="image" src="https://user-images.githubusercontent.com/75510135/127536701-fbe964f8-7f94-45e9-9928-c6e153a9175c.png">

# Labels and Selectors
<img width="765" alt="image" src="https://user-images.githubusercontent.com/75510135/127580694-c9c850f7-0841-4205-9d36-a0c94dc95291.png">

<img width="710" alt="image" src="https://user-images.githubusercontent.com/75510135/127580724-aa6dbd7a-292a-491e-abab-d56d2912f837.png">

<img width="689" alt="image" src="https://user-images.githubusercontent.com/75510135/127580743-3a026ec8-1feb-4fb0-9977-7434c44f633d.png">

<img width="692" alt="image" src="https://user-images.githubusercontent.com/75510135/127580756-9a4236ff-ed17-48ca-b968-ae75516c47af.png">

<img width="696" alt="image" src="https://user-images.githubusercontent.com/75510135/127580775-a6164a7c-781d-429f-8839-d3d3ff1f5dd3.png">

<img width="606" alt="image" src="https://user-images.githubusercontent.com/75510135/127580798-0f0672cf-277d-4c2a-857c-b4689457a50b.png">

<img width="649" alt="image" src="https://user-images.githubusercontent.com/75510135/127580813-273a5f72-e440-4df3-82fb-908293d25cf8.png">

<img width="610" alt="image" src="https://user-images.githubusercontent.com/75510135/127580850-f75a8e64-e00a-46cb-834a-245dff82f720.png">

<img width="649" alt="image" src="https://user-images.githubusercontent.com/75510135/127580870-564657bb-d454-4eb1-82ae-484e0f7dc85c.png">

<img width="580" alt="image" src="https://user-images.githubusercontent.com/75510135/127580891-d161cfb1-7458-4c21-8148-2f68a6734a9f.png">

# Taints and Tolerations vs Node Affinity
<img width="813" alt="image" src="https://user-images.githubusercontent.com/75510135/127581948-a06c1fde-0d50-4298-8666-51f03aa3f221.png">

<img width="823" alt="image" src="https://user-images.githubusercontent.com/75510135/127581970-1f03c1f7-79d2-4930-8747-e59f945c713e.png">

<img width="868" alt="image" src="https://user-images.githubusercontent.com/75510135/127582022-72445a4f-e4f4-418e-a80c-a84170c428b8.png">
<img width="891" alt="image" src="https://user-images.githubusercontent.com/75510135/127582056-d3e964ec-5373-4f6b-9b1f-4604dc3b0b47.png">

<img width="752" alt="image" src="https://user-images.githubusercontent.com/75510135/127582105-2379f2df-2c8e-4c1c-8308-82e716e2c2a6.png">

<img width="705" alt="image" src="https://user-images.githubusercontent.com/75510135/127582124-2a441c9a-22b5-4a3b-bbdf-c724548cbfc2.png">

<img width="695" alt="image" src="https://user-images.githubusercontent.com/75510135/127582252-6b60a0e7-93de-4d45-93f7-e9e33e8d587c.png">

      kubectl describe nodes node01 | grep Taints
      kubectl taint nodes node01 spray=mortein:NoSchedule
      kubectl taint nodes controlplane node-role.kubernetes.io/master:NoSchedule-


     add below section to pod definition to apply taint n toleration
     tolerations:
    - key: spray
      value: mortein
      effect: NoSchedule
      operator: Equal

# Node Selectors
<img width="732" alt="image" src="https://user-images.githubusercontent.com/75510135/127592102-b8b11041-6340-4605-b6d0-05d29cb49bb2.png">

<img width="849" alt="image" src="https://user-images.githubusercontent.com/75510135/127592111-d2f5899b-6557-4ff2-b06e-d72dfadf1c2c.png">

<img width="756" alt="image" src="https://user-images.githubusercontent.com/75510135/127592127-632cf228-7434-43b6-996e-8b8647cfbd63.png">

<img width="839" alt="image" src="https://user-images.githubusercontent.com/75510135/127592149-92564a35-83e6-40e0-ad8e-12548fed20d4.png">

<img width="836" alt="image" src="https://user-images.githubusercontent.com/75510135/127592162-a0540a23-173f-4a4b-b336-3929230e2c4d.png">

# Node Affinity
<img width="767" alt="image" src="https://user-images.githubusercontent.com/75510135/127592200-b88e02c8-3810-43ad-b8cb-2c045e1d1051.png">

<img width="684" alt="image" src="https://user-images.githubusercontent.com/75510135/127592219-0d0131d9-1029-4ce9-98e5-958caa6be64a.png">

<img width="613" alt="image" src="https://user-images.githubusercontent.com/75510135/127592238-2a9096af-b175-4fc8-bbb8-b47d055ab118.png">

<img width="549" alt="image" src="https://user-images.githubusercontent.com/75510135/127592260-41d57147-c9a6-4a22-b55f-92ca86f25eec.png">

<img width="643" alt="image" src="https://user-images.githubusercontent.com/75510135/127592286-5f5fb9ba-34a0-4e59-9452-42acb9588c45.png">

<img width="571" alt="image" src="https://user-images.githubusercontent.com/75510135/127592309-5ca7310b-9071-4410-945c-f80b7068fc9e.png">

<img width="677" alt="image" src="https://user-images.githubusercontent.com/75510135/127592391-d0862994-c77c-4edf-8f22-30b08c771d7b.png">

<img width="688" alt="image" src="https://user-images.githubusercontent.com/75510135/127592413-7582a11f-729f-49d8-89c8-1311042b1e22.png">

<img width="804" alt="image" src="https://user-images.githubusercontent.com/75510135/127592431-c29f8904-0d7d-430e-873c-96cf461d263e.png">

           kubectl get nodes -o wide
           kubectl describe node node01 | grep labels
           kubectl describe node node01 | grep -i Labels
           kubectl label nodes node01 color=blue

            kubectl create deploy blue --image=nginx --replicas=3
            kubectl edit deployment blue

           append below template.spec
           affinity:
              nodeAffinity:
                requiredDuringSchedulingIgnoredDuringExecution:
                  nodeSelectorTerms:
                  - matchExpressions:
                    - key: node-role.kubernetes.io/master
                      operator: Exists

           append below template.spec          
           affinity:
             nodeAffinity:
                 requiredDuringSchedulingIgnoredDuringExecution:
                   nodeSelectorTerms:
                   - matchExpressions:
                     - key: color
                       operator: In
                       values:
                       - blue
  
  # Node Affinity vs T&T
  <img width="802" alt="image" src="https://user-images.githubusercontent.com/75510135/127594684-1000a3fe-7eba-4b5f-ab45-0d393f5898b3.png">

<img width="794" alt="image" src="https://user-images.githubusercontent.com/75510135/127594726-099352cb-4951-4c18-bb54-428f8282625b.png">

<img width="613" alt="image" src="https://user-images.githubusercontent.com/75510135/127594806-1a998092-da8a-4f16-9560-f79dc320b543.png">

<img width="759" alt="image" src="https://user-images.githubusercontent.com/75510135/127594892-a5fd2330-d8d3-4947-aeb6-2102f2008297.png">

# Resource Requirements & Limits 
  
<img width="901" alt="image" src="https://user-images.githubusercontent.com/75510135/127597422-47681fcf-f7fc-4a2d-acd9-d55efcbfd177.png">

<img width="979" alt="image" src="https://user-images.githubusercontent.com/75510135/127597435-570974e0-c014-4d7f-a15a-c9884c65f813.png">

<img width="943" alt="image" src="https://user-images.githubusercontent.com/75510135/127597448-0632e4e3-e498-45c6-80f8-a9d300570ad9.png">

<img width="822" alt="image" src="https://user-images.githubusercontent.com/75510135/127597466-27cc1288-b2a5-4010-9c21-ccc2c66e6a12.png">

<img width="692" alt="image" src="https://user-images.githubusercontent.com/75510135/127597491-cd14f09e-97ca-4500-be82-012190227868.png">

<img width="959" alt="image" src="https://user-images.githubusercontent.com/75510135/127597509-7070ccff-f31a-4943-97de-32dc17c7dd23.png">

<img width="787" alt="image" src="https://user-images.githubusercontent.com/75510135/127597523-08bf1a7e-e25a-4795-a8be-413324818674.png">

<img width="696" alt="image" src="https://user-images.githubusercontent.com/75510135/127597537-297db263-e166-49ce-97d5-aa2ad236d497.png">


            kubectl describe pod rabbit

            resources:
                  limits:
                    cpu: "1"
                    memory: 512Mi
                  requests:
                    cpu: "1"
                    memory: 512Mi

            kubectl get events | grep nginx
            kubectl describe pod nginx | grep -i image
            kubectl describe pod nginx | grep IP:
  
  
  
  # Daemon Set
  <img width="731" alt="image" src="https://user-images.githubusercontent.com/75510135/127603644-9f3742d1-a3d3-445b-a03a-603aec20bf33.png">

<img width="747" alt="image" src="https://user-images.githubusercontent.com/75510135/127603671-04e8b7e6-8676-411e-8c16-dee3858dbcd7.png">

<img width="729" alt="image" src="https://user-images.githubusercontent.com/75510135/127603696-474639f3-a992-4d68-8641-34d7d0fd4dc3.png">

<img width="746" alt="image" src="https://user-images.githubusercontent.com/75510135/127603732-e2357fed-edf4-49bd-a042-6e5ed4d5cbdc.png">

<img width="642" alt="image" src="https://user-images.githubusercontent.com/75510135/127603750-4bbe03d1-a00a-4f30-89b8-5420507f7ef6.png">

<img width="721" alt="image" src="https://user-images.githubusercontent.com/75510135/127603770-87e5525c-a0f6-43fc-890c-b14c90aa64a7.png">

<img width="714" alt="image" src="https://user-images.githubusercontent.com/75510135/127603799-e10a17d4-9aee-4883-962f-bfe7a2d66445.png">

<img width="748" alt="image" src="https://user-images.githubusercontent.com/75510135/127603823-2e587743-1b31-4523-9300-3f29dba1a18c.png">

            kubectl get daemonsets --all-namespaces
            kubectl describe daemonset kube-proxy --namespace=kube-system
            kubectl describe daemonset kube-flannel-ds-amd64 --namespace=kube-system
            kubectl get pod -n kube-system|grep elasticsearch

  
# Static PODs
<img width="795" alt="image" src="https://user-images.githubusercontent.com/75510135/127606451-1bb6f231-a4a4-451c-8e55-494bc5b763f0.png">

<img width="703" alt="image" src="https://user-images.githubusercontent.com/75510135/127606471-09805938-f0e9-4de9-a49b-a53266d5906a.png">

<img width="801" alt="image" src="https://user-images.githubusercontent.com/75510135/127606495-02077dee-cdd5-496f-9180-6c6711e4c4a6.png">
<img width="815" alt="image" src="https://user-images.githubusercontent.com/75510135/127606638-8aa10157-cbf7-4a50-a590-bb7f7c826f2b.png">

<img width="798" alt="image" src="https://user-images.githubusercontent.com/75510135/127606653-c962ef2c-40d5-4006-9a15-a322a7e1c437.png">
<img width="799" alt="image" src="https://user-images.githubusercontent.com/75510135/127606681-3f87b91a-bfb2-4030-9e72-3ecb0e94894d.png">

<img width="703" alt="image" src="https://user-images.githubusercontent.com/75510135/127606709-32b1a342-e593-435a-94ef-c9608359ad99.png">
<img width="781" alt="image" src="https://user-images.githubusercontent.com/75510135/127606728-dc4f690c-3cdf-45c9-880e-dec62f5eb630.png">
**pods with controlplane are marked as static**
            kubectl get pods --all-namespaces -o wide

            ps -aux | grep kubelet
            - identify the config file - --config=/var/lib/kubelet/config.yaml
            - /etc/kubernetes/manifests
            - image defined in the /etc/kubernetes/manifests/kube-apiserver.yaml 
            - $ kubectl run --restart=Never --image=busybox static-busybox --dry-run=client -o yaml --command -- sleep 1000 > /etc/kubernetes/manifests/static-busybox.yaml
            - Run the command with updated image tag:
            kubectl run --restart=Never --image=busybox:1.28.4 static-busybox--dry-run=client -o yaml --command -- sleep 1000 > /etc/kubernetes/manifests/static-busybox.yaml

            $ grep staticPodPath /var/lib/kubelet/config.yaml
            $ node01 $ rm -rf /etc/just-to-mess-with-you/greenbox.yaml

# Multiple Schedulers
<img width="843" alt="image" src="https://user-images.githubusercontent.com/75510135/127610307-a2740be6-64f0-4436-9def-2c9cbd41477f.png">

# Deploy additional scheduler
* Download the binary
            $ wget https://storage.googleapis.com/kubernetes-release/release/v1.12.0/bin/linux/amd64/kube-scheduler

<img width="780" alt="image" src="https://user-images.githubusercontent.com/75510135/127610427-70cfa1fa-81d1-44a4-b236-1f051b99a3e1.png">

<img width="842" alt="image" src="https://user-images.githubusercontent.com/75510135/127610455-99ac71c2-145e-4cb8-a040-db5c4b396aa7.png">

<img width="833" alt="image" src="https://user-images.githubusercontent.com/75510135/127610487-f07ca5da-b3a8-470a-9a4b-c529d17d0e45.png">

<img width="829" alt="image" src="https://user-images.githubusercontent.com/75510135/127610509-60bc8bce-f647-45fb-b014-ecd5685a7b63.png">

<img width="829" alt="image" src="https://user-images.githubusercontent.com/75510135/127610537-2b086f9e-7dff-4b72-a869-349f05bb8bf3.png">

<img width="844" alt="image" src="https://user-images.githubusercontent.com/75510135/127610577-5249016b-ab05-42fe-92d5-0253dc3b55bc.png">

         kubectl get pods --namespace=kube-system
         kubectl describe pod kube-scheduler-controlplane --namespace=kube-system
         cat /etc/kubernetes/manifests/kube-scheduler.yaml > custom-scheduler.yaml
         change name , port then create custom scheduler
         kubectl create -f custom-scheduler.yaml

         grep schedulerName /root/nginx-pod.yaml
         schedulerName: my-scheduler

         kubectl create -f /root/nginx-pod.yaml



<img width="902" alt="image" src="https://user-images.githubusercontent.com/75510135/127614581-c2cfdcf3-a2f2-452e-bd57-ef543922228a.png">

# Logging & Monitoring

    Monitor Cluster Components
    Monitor Applications
    Monitor Cluster Components Logs
    Application Logs

<img width="662" alt="image" src="https://user-images.githubusercontent.com/75510135/127615024-eae57380-a2a3-41ef-9a8c-cdc2d0def46d.png">


## Monitor Cluster Components
<img width="733" alt="image" src="https://user-images.githubusercontent.com/75510135/127618132-89870bbe-7db8-469b-b48d-dcc5c85d72d4.png">
<img width="777" alt="image" src="https://user-images.githubusercontent.com/75510135/127618195-54cf416b-1e8f-4ee6-a4fa-6b1e4a080ed8.png">
<img width="792" alt="image" src="https://user-images.githubusercontent.com/75510135/127618225-ba248762-332f-428a-99a9-0c3d90728af6.png">
<img width="663" alt="image" src="https://user-images.githubusercontent.com/75510135/127618249-daa57f0c-c425-4f84-827f-ba1ed8909cea.png">
<img width="789" alt="image" src="https://user-images.githubusercontent.com/75510135/127618287-e45a4a86-0f07-4693-84de-0c094a5c284c.png">

<img width="676" alt="image" src="https://user-images.githubusercontent.com/75510135/127618319-bc8dcbb2-c395-419e-87f6-c4924b575109.png">
<img width="638" alt="image" src="https://user-images.githubusercontent.com/75510135/127618362-aad49154-83ab-4c12-942e-2657687e1d98.png">

            git clone https://github.com/kodekloudhub/kubernetes-metrics-server.git
            kubectl create -f kubernetes-metrics-server
            kubectl top node
            kubectl top pods

# Managing Application Logs
<img width="537" alt="image" src="https://user-images.githubusercontent.com/75510135/127621862-3edadd38-eea4-4e05-be92-921933875b51.png">
<img width="548" alt="image" src="https://user-images.githubusercontent.com/75510135/127621889-fd436de9-6eb7-4ad1-ab60-56b69cfcf7b3.png">
<img width="898" alt="image" src="https://user-images.githubusercontent.com/75510135/127621934-25492df9-7d0a-4a69-8f2f-79669d199286.png">
<img width="890" alt="image" src="https://user-images.githubusercontent.com/75510135/127621969-1d3a51f7-c14e-4b98-b4fd-e29942a32405.png">















