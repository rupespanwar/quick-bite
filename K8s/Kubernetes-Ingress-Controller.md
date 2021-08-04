# Serve the request
- By exposing service via LoadBalancer (type)
- This will create Public IP for each of the service
- To configure DNS for the application
- Routing = >         INGRESS Req => LB => Service
- Ingress is an add-on installation , K8s provide api interface only but not ingress controller

<img width="941" alt="image" src="https://user-images.githubusercontent.com/75510135/125153989-2f8b1780-e175-11eb-87dc-dc125d3b36fd.png">

# Sample App
- https://github.com/rupeshpanwar/kubernetes-ingress-tls-ssl-https

# Create a namespace for the apps
kubectl apply -f app-namespace.yaml

# Deploy the 2 sample apps into Kubernetes
kubectl apply -f app1-deploy-svc.yaml 
kubectl apply -f app2-deploy-svc.yaml

# Get the 2 public IP addresses 
kubectl get services --namespace app
<img width="1213" alt="image" src="https://user-images.githubusercontent.com/75510135/125154168-61e94480-e176-11eb-918f-f51d2f0b9ebc.png">

# Add the Helm chart for Nginx Ingress
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update

# Install the Helm (v3) chart for nginx ingress controller
# (If using Bash instead of Powershell, replace ` with \)
helm install app-ingress ingress-nginx/ingress-nginx `
     --namespace ingress `
     --create-namespace `
     --set controller.replicaCount=2 `
     --set controller.nodeSelector."beta\.kubernetes\.io/os"=linux `
     --set defaultBackend.nodeSelector."beta\.kubernetes\.io/os"=linux

# Get the Ingress Controller public IP address
kubectl get services --namespace ingress

# Update the service type to ClusterIP instead of LoadBalancer 
# in app-deploy.yaml file
<img width="1213" alt="image" src="https://user-images.githubusercontent.com/75510135/125154292-f05dc600-e176-11eb-8ebc-150eb556d3a1.png">

<img width="1213" alt="image" src="https://user-images.githubusercontent.com/75510135/125154298-f94e9780-e176-11eb-834e-c8442dcdfb11.png">

# Delete and redeploy the service for the update to take effect
kubectl delete -f app1-deploy-svc.yaml 
kubectl delete -f app2-deploy-svc.yaml
kubectl apply -f app1-deploy-svc.yaml 
kubectl apply -f app2-deploy-svc.yaml

# Install Ingress controller
<img width="1213" alt="image" src="https://user-images.githubusercontent.com/75510135/125154427-a32e2400-e177-11eb-9758-8d371421cc5a.png">

<img width="1213" alt="image" src="https://user-images.githubusercontent.com/75510135/125154550-1899f480-e178-11eb-8193-f29188f8177a.png">

<img width="1213" alt="image" src="https://user-images.githubusercontent.com/75510135/125154562-28193d80-e178-11eb-80f2-e7df09160554.png">

# Deploy the Ingress resource into Kubernetes
kubectl apply -f app-ingress.yaml 
<img width="1213" alt="image" src="https://user-images.githubusercontent.com/75510135/125154598-5bf46300-e178-11eb-8de7-a371b357de7f.png">
<img width="1213" alt="image" src="https://user-images.githubusercontent.com/75510135/125154612-71698d00-e178-11eb-96e6-d157397b9d8c.png">


# Configure HTTPS n TLS
<img width="1213" alt="image" src="https://user-images.githubusercontent.com/75510135/125154824-a0ccc980-e179-11eb-971f-41338011965d.png">

# Create a namespace for Cert Manager
kubectl create namespace cert-manager

# Get the Helm Chart for Cert Manager
helm repo add jetstack https://charts.jetstack.io
helm repo update

# Install Cert Manager using Helm charts
helm install cert-manager jetstack/cert-manager `
    --namespace cert-manager `
    --version v0.14.0 `
    --set installCRDs=true

# Check the created Pods
kubectl get pods --namespace cert-manager

- configure ssl-tls-cluster-issuer.

<img width="463" alt="image" src="https://user-images.githubusercontent.com/75510135/125155014-b7bfeb80-e17a-11eb-97b6-79bb06529324.png">

# Install the Cluster Issuer
kubectl apply --namespace app -f ssl-tls-cluster-issuer.yaml

# Install the Ingress resource configured with TLS/SSL
kubectl apply --namespace app -f ssl-tls-ingress.yaml

<img width="606" alt="image" src="https://user-images.githubusercontent.com/75510135/125155063-1a18ec00-e17b-11eb-8eef-73168659f490.png">

<img width="824" alt="image" src="https://user-images.githubusercontent.com/75510135/125155117-62d0a500-e17b-11eb-9c4d-c369a11caf38.png">

# Verify that the certificate was issued
kubectl describe cert app-web-cert --namespace app

# Check the services
kubectl get services -n app

# Now test the app with HTTPS: https://frontend.<ip-address>.nip.io

# Cleanup resources
helm delete cert-manager --namespace cert-manager
kubectl delete namespace cert-manager
kubectl delete --namespace app -f ssl-tls-cluster-issuer.yaml
kubectl delete --namespace app -f ssl-tls-ingress.yaml

  
  
