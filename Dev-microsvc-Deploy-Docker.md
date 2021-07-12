# Archicture

<img width="764" alt="image" src="https://user-images.githubusercontent.com/75510135/125185833-a4795280-e244-11eb-8397-843eacadea31.png">

# Deployment issue - Approach 1
<img width="739" alt="image" src="https://user-images.githubusercontent.com/75510135/125185868-cc68b600-e244-11eb-86da-5895e9583638.png">

<img width="850" alt="image" src="https://user-images.githubusercontent.com/75510135/125185881-d4c0f100-e244-11eb-920e-d813a7f1edb6.png">

<img width="928" alt="image" src="https://user-images.githubusercontent.com/75510135/125185950-249fb800-e245-11eb-9073-d3b5c3f69ff7.png">

# Docker Deployment - Approach
<img width="787" alt="image" src="https://user-images.githubusercontent.com/75510135/125186350-9b3db500-e247-11eb-923f-a56b2bf94c88.png">

- with mulitple copy of the services
<img width="691" alt="image" src="https://user-images.githubusercontent.com/75510135/125186360-ab559480-e247-11eb-91df-9906cb55717e.png">
- why Docker
<img width="850" alt="image" src="https://user-images.githubusercontent.com/75510135/125186390-d213cb00-e247-11eb-97b9-09db7664cc8d.png">
- Kubernetes for container management
<img width="740" alt="image" src="https://user-images.githubusercontent.com/75510135/125186540-7990fd80-e248-11eb-8c58-fdd9b03d4d57.png">

<img width="708" alt="image" src="https://user-images.githubusercontent.com/75510135/125186576-ae04b980-e248-11eb-8868-b94975a1ee9a.png">

<img width="922" alt="image" src="https://user-images.githubusercontent.com/75510135/125186596-de4c5800-e248-11eb-89b0-120c7b3011ee.png">

<img width="724" alt="image" src="https://user-images.githubusercontent.com/75510135/125186602-e906ed00-e248-11eb-9a64-aa894ae5a8af.png">

<img width="691" alt="image" src="https://user-images.githubusercontent.com/75510135/125186685-6d597000-e249-11eb-9271-a184fcaafd7c.png">

# Create Dockerfile - POST service
 - create .dockerignore file to avoid copying node_moudle

<img width="428" alt="image" src="https://user-images.githubusercontent.com/75510135/125189876-f11a5900-e257-11eb-90c3-68f46f46f410.png">


<img width="492" alt="image" src="https://user-images.githubusercontent.com/75510135/125189837-c3cdab00-e257-11eb-8ac1-c440e52279f9.png">

- docker build .
<img width="570" alt="image" src="https://user-images.githubusercontent.com/75510135/125189909-1e670700-e258-11eb-9bf4-8c8efdb17eb6.png">


- run instance of above build docker image <= docker run  imageId
<img width="913" alt="image" src="https://user-images.githubusercontent.com/75510135/125189933-43f41080-e258-11eb-9b14-57be29cc3a2c.png">

<img width="726" alt="image" src="https://user-images.githubusercontent.com/75510135/125190038-cb418400-e258-11eb-84e4-613e5c975fa7.png">

<img width="965" alt="image" src="https://user-images.githubusercontent.com/75510135/125190098-12c81000-e259-11eb-93f3-84ed20c3cd61.png">

<img width="727" alt="image" src="https://user-images.githubusercontent.com/75510135/125190149-35f2bf80-e259-11eb-9fc7-bcefd5d42074.png">

- create similiar Dockerfile, .dockerignore for all the microservices 

<img width="577" alt="image" src="https://user-images.githubusercontent.com/75510135/125190533-4efc7000-e25b-11eb-971f-22858d745e62.png">

- k8s deployment

<img width="919" alt="image" src="https://user-images.githubusercontent.com/75510135/125190890-207f9480-e25d-11eb-9086-b691edaa5129.png">

<img width="924" alt="image" src="https://user-images.githubusercontent.com/75510135/125191417-fa0f2880-e25f-11eb-919e-c85ce57266e0.png">

- basic terms

<img width="826" alt="image" src="https://user-images.githubusercontent.com/75510135/125191386-c16f4f00-e25f-11eb-90b4-ba534fb66ac8.png">

- config files to create pods, svc, deployments

<img width="789" alt="image" src="https://user-images.githubusercontent.com/75510135/125191500-62f6a080-e260-11eb-93e3-abb39e097948.png">


# Create a single POD first - POSTs service
- first build docker image
 - docker build -t rupeshpanwar/posts:0.0.1 .

- docker images # to list the images
<img width="1174" alt="image" src="https://user-images.githubusercontent.com/75510135/125191987-f29d4e80-e262-11eb-994f-2e10bd6963b4.png">
- Create pod using above docker image 

<img width="616" alt="image" src="https://user-images.githubusercontent.com/75510135/125192513-e4046680-e265-11eb-9f12-e982fbbe7431.png">

# Quick reference for POD specs

<img width="806" alt="image" src="https://user-images.githubusercontent.com/75510135/125192650-94726a80-e266-11eb-8732-df155e422c22.png">
<img width="1174" alt="image" src="https://user-images.githubusercontent.com/75510135/125193028-11eaaa80-e268-11eb-90e4-cc2e4b5db72a.png">

# Common KubeCtl Cmdlets
<img width="908" alt="image" src="https://user-images.githubusercontent.com/75510135/125192884-840ebf80-e267-11eb-84a0-450044beaf0a.png">

<img width="781" alt="image" src="https://user-images.githubusercontent.com/75510135/125192932-bb7d6c00-e267-11eb-8d15-6c6bb419d94f.png">

# Create Deployment to spin up pods n manage
<img width="661" alt="image" src="https://user-images.githubusercontent.com/75510135/125193360-a0136080-e269-11eb-9ced-ec4660c32b75.png">

<img width="914" alt="image" src="https://user-images.githubusercontent.com/75510135/125193404-ecf73700-e269-11eb-849a-6437ac49ea8a.png">

<img width="713" alt="image" src="https://user-images.githubusercontent.com/75510135/125193670-401db980-e26b-11eb-9611-cba2785bd885.png">

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: posts-depl
spec:
  replicas: 1
  selector:
    matchLabels:
      app: posts
  template:
    metadata:
      labels:
        app: posts
    spec:
      containers:
        - name: posts
          image:  rupeshpanwar/posts:0.0.1
   ```
   
   <img width="868" alt="image" src="https://user-images.githubusercontent.com/75510135/125194039-23828100-e26d-11eb-9fcf-7f377903aa29.png">

<img width="903" alt="image" src="https://user-images.githubusercontent.com/75510135/125194096-680e1c80-e26d-11eb-8833-4a09131809ac.png">

# Updating the application via Deployment
<img width="878" alt="image" src="https://user-images.githubusercontent.com/75510135/125215249-7f362400-e2d8-11eb-90eb-547933731676.png">
- Approach 2
<img width="820" alt="image" src="https://user-images.githubusercontent.com/75510135/125215589-8f023800-e2d9-11eb-9a39-8becae188944.png">
- Include "*LATEST" tag with image or dont include , docker will assume automatically
<img width="581" alt="image" src="https://user-images.githubusercontent.com/75510135/125215671-b953f580-e2d9-11eb-8c07-f7fedaeee412.png">


* Step1: untag image
<img width="638" alt="image" src="https://user-images.githubusercontent.com/75510135/125216048-983fd480-e2da-11eb-940e-8f287b5eb15c.png">
* Step2: build new docker image
<img width="1225" alt="image" src="https://user-images.githubusercontent.com/75510135/125216258-392e8f80-e2db-11eb-99ad-9c8fafeda03e.png">

* Step3: push the docker image to Docker Registry

<img width="834" alt="image" src="https://user-images.githubusercontent.com/75510135/125216355-8f9bce00-e2db-11eb-90af-ceb57b64cd87.png">
* Rollout the deployment
<img width="810" alt="image" src="https://user-images.githubusercontent.com/75510135/125217160-a3483400-e2dd-11eb-89ca-35c6b6514001.png">













