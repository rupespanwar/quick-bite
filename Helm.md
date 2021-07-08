# Installing Virtualbox & Minikube  
  - Download VirtualBox: https://www.virtualbox.org/wiki/Downloads

  - Install MiniKube: https://kubernetes.io/docs/tasks/tools/install-minikube
    cmd > minikube start
        
# VSCode Tools to install
  - Keubernetes(Microsoft)
  - Kubernetes Support(Ipedrazas)
  - YAML(Red-Hat)
  - Non-breaking space highlighter(Viktor)

# Helm installation
- https://helm.sh/docs/intro/install/

- https://github.com/helm/helm/releases

![image](https://user-images.githubusercontent.com/75510135/124866420-05512280-dfda-11eb-98b3-7d2398a07801.png)

 cmd > helm version

# Cmdlets
![image](https://user-images.githubusercontent.com/75510135/124867475-ccb24880-dfdb-11eb-8400-9afcba983100.png)

![image](https://user-images.githubusercontent.com/75510135/124867541-ea7fad80-dfdb-11eb-8936-23dd29e92674.png)

cmd > kubctl get deployments/deploy
    > kubctl get svc
    > minikube ip
    > helm list
    > helm unintsall chartname
    
# Challenge
![image](https://user-images.githubusercontent.com/75510135/124867916-9d500b80-dfdc-11eb-91eb-85e85387dda9.png)
```
cmd> helm create challenge # to create the chart
   Note # template folder > keep service.yml n deployment.yml file
   > helm install helmname .
   > helm list
   > minikube ip
   > ip:portNumber # for testing
   > helm uninstall helmname # to teardown the helm chart
 ```
   - deployment.yml > change the label to app:apache
    ![image](https://user-images.githubusercontent.com/75510135/124870652-afcc4400-dfe0-11eb-85e8-3668b6d156d0.png)

   - service.yml
   ![image](https://user-images.githubusercontent.com/75510135/124871029-28cb9b80-dfe1-11eb-9007-119495977656.png)

   - values.yml
   ![image](https://user-images.githubusercontent.com/75510135/124871362-9677c780-dfe1-11eb-9bdf-cba31810bc83.png)
    
# Troubleshooting
    - helm lint # highlight format errors
    - helm template . # swiss army knife , value replacement
    - heml template . > templated.yaml # dryn-run to identify run time issue
    - helm template . | kubectl create -f - # simulate deployment
    
   
