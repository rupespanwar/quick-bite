   
    
    
    
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


  
  
  
  
  
  
  
  






