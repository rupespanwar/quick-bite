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
    
   
# CHART-DEEP DIVE
 - To Deploy into Production , refer Production.yaml as Values
    
    ![image](https://user-images.githubusercontent.com/75510135/124876249-6af7db80-dfe7-11eb-910f-6eb8a988da49.png)
    
 - Labels
   ![image](https://user-images.githubusercontent.com/75510135/124879056-71d41d80-dfea-11eb-8bf0-8a4f080ceaa9.png)

 - using the labels
      ![image](https://user-images.githubusercontent.com/75510135/124878936-4a7d5080-dfea-11eb-82dd-7037344e9485.png)
 
  - using Template
    ![image](https://user-images.githubusercontent.com/75510135/124880948-71d51d00-dfec-11eb-9f50-c38653906081.png)
    
    set variable values to check
    ![image](https://user-images.githubusercontent.com/75510135/124881490-0475bc00-dfed-11eb-94b5-95febb60e23a.png)

    replacing the proxy template 
    ![image](https://user-images.githubusercontent.com/75510135/124881850-6df5ca80-dfed-11eb-8799-80b5d9c4cc67.png)

    cmd > helm template . -f values.yaml
    
   # REFERENCES
    - More information on flow control with Helm:
    - https://helm.sh/docs/chart_template_guide/control_structures/

    - Operators you can use with Helm: 
    - https://helm.sh/docs/chart_template_guide/functions_and_pipelines/#operators-are-functions

# Challenge 2
![image](https://user-images.githubusercontent.com/75510135/124884296-c332db80-dfef-11eb-9bdf-d48c8a533114.png)

![image](https://user-images.githubusercontent.com/75510135/124885771-3b4dd100-dff1-11eb-8c57-ff4071141ef6.png)

![image](https://user-images.githubusercontent.com/75510135/124886670-17d75600-dff2-11eb-929e-9d90e6334545.png)


![image](https://user-images.githubusercontent.com/75510135/124886569-fecea500-dff1-11eb-8f54-5061d4601c80.png)

# CHart Museum
> helm repo update
> helm pull chatmuseum/name
Where to get Chart Museum:
- https://github.com/helm/chartmuseum

If you have issues with the above link; please try the following:
 - https://github.com/helm/chartmuseum#helm-chart

More details on Chart Museum, useful for when deploying to different cloud platforms:
 - https://github.com/helm/charts/tree/master/stable/chartmuseum
```
cmd > helm repo add cmuseum urlofApp
cmd ? helm repo list
cmd > helm repo update
cmd > helm package .
cmd > helm search repo reponame
cmd > helm install chartname repo/chartname --version 1.0.0
cmd > curl -x DELETE chartURL
cmd > helm repo remove repoName

```

# Challenge 3
![image](https://user-images.githubusercontent.com/75510135/124913156-6b569d80-e00c-11eb-9548-b77da892e25b.png)

# Umbrella Chart
- values for subchart
![image](https://user-images.githubusercontent.com/75510135/124913917-58909880-e00d-11eb-9bad-28e0f1350f98.png)

- global values
![image](https://user-images.githubusercontent.com/75510135/124914244-c210a700-e00d-11eb-882e-c0610253cafc.png)

- make changes in service.yaml
![image](https://user-images.githubusercontent.com/75510135/124915583-53cce400-e00f-11eb-931e-9bfebe23f983.png)

cmd > helm template umberlla # to validate

- Dependency
![image](https://user-images.githubusercontent.com/75510135/124916872-c5596200-e010-11eb-9384-e4e7f38083ae.png)

cmd > helm dep list
cmd > helm dep build 

![image](https://user-images.githubusercontent.com/75510135/124917115-12d5cf00-e011-11eb-8e7d-6844fe74a945.png)




API Commands Available: 
- https://github.com/helm/chartmuseum


