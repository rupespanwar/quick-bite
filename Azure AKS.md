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
- MSSQL PV CLAIM . yaml
 <img width="730" alt="image" src="https://user-images.githubusercontent.com/75510135/125093898-6bc86480-e0f0-11eb-80bf-85b1c876cde0.png">

 <img width="697" alt="image" src="https://user-images.githubusercontent.com/75510135/125094052-8f8baa80-e0f0-11eb-998f-34ad536200b2.png">

# update FE APP.yaml with Loadbalancer service 
  <img width="662" alt="image" src="https://user-images.githubusercontent.com/75510135/125095435-c8784f00-e0f1-11eb-996a-200b698e2c14.png">

# Deploy MSSQL PV.yaml first to create disk volume n claim
  <img width="948" alt="image" src="https://user-images.githubusercontent.com/75510135/125096011-5c4a1b00-e0f2-11eb-882b-1f96cde708e1.png">

 <img width="1045" alt="image" src="https://user-images.githubusercontent.com/75510135/125096181-83a0e800-e0f2-11eb-9944-4db4ae513430.png">

  <img width="813" alt="image" src="https://user-images.githubusercontent.com/75510135/125096280-9e735c80-e0f2-11eb-91ff-ec5000b438aa.png">

 # Deploy Secret.yaml now to AKS
  <img width="962" alt="image" src="https://user-images.githubusercontent.com/75510135/125096466-cbc00a80-e0f2-11eb-833d-6a24d92b7173.png">

  <img width="1041" alt="image" src="https://user-images.githubusercontent.com/75510135/125096572-e72b1580-e0f2-11eb-9416-c1a34754be6e.png">

  # Now Deploy SQL Server.yaml to AKS
  <img width="677" alt="image" src="https://user-images.githubusercontent.com/75510135/125096745-117cd300-e0f3-11eb-97b7-a1c88f9c955f.png">
  <img width="1019" alt="image" src="https://user-images.githubusercontent.com/75510135/125096880-2e190b00-e0f3-11eb-9f57-1fbd41740081.png">

  # Now Deplay APP.yaml to AKS
  <img width="734" alt="image" src="https://user-images.githubusercontent.com/75510135/125097068-5d2f7c80-e0f3-11eb-97d6-ba13fef2dfc0.png">

  <img width="620" alt="image" src="https://user-images.githubusercontent.com/75510135/125097106-6587b780-e0f3-11eb-9cdc-f961f07bf177.png">

  <img width="1063" alt="image" src="https://user-images.githubusercontent.com/75510135/125097215-87813a00-e0f3-11eb-8351-2173df4dbc58.png">

  <img width="1035" alt="image" src="https://user-images.githubusercontent.com/75510135/125097295-9c5dcd80-e0f3-11eb-8caf-90ff2c88d469.png">

  <img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125097548-dfb83c00-e0f3-11eb-8e89-f4cebeaf9444.png">

  <img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125097575-e646b380-e0f3-11eb-9e85-3b3099f71f81.png">

  
