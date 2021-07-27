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

# Create Client-deployment.yml
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
# Create Client-Cluster-IP-Service
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

# Create deployment for Server
<img width="1133" alt="image" src="https://user-images.githubusercontent.com/75510135/127095550-9ce00b33-215f-4b34-81cc-31ffad106f0d.png">

<img width="883" alt="image" src="https://user-images.githubusercontent.com/75510135/127096324-e26f6089-47d0-43fd-b289-e0b4bb0175db.png">



