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


 
 
 
