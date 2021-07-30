   
    
    
    
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
  
  
  
  
  






