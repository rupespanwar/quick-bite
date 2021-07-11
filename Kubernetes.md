
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

<img width="778" alt="image" src="https://user-images.githubusercontent.com/75510135/125191337-735a4b80-e25f-11eb-9162-44b6463f153b.png">

- basic terms

<img width="826" alt="image" src="https://user-images.githubusercontent.com/75510135/125191386-c16f4f00-e25f-11eb-90b4-ba534fb66ac8.png">


