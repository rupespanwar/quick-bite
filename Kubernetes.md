
<img width="791" alt="image" src="https://user-images.githubusercontent.com/75510135/125190598-9a168300-e25b-11eb-8530-0c307ba47d39.png">

<img width="908" alt="image" src="https://user-images.githubusercontent.com/75510135/125190620-b0bcda00-e25b-11eb-8208-9e4f060c8d9f.png">

- Enable K8S via Docker

<img width="1238" alt="image" src="https://user-images.githubusercontent.com/75510135/125190656-d4802000-e25b-11eb-8d44-f8981eddac45.png">

- minikube
<img width="930" alt="image" src="https://user-images.githubusercontent.com/75510135/125190744-4a848700-e25c-11eb-9406-bd04e3f44735.png">

IMPORTANT Note for Minikube and MicroK8s Users
Minikube Users

Recent versions of Minikube will use the docker driver by default when you run minikube start. On Windows or macOS, the docker driver is not compatible with an ingress, which we will be using throughout the course.

https://minikube.sigs.k8s.io/docs/drivers/docker/#known-issues

https://github.com/kubernetes/minikube/issues/7332

To avoid this issue, you can pass the --driver flag with a specific driver or --vm=true

macOS

minikube start --vm=true

minikube start --driver=hyperkit

minikube start --driver=virtualbox

Windows:

minikube start --vm=true

minikube start --driver=hyperv

minikube start --driver=virtualbox
MicroK8s Users

This course does not support the use of MicroK8s and will likely not work in the way that is presented. We highly suggest the use of Docker Desktop for macOS and Windows users 
and Minikube for Linux users. If you choose to use MicroK8s you will need to do your own research and refactoring to resolve the issues that may arise.
<img width="919" alt="image" src="https://user-images.githubusercontent.com/75510135/125190890-207f9480-e25d-11eb-9086-b691edaa5129.png">

<img width="924" alt="image" src="https://user-images.githubusercontent.com/75510135/125191417-fa0f2880-e25f-11eb-919e-c85ce57266e0.png">

- basic terms

<img width="826" alt="image" src="https://user-images.githubusercontent.com/75510135/125191386-c16f4f00-e25f-11eb-90b4-ba534fb66ac8.png">

- config files to create pods, svc, deployments

<img width="789" alt="image" src="https://user-images.githubusercontent.com/75510135/125191497-5ffbb000-e260-11eb-98b1-d158c7a799c5.png">

- create n log pod using custom docker image
<img width="616" alt="image" src="https://user-images.githubusercontent.com/75510135/125192503-d7800e00-e265-11eb-82e4-a70f3f31f32a.png">


ErrImagePull, ErrImageNeverPull and ImagePullBackoff Errors

If your pods are showing ErrImagePull, ErrImageNeverPull, or ImagePullBackOff errors after running kubectl apply, the simplest solution is to provide an imagePullPolicy to the pod.

First, run kubectl delete -f infra/k8s/

Then, update your pod manifest:

    spec:
      containers:
        - name: posts
          image: cygnet/posts:0.0.1
          imagePullPolicy: Never

Then, run kubectl apply -f infra/k8s/

This will ensure that Kubernetes will use the image built locally from your image cache instead of attempting to pull from a registry.

Minikube Users:

If you are using a vm driver, you will need to tell Kubernetes to use the Docker daemon running inside of the single node cluster instead of the host.

Run the following command:

eval $(minikube docker-env)

Note - This command will need to be repeated anytime you close and restart the terminal session.

Afterward, you can build your image:

docker build -t USERNAME/REPO .

Update, your pod manifest as shown above and then run:

kubectl apply -f infra/k8s/

https://minikube.sigs.k8s.io/docs/commands/docker-env/

# Quick note for POD yaml 
<img width="842" alt="image" src="https://user-images.githubusercontent.com/75510135/125192619-6ee56100-e266-11eb-805b-48a578dac6f7.png">
<img width="1174" alt="image" src="https://user-images.githubusercontent.com/75510135/125193017-0b5c3300-e268-11eb-8d4a-fe5bc906a9f8.png">

# Deployment - to create POD n manage, 2 purpose
<img width="661" alt="image" src="https://user-images.githubusercontent.com/75510135/125193349-95f16200-e269-11eb-9631-43bcdae39bce.png">

<img width="914" alt="image" src="https://user-images.githubusercontent.com/75510135/125193397-e1a40b80-e269-11eb-9e32-ebd0fa9d9efb.png">



# Common KubeCtl Cmdlets
<img width="908" alt="image" src="https://user-images.githubusercontent.com/75510135/125192879-8244fc00-e267-11eb-8519-0620e357ff89.png">

<img width="781" alt="image" src="https://user-images.githubusercontent.com/75510135/125192930-b91b1200-e267-11eb-9379-e2b887aebde5.png">


# Create Deployment to spin up pods n manage
<img width="661" alt="image" src="https://user-images.githubusercontent.com/75510135/125193360-a0136080-e269-11eb-9ced-ec4660c32b75.png">

<img width="914" alt="image" src="https://user-images.githubusercontent.com/75510135/125193404-ecf73700-e269-11eb-849a-6437ac49ea8a.png">

<img width="713" alt="image" src="https://user-images.githubusercontent.com/75510135/125193670-401db980-e26b-11eb-9611-cba2785bd885.png">

<img width="868" alt="image" src="https://user-images.githubusercontent.com/75510135/125194052-339a6080-e26d-11eb-82b0-327f4aea39d1.png">

<img width="903" alt="image" src="https://user-images.githubusercontent.com/75510135/125194090-62b0d200-e26d-11eb-86a4-afc718c926e8.png">

# Updating the application via Deployment
- Approach 1
<img width="878" alt="image" src="https://user-images.githubusercontent.com/75510135/125215241-76455280-e2d8-11eb-8527-c4e2b3ad627a.png">

- Approach 2
<img width="820" alt="image" src="https://user-images.githubusercontent.com/75510135/125215562-83167600-e2d9-11eb-98f2-3b7a8a925544.png"
- include "LATEST" tag with image or dont include , docker will assume to pick the latest
     <img width="581" alt="image" src="https://user-images.githubusercontent.com/75510135/125215628-a7725280-e2d9-11eb-9dc7-08c5044a1533.png">

 # Service - Networking
 <img width="737" alt="image" src="https://user-images.githubusercontent.com/75510135/125217529-7f392280-e2de-11eb-942f-40c7e5984079.png">

<img width="685" alt="image" src="https://user-images.githubusercontent.com/75510135/125217695-e9ea5e00-e2de-11eb-935a-c41dc94222f6.png">

<img width="702" alt="image" src="https://user-images.githubusercontent.com/75510135/125217714-f40c5c80-e2de-11eb-9a4b-6fb1a59b1fce.png">

<img width="739" alt="image" src="https://user-images.githubusercontent.com/75510135/125217819-39c92500-e2df-11eb-8bc0-6b4713c86000.png">

<img width="481" alt="image" src="https://user-images.githubusercontent.com/75510135/125217882-5feec500-e2df-11eb-86ab-af2ac9ebfebf.png">

# Port exposed via Service

<img width="923" alt="image" src="https://user-images.githubusercontent.com/75510135/125233650-a999d880-e2fc-11eb-9ef3-b3bf348f6f5e.png">

<img width="563" alt="image" src="https://user-images.githubusercontent.com/75510135/125234011-655b0800-e2fd-11eb-928a-24efdc558866.png">

- note down NodePort # 30XXXX
<img width="922" alt="image" src="https://user-images.githubusercontent.com/75510135/125234211-db5f6f00-e2fd-11eb-93b5-8031f7dda659.png">
<img width="924" alt="image" src="https://user-images.githubusercontent.com/75510135/125234382-3a24e880-e2fe-11eb-824b-7ab1e705e62e.png">

<img width="794" alt="image" src="https://user-images.githubusercontent.com/75510135/125234416-5032a900-e2fe-11eb-8896-e3f0f7fd3822.png">

<img width="678" alt="image" src="https://user-images.githubusercontent.com/75510135/125236130-157e4000-e301-11eb-868d-88591e75b43a.png">

<img width="709" alt="image" src="https://user-images.githubusercontent.com/75510135/125237487-642cd980-e303-11eb-9d40-0b3e409b73c5.png">

<img width="892" alt="image" src="https://user-images.githubusercontent.com/75510135/125239496-5cbaff80-e306-11eb-8bd9-f153c466b945.png">

<img width="786" alt="image" src="https://user-images.githubusercontent.com/75510135/125242859-dead2780-e30a-11eb-8ed1-b41451fc1029.png">



# Bring React app to container

<img width="919" alt="image" src="https://user-images.githubusercontent.com/75510135/125326839-1d210180-e360-11eb-8e26-8ea13734b000.png">

<img width="938" alt="image" src="https://user-images.githubusercontent.com/75510135/125327021-4c377300-e360-11eb-930b-6c2e51544bce.png">

<img width="932" alt="image" src="https://user-images.githubusercontent.com/75510135/125327157-6d985f00-e360-11eb-961b-7fb9782659d1.png">

<img width="924" alt="image" src="https://user-images.githubusercontent.com/75510135/125327284-90c30e80-e360-11eb-9251-45290c6d3fbe.png">


<img width="799" alt="image" src="https://user-images.githubusercontent.com/75510135/125328339-d6340b80-e361-11eb-847e-bca54375ac77.png">

<img width="891" alt="image" src="https://user-images.githubusercontent.com/75510135/125328594-24490f00-e362-11eb-9e64-0b28e3dbd284.png">

Update on Ingress Nginx Mandatory Commands

In the upcoming lecture, we will be installing Ingress Nginx. In the video, it is shown that there is a required mandatory command that needed to be run for all providers. This has since been removed, so, the provider-specific commands (Docker Desktop, Minikube, etc) are all that is required.

https://kubernetes.github.io/ingress-nginx/deploy/#provider-specific-steps


# Ingress controller
Update on Ingress Nginx Mandatory Commands

In the upcoming lecture, we will be installing Ingress Nginx. In the video, it is shown that there is a required mandatory command that needed to be run for all providers. This has since been removed, so, the provider-specific commands (Docker Desktop, Minikube, etc) are all that is required.

https://kubernetes.github.io/ingress-nginx/deploy/#provider-specific-steps

# Load balancer
<img width="907" alt="image" src="https://user-images.githubusercontent.com/75510135/125389130-59834a80-e3be-11eb-85df-0dc38c11821b.png">
<img width="610" alt="image" src="https://user-images.githubusercontent.com/75510135/125389203-77e94600-e3be-11eb-8d79-f090e84a6ad7.png">

<img width="662" alt="image" src="https://user-images.githubusercontent.com/75510135/125389312-a404c700-e3be-11eb-8b07-8939a7060126.png">

<img width="841" alt="image" src="https://user-images.githubusercontent.com/75510135/125389390-c1d22c00-e3be-11eb-930a-150e8c254372.png">

- installation of ingnx https://kubernetes.github.io/ingress-nginx/deploy/

Ingress - networking.k8s.io/v1beta1 Ingress is deprecated

When running kubectl apply in the upcoming lecture you may encounter a warning about the v1beta1 API version that is being used:

Warning: networking.k8s.io/v1beta1 Ingress is deprecated in v1.19+, unavailable in v1.22+; use networking.k8s.io/v1 Ingress

To be clear, any changes to the Ingress will be optional and this API will be supported until Kubernetes v1.22. If you are currently experiencing any errors or issues with your Ingress this warning is not the cause of it.

If you wish to update to the v1 API, only a few very minor changes are needed:

https://kubernetes.io/docs/concepts/services-networking/ingress/

Notably, a pathType needs to be added, and how we specify the backend service name and port has changed:
```
    apiVersion: networking.k8s.io/v1
    kind: Ingress
    metadata:
      name: ingress-srv
      annotations:
        kubernetes.io/ingress.class: nginx
    spec:
      rules:
        - host: posts.com
          http:
            paths:
              - path: /posts
                pathType: Prefix
                backend:
                  service:
                    name: posts-clusterip-srv
                    port:
                      number: 4000
```

While the old API is still supported we will include a separate v1 Ingress file attached to each appropriate lecture that students can refer to.
# Writing ingress config file
<img width="879" alt="image" src="https://user-images.githubusercontent.com/75510135/125398401-e503d800-e3cc-11eb-9ce7-b9f17d8ca430.png">

<img width="949" alt="image" src="https://user-images.githubusercontent.com/75510135/125399709-9a835b00-e3ce-11eb-95fe-89e239b9741d.png">

Important Note About Port 80

In the upcoming lecture, we will be editing our hosts file so that we can access posts.com/posts in our browser. If you are unable to access the application you may have something already running on port 80, which is the default port for the ingress.

You'll need to identify what is using this port and shut it down. Some students have even had applications from other courses or personal projects still running. For Windows Pro users, both SQL Server Reporting Services (MSSQLSERVER) and the World Wide Web Publishing Service / IIS Server have been the most common services causing a conflict.

To determine what might be using this port, run:

macOS / Linux

sudo lsof -i tcp:80

Windows:

netstat -aon | findstr :80

Minikube users on Windows and macOS should make sure that they aren't using the docker driver which is not compatible with an ingress as noted here:

https://www.udemy.com/course/microservices-with-node-js-and-react/learn/lecture/23145358#questions

<img width="878" alt="image" src="https://user-images.githubusercontent.com/75510135/125400136-2b5a3680-e3cf-11eb-9de4-9639e2694025.png">

<img width="870" alt="image" src="https://user-images.githubusercontent.com/75510135/125400206-42008d80-e3cf-11eb-82ba-b4d5c072b583.png">

<img width="475" alt="image" src="https://user-images.githubusercontent.com/75510135/125404176-f8667180-e3d3-11eb-9fa9-e301c9217fdf.png">


# Routes for different application components
<img width="579" alt="image" src="https://user-images.githubusercontent.com/75510135/125412558-a8d87380-e3dc-11eb-8298-d95c280c2e41.png">

# final routing config
<img width="650" alt="image" src="https://user-images.githubusercontent.com/75510135/125416068-0d35bb28-d535-4170-8254-08cde1cbb898.png">

<img width="761" alt="image" src="https://user-images.githubusercontent.com/75510135/125416465-91cd0e57-8181-43b0-ae64-048c25741741.png">


# Skaffold
<img width="691" alt="image" src="https://user-images.githubusercontent.com/75510135/125419339-e62b96af-e5ef-4af6-a33a-bca76f3c4a86.png">
<img width="1014" alt="image" src="https://user-images.githubusercontent.com/75510135/125419598-2849c477-dc3e-4f95-a2c8-a77156f45818.png">



















