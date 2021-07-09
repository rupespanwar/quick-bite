# Create Kubernetes Cluster
<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125068224-e2ef0000-e0d2-11eb-8205-efcd90396fce.png">

<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125068447-1d589d00-e0d3-11eb-8717-655284d48031.png">

<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125068535-36f9e480-e0d3-11eb-9ea6-75df66112885.png">

<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125068580-424d1000-e0d3-11eb-9e66-f89d690e9564.png">


<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125068658-598bfd80-e0d3-11eb-8016-235c43f0a9bb.png">

- Dashboard
<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125068860-9526c780-e0d3-11eb-8536-be0a6f326d27.png">

- Install & Connect to AKS via kubectl
<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125069061-e040da80-e0d3-11eb-8d59-2e1b9c521248.png">

# Template
az aks get-credentials --resource-group <Resource-Group-Name> --name <Cluster-Name>
  
 -  To launch dashboard                                                                               
<img width="1047" alt="image" src="https://user-images.githubusercontent.com/75510135/125069774-d075c600-e0d4-11eb-92ce-0ecadc06a27a.png">

  <img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125069891-fd29dd80-e0d4-11eb-8d88-9c1848d70085.png">

 - List Kubernetes Worker Nodes
    1. kubectl get nodes 
    2. kubectl get nodes -o wide
  
# Create Azure Disk for Persistent Valume
  <img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125093678-2b68e680-e0f0-11eb-887e-84597a07945f.png">
