# App over view
<img width="1133" alt="image" src="https://user-images.githubusercontent.com/75510135/127075146-b9651580-4574-4cae-9b68-4939c2ecb68a.png">

<img width="1133" alt="image" src="https://user-images.githubusercontent.com/75510135/127075159-38cfcef7-7bd3-47e1-bd1d-037e96008ecc.png">

- Path to deploy 

<img width="1133" alt="image" src="https://user-images.githubusercontent.com/75510135/127075330-d550041a-1ea1-401d-9ec5-a97d1b09e112.png">

# Github code reference
https://github.com/rupeshpanwar/k8s-react-prod-deployment

<img width="1133" alt="image" src="https://user-images.githubusercontent.com/75510135/127080934-20beb397-4a1f-4b2e-870d-ea7cd098a999.png">

- push to git 
```
echo "# k8s-react-prod-deployment" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/rupeshpanwar/k8s-react-prod-deployment.git
git push -u origin main
```

# test using docker compose if application can run on local
- first time use docker-compose up --build [to pull in image and in case of any issue ]
- next time onwards , docker-compose up
<img width="808" alt="image" src="https://user-images.githubusercontent.com/75510135/127081204-4c2c24c7-adb9-4f19-8300-b26d46cf8636.png">
<img width="808" alt="image" src="https://user-images.githubusercontent.com/75510135/127081928-bfb34d05-9323-47d0-a8f4-92eafb9443f6.png">

<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/127081996-80d5e396-c949-4d21-86d9-15dca9782a15.png">

- once testing is complete , down the application,

<img width="808" alt="image" src="https://user-images.githubusercontent.com/75510135/127082749-51f110b5-8c77-4672-9a24-1482d93189b3.png">

# Create deployment for client
<img width="883" alt="image" src="https://user-images.githubusercontent.com/75510135/127093012-d2361bc6-adca-43bf-b353-dd9147b92af3.png">
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: client-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: web
  template:
    metadata:
      labels:
        app: web
    spec:
      containers:
      - name: client
        image: rupeshpanwar/multi-client
        resources:
          limits:
            memory: "128Mi"
            cpu: "500m"
        ports:
        - containerPort: 3000

```
# Create service for client
<img width="883" alt="image" src="https://user-images.githubusercontent.com/75510135/127094688-b0feb8fb-eb69-4759-999e-0ff84f4984ab.png">
```
apiVersion: v1
kind: Service
metadata:
  name: client-cluster-ip-service
spec:
  type: ClusterIP
  selector:
    app: web
  ports:
  - port: 3000
    targetPort: 3000
```

- create deployment & service [test to check if you are able to deploy or not]

<img width="808" alt="image" src="https://user-images.githubusercontent.com/75510135/127094869-96466325-902e-418c-816f-a9265aab3f88.png">

- Note # to delete the deployment 
<img width="808" alt="image" src="https://user-images.githubusercontent.com/75510135/127095142-1b0fa68d-b237-4fb8-b7e7-1fc7432cf45b.png">

# Create deployment/service for Server
<img width="1133" alt="image" src="https://user-images.githubusercontent.com/75510135/127095550-9ce00b33-215f-4b34-81cc-31ffad106f0d.png">

<img width="883" alt="image" src="https://user-images.githubusercontent.com/75510135/127096324-e26f6089-47d0-43fd-b289-e0b4bb0175db.png">

- create ClusterIP service for server

<img width="883" alt="image" src="https://user-images.githubusercontent.com/75510135/127100148-15c5807c-993f-407c-a175-b59690e72690.png">

# Create deployment for worker
<img width="883" alt="image" src="https://user-images.githubusercontent.com/75510135/127101719-4bb8bce2-c6fa-4590-ba68-8c3016fcd4fb.png">


# Create deployment / service for Redis
<img width="883" alt="image" src="https://user-images.githubusercontent.com/75510135/127104182-966762c2-29af-4f9f-9b0c-4ca109dfe948.png">

<img width="883" alt="image" src="https://user-images.githubusercontent.com/75510135/127104355-6fd43f46-860b-4513-9a3f-f60e12909ef6.png">

# Create deployment/service for Postgres
<img width="883" alt="image" src="https://user-images.githubusercontent.com/75510135/127105584-7967ddb1-d259-40fe-b487-99ae85c3fd6f.png">

<img width="883" alt="image" src="https://user-images.githubusercontent.com/75510135/127105891-4e2080c3-840f-4f92-8375-6ba4c64ea477.png">

<img width="883" alt="image" src="https://user-images.githubusercontent.com/75510135/127106134-c7e869ea-bda5-4d72-aaa1-fdbb5b4842d4.png">

<img width="1133" alt="image" src="https://user-images.githubusercontent.com/75510135/127111547-6c8b971a-75b3-4033-83fc-342619c4f4ff.png">
<img width="1133" alt="image" src="https://user-images.githubusercontent.com/75510135/127112635-f06fa7e7-920d-4254-be45-5ac1065007f2.png">

<img width="1133" alt="image" src="https://user-images.githubusercontent.com/75510135/127113000-f4a050ad-7414-40ec-85a0-5f9a75828b42.png">

- create PVC( like advertisement)

<img width="883" alt="image" src="https://user-images.githubusercontent.com/75510135/127116907-a8d3ae96-0b5c-4ce8-bb96-7966030830cb.png">
- now mount volume(claiming the volumne defined above)

<img width="683" alt="image" src="https://user-images.githubusercontent.com/75510135/127134873-28279de2-3ba6-41aa-a10e-8e5934a620b1.png">
- kubectl get pv
- kubectl get pvc

# Setup Env vars
<img width="1133" alt="image" src="https://user-images.githubusercontent.com/75510135/127137867-3d775f6a-a951-4600-b5ce-c48ac91b9bb9.png">
- via cluster IP service

<img width="1133" alt="image" src="https://user-images.githubusercontent.com/75510135/127138043-e05d8af0-bcc3-4425-8899-38605b28a70b.png">
- for worker 

<img width="683" alt="image" src="https://user-images.githubusercontent.com/75510135/127138988-98db1bd3-72f0-488d-bea0-23f9726c75d7.png">

- for server

<img width="683" alt="image" src="https://user-images.githubusercontent.com/75510135/127139689-0a63ed8d-89d1-4f5d-ac23-f2b0511c4d20.png">

- secret (to store DB password)

<img width="1133" alt="image" src="https://user-images.githubusercontent.com/75510135/127140376-4c6c43b0-06b8-4316-b374-deb67458e3d7.png">

<img width="808" alt="image" src="https://user-images.githubusercontent.com/75510135/127141595-f14ddd63-c6a5-4aae-8ac9-c46cb10922ee.png">

- update postgres password in server deployment

<img width="683" alt="image" src="https://user-images.githubusercontent.com/75510135/127142625-28d59e40-b3d8-4c5e-b857-0863a6714695.png">

- update postgres password in postgres deployment

<img width="696" alt="image" src="https://user-images.githubusercontent.com/75510135/127144621-2e33bcda-33e2-45d0-ae99-5fc2886ef02c.png">

# Deploy above config
- kubectl apply -f k8s
<img width="808" alt="image" src="https://user-images.githubusercontent.com/75510135/127145170-fc813042-434e-46ca-9c3d-67700d931099.png">

<img width="808" alt="image" src="https://user-images.githubusercontent.com/75510135/127145417-afb43ac3-121c-4510-a272-1161fbf2be4a.png">


# Setup Ingress Networking
<img width="1039" alt="image" src="https://user-images.githubusercontent.com/75510135/127167993-8348a5c8-3e6b-4ede-b228-c8c8e2d4a3e5.png">
- https://kubernetes.github.io/ingress-nginx/deploy/#provider-specific-steps
<img width="1039" alt="image" src="https://user-images.githubusercontent.com/75510135/127172535-cdb526fc-731f-449d-b218-d942a46dc9a2.png">

- verify installation

kubectl get pods -n ingress-nginx \
  -l app.kubernetes.io/name=ingress-nginx --watch
  
- create routing rule for 

<img width="1180" alt="image" src="https://user-images.githubusercontent.com/75510135/127198538-dfad60b6-7ed7-4143-856c-a5b8b2eba2d5.png">

<img width="696" alt="image" src="https://user-images.githubusercontent.com/75510135/127200415-4d085b9f-4734-424b-916f-25e5a03ba99e.png">

# Apply the config 
- kubectl apply -f k8s

