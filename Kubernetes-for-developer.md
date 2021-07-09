# Kubernetes Cluster

<img width="1041" alt="image" src="https://user-images.githubusercontent.com/75510135/124960299-cbb00400-e039-11eb-95ee-ae499916fb2e.png">

# Application perspective 
<img width="962" alt="image" src="https://user-images.githubusercontent.com/75510135/124960518-0a45be80-e03a-11eb-8711-72f7ecac08c2.png">

<img width="961" alt="image" src="https://user-images.githubusercontent.com/75510135/124962887-c6a08400-e03c-11eb-8bee-790e7bf4ff4b.png">

# Docker file for MVC App
<img width="675" alt="image" src="https://user-images.githubusercontent.com/75510135/124965755-1a609c80-e040-11eb-9d21-fc42a373c55e.png">

<img width="749" alt="image" src="https://user-images.githubusercontent.com/75510135/124965953-4ed45880-e040-11eb-8386-fece48db9e0d.png">

# Setup kubernetes
<img width="1031" alt="image" src="https://user-images.githubusercontent.com/75510135/125042569-9ba74600-e0b7-11eb-94dc-a6389d5241c6.png">

- minikube start
- minikube dashboard

<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125043457-91d21280-e0b8-11eb-8486-f55d1cb5ea2c.png">

<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125043673-cc3baf80-e0b8-11eb-90c9-fbc83e29859c.png">

<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125044111-45d39d80-e0b9-11eb-9ab1-187768ca8b19.png">

# Run image into kubernetes
<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125046865-08244400-e0bc-11eb-85da-5e4627311c3d.png">

- kubctl apply -f yamlfile
- kubctl get pods svc deploy

# Expose to Service(nodeport)
<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125047920-0eff8680-e0bd-11eb-896f-2553dd5e18a8.png">

# Deploy MS SQL Server on Kubernetes
<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125054861-46bdfc80-e0c4-11eb-8e5e-d636cb011676.png">

<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125055576-f7c49700-e0c4-11eb-97cc-70379928c2c2.png">

<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125056078-80dbce00-e0c5-11eb-8966-16880a02c060.png">
<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125056205-9fda6000-e0c5-11eb-8a55-26000174cd17.png">

<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125056142-8e915380-e0c5-11eb-92bd-115de4883ed0.png">

# Env Var for SQL Server Connection String
- original
<img width="678" alt="image" src="https://user-images.githubusercontent.com/75510135/125059606-1f1d6300-e0c9-11eb-976b-77302f0575ca.png">
- replaced
<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125059438-f39a7880-e0c8-11eb-8bfc-ec6473714ea9.png">

# Persistent Value & claim
<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125060066-99e67e00-e0c9-11eb-894f-269146cb02d6.png">

<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125060192-b8e51000-e0c9-11eb-8e07-d842263f5eb3.png">

* kubectl apply -f mssql-pv.yaml
* kubect get pv

* add the spec into SQL Server Deployment manifest file
<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/125060407-fa75bb00-e0c9-11eb-990b-334150042b30.png">

* deploy SQL Server manifest again 
* kubectl apply -f sqlserver.yaml






