<img width="631" alt="image" src="https://user-images.githubusercontent.com/75510135/127624609-00f5a29c-4606-4b8b-85a7-07f25f113a50.png">
<img width="796" alt="image" src="https://user-images.githubusercontent.com/75510135/127626373-c2dd3ac7-3f5d-4f47-9176-3e6081a2eed5.png">

<img width="728" alt="image" src="https://user-images.githubusercontent.com/75510135/127626398-77a6fce8-f164-453f-a6c5-1ae9171a4405.png">
<img width="797" alt="image" src="https://user-images.githubusercontent.com/75510135/127626429-cc3de3d1-ae8a-4a42-bf3d-80ea4e85b5ab.png">

<img width="764" alt="image" src="https://user-images.githubusercontent.com/75510135/127626488-771ea9f8-f341-480b-af51-c9ac5d536e95.png">

<img width="747" alt="image" src="https://user-images.githubusercontent.com/75510135/127626511-0f9524ab-c74c-4425-9251-6a6ff607194e.png">

<img width="800" alt="image" src="https://user-images.githubusercontent.com/75510135/127626534-6c1ad4e5-6a87-4212-96c2-1098c735989f.png">

<img width="807" alt="image" src="https://user-images.githubusercontent.com/75510135/127626554-acc16836-2067-47c5-93d2-fa3246667b19.png">

<img width="813" alt="image" src="https://user-images.githubusercontent.com/75510135/127626601-ec10d994-3078-4cbe-97c4-a4f76166b709.png">

<img width="786" alt="image" src="https://user-images.githubusercontent.com/75510135/127626639-e1a29d6e-a512-472f-9bf5-9a39378b8470.png">

<img width="771" alt="image" src="https://user-images.githubusercontent.com/75510135/127626665-64a13599-29f9-4304-9045-939a71cb1354.png">

        kubectl create -f deployment-definition.yaml
        kubectl get deployments
        kubectl apply -f deployment-definition.yaml
        kubectl set image deployment/myapp-deployment nginx=nginx:1.9.1
        kubectl rollout status deployment/myapp-deployment
        kubectl rollout history deployment/myapp-deployment
        kubectl rollout undo deployment/myapp-deployment

        curl-test.sh
        for i in {1..35}; do
           kubectl exec --namespace=kube-public curl -- sh -c 'test=`wget -qO- -T 2  http://webapp-service.default.svc.cluster.local:8080/info 2>&1` && echo "$test OK" || echo "Failed"';
           echo ""
        done

         kubectl describe deploy frontend | grep Image
         kubectl describe deploy frontend | grep StrategyType:
         kubectl set image deployment/deploymentName containerName=newImage/webapp-color:v2


Configure Applications

Configuring applications comprises of understanding the following concepts:

    Configuring Command and Arguments on applications

    Configuring Environment Variables

    Configuring Secrets
    
 <img width="771" alt="image" src="https://user-images.githubusercontent.com/75510135/127632502-fb3e2795-820d-4820-941d-40b57255e7ed.png">

 <img width="806" alt="image" src="https://user-images.githubusercontent.com/75510135/127632602-33c67f3c-f9f6-43b1-ad2c-1af844d48a93.png">

<img width="819" alt="image" src="https://user-images.githubusercontent.com/75510135/127632630-b6503af3-d6ce-4cba-b92d-51499c5e117c.png">

<img width="802" alt="image" src="https://user-images.githubusercontent.com/75510135/127632656-93398b6b-4e19-473e-ab8e-b85cfb2b22b9.png">

<img width="845" alt="image" src="https://user-images.githubusercontent.com/75510135/127632755-2214aaee-8c81-41ee-afd8-b632e13a796e.png">

<img width="818" alt="image" src="https://user-images.githubusercontent.com/75510135/127632853-57247347-19a4-43ab-a22a-a3c67a94cf58.png">

![image](https://user-images.githubusercontent.com/75510135/127644944-5035a569-4bac-4969-a1d8-cecbbf75db92.png)
![image](https://user-images.githubusercontent.com/75510135/127645011-3a634d02-d4d6-4e7c-8683-7da4a80f0bca.png)

* Create a pod with the ubuntu image to run a container to sleep for 5000 seconds

                                apiVersion: v1
                                kind: Pod
                                metadata:
                                  name: ubuntu-sleeper-pod
                                spec:
                                 containers:
                                 - name: ubuntu-sleeper
                                   image: ubuntu-sleeper
                                   command: ["sleep","5000"]
                                //   args: ["5000"]
  

 # Configure Environment Variables In Applications

![image](https://user-images.githubusercontent.com/75510135/127650614-b264f7e9-ae5b-454e-a8a4-98b04a38f9a6.png)
![image](https://user-images.githubusercontent.com/75510135/127650673-94e4f3e0-b60c-470b-9fee-a0cd2685c938.png)
![image](https://user-images.githubusercontent.com/75510135/127650730-bd323e68-c391-4865-ba1e-61f570f104d3.png)
![image](https://user-images.githubusercontent.com/75510135/127650798-d7329bed-b087-40df-a47c-db8bf36d5b9a.png)
    kubectl create configmap app-config --from-literal=APP_COLOR=blue --from-literal=APP_MODE=prod
    kubectl create configmap app-config --from-file=app_config.properties (Another way)

![image](https://user-images.githubusercontent.com/75510135/127650969-731aec36-1ac9-4001-a733-03e840f62f0f.png)

![image](https://user-images.githubusercontent.com/75510135/127651084-5e69c7c5-4c59-4984-8e24-a46856cab6f9.png)

![image](https://user-images.githubusercontent.com/75510135/127651150-37b1d1f0-8eb9-4d5c-a341-3f7eb42647af.png)

![image](https://user-images.githubusercontent.com/75510135/127651202-b0ebea5f-cdac-4cc8-8574-03eb73338d1e.png)

![image](https://user-images.githubusercontent.com/75510135/127651242-af1e88a5-b364-4032-9c86-0c5c79f42779.png)

![image](https://user-images.githubusercontent.com/75510135/127651268-df726b6f-c2d4-4bda-89b0-cde5f0a3cdd4.png)

![image](https://user-images.githubusercontent.com/75510135/127651344-e26dcf44-ce0b-463d-b6fb-49a53ac46321.png)
![image](https://user-images.githubusercontent.com/75510135/127651299-ec962704-bd37-478a-bfdd-3fd256dee769.png)

        kubectl get cm
        kubectl create configmap webapp-config-map --from-literal=APP_COLOR=darkblue
        kubectl get pods webapp-color -o yaml > new-webapp.yaml
        kubectl delete pods webapp-color
        Update pod definition file, under spec.containers section update the below.
        - envFrom:
          - configMapRef:
             name: webapp-config-map
        kubectl create -f new-webapp.yaml


# Secrets
<img width="753" alt="image" src="https://user-images.githubusercontent.com/75510135/127661115-0cf75fc7-c656-4d3b-bf23-57791a63daf2.png">

<img width="747" alt="image" src="https://user-images.githubusercontent.com/75510135/127661149-cfe12a91-b54e-414a-80a8-7db7b9cb291b.png">

<img width="757" alt="image" src="https://user-images.githubusercontent.com/75510135/127661176-f6a9a496-5c30-4a03-b675-fe5d58309043.png">

<img width="762" alt="image" src="https://user-images.githubusercontent.com/75510135/127661200-44b970bb-0233-4827-8479-a3b221f9d7cb.png">

<img width="772" alt="image" src="https://user-images.githubusercontent.com/75510135/127661224-e78cbb87-6dc9-47de-8d1a-372cd0572a91.png">

<img width="740" alt="image" src="https://user-images.githubusercontent.com/75510135/127661246-c9de3890-8584-4703-9097-f69b245302cd.png">

<img width="771" alt="image" src="https://user-images.githubusercontent.com/75510135/127661289-81dc4d92-c564-453c-b0e6-1c3a561e5ff7.png">

<img width="631" alt="image" src="https://user-images.githubusercontent.com/75510135/127661309-a4461e28-350e-4197-ac9c-77b5f89b971c.png">
<img width="764" alt="image" src="https://user-images.githubusercontent.com/75510135/127661327-17b87273-2705-4ae0-99d4-f154c16a87ef.png">

<img width="733" alt="image" src="https://user-images.githubusercontent.com/75510135/127661360-94fddb4b-7bb2-4477-a97e-bcc09add2b6c.png">

<img width="769" alt="image" src="https://user-images.githubusercontent.com/75510135/127661406-7e97c4be-4793-49df-8b46-31370f725b75.png">

<img width="767" alt="image" src="https://user-images.githubusercontent.com/75510135/127661449-32d807a1-7c7f-463d-b443-0b034a8e9605.png">
<img width="671" alt="image" src="https://user-images.githubusercontent.com/75510135/127661479-33baadc5-65cc-4fd6-adbc-5c3350c89609.png">
<img width="723" alt="image" src="https://user-images.githubusercontent.com/75510135/127661502-cc0d14e1-fa1e-49b1-897e-9301c51186ea.png">






















 
 
