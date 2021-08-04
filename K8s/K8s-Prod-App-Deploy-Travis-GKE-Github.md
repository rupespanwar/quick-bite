# Deployment Overview
<img width="1177" alt="image" src="https://user-images.githubusercontent.com/75510135/127202383-dbe866e7-fec8-4f0a-8013-99a963729466.png">

# Why GKE
<img width="1177" alt="image" src="https://user-images.githubusercontent.com/75510135/127202963-fbb8a542-74e1-460e-97cc-526531d889d9.png">

# STEP1 make a github repo
<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127204258-ef4dadd9-6d84-4f17-897a-a39656f25f8b.png">

<img width="808" alt="image" src="https://user-images.githubusercontent.com/75510135/127205907-319c1546-1ffd-4523-9ec7-f139d7d078bb.png">

<img width="953" alt="image" src="https://user-images.githubusercontent.com/75510135/127206001-60bd2703-789c-4628-b709-e4cbc5c5cc58.png">

# STEP2 wire up git repo with Travis ci
<img width="953" alt="image" src="https://user-images.githubusercontent.com/75510135/127206484-ad46d022-9f7d-4649-b112-a90513215d77.png">

<img width="953" alt="image" src="https://user-images.githubusercontent.com/75510135/127206432-c7c3f162-41ae-4aad-b8f2-a2d7f9c78f9f.png">

<img width="953" alt="image" src="https://user-images.githubusercontent.com/75510135/127206578-9fbf9534-8698-479c-a88a-859611135bd1.png">

# STEP3 create GKE, google cloud project
<img width="953" alt="image" src="https://user-images.githubusercontent.com/75510135/127206966-31cc3efe-0b13-441f-9c6f-d23af68051c1.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127207821-e5d91b3c-1b9e-4ccf-bbf7-652e343ad3ec.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127208420-312f0dd3-1585-45e9-8b56-cdb359223ea1.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127242593-a7cd774e-d940-494b-bfde-34de289f6e20.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127242656-0dfb3971-789a-4871-b1de-d168fe0650b6.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127242923-13896b2e-57e7-49ba-a907-1de6cd3ed28b.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127242941-bfd644d3-533e-413f-8bfd-de066bb75cb8.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127242986-81bee97c-f0fa-4af3-9af7-2f6309af7a4e.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127243002-9af93a8d-07bc-4a12-867b-877857518763.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127243290-5017f8e6-1733-4d6b-baff-3487889d69b9.png">

# STEP4 Travis configuation
<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127243717-5b4e675d-5583-4e0e-9759-035dcedcefa0.png">

- install Google cloud CLI 
<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127245201-1cb652d9-d600-4b65-a51c-53a124fae17b.png">
- create service account
<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127245264-ce21ae4d-0b43-4248-992a-5cfe893c1f67.png">
<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127245559-7a0c505c-f692-47a1-b76e-7864efde0aa6.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127245618-b57593ad-9585-4638-8421-7fd37d6e9f79.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127245699-a72f2b83-ad99-47dc-a244-002b99bdbf44.png">
<img width="1317" alt="image" src="https://user-images.githubusercontent.com/75510135/127246068-4894c294-2626-49e5-8569-59bd04f1c179.png">

<img width="1317" alt="image" src="https://user-images.githubusercontent.com/75510135/127246086-c6c42949-3e3c-4993-b7cb-717672ba4584.png">

<img width="486" alt="image" src="https://user-images.githubusercontent.com/75510135/127246106-4968e526-89e6-47e1-8ff4-1bde571d0850.png">

- download travis cli
- https://github.com/travis-ci/travis.rb
<img width="1103" alt="image" src="https://user-images.githubusercontent.com/75510135/127246499-cd4ca9a5-e737-4fe0-9033-4288d214ea2b.png">
 - create a docker image to work on secret
<img width="1004" alt="image" src="https://user-images.githubusercontent.com/75510135/127246927-53ff4242-82ad-425b-8a3c-b47969a1a8bf.png">
- then run gem install travis

<img width="1004" alt="image" src="https://user-images.githubusercontent.com/75510135/127247225-a7186d8e-c876-49c5-8c90-7c22878cdf4f.png">

- then type > travis

<img width="1004" alt="image" src="https://user-images.githubusercontent.com/75510135/127247491-d77f36ed-4e23-4b49-bd96-df3bf03783ff.png">

- encrypt the file
<img width="1103" alt="image" src="https://user-images.githubusercontent.com/75510135/127249048-b6ed9f2f-2be5-4b29-8b50-035afcb81d56.png">

- login into Travis using Github token

multi-k8s-prod $ travis login --github-token GIT_HUB_TOKEN --com
Successfully logged in as rupeshpanwar!


- Note
     * travis login --github-token YOUR_PERSONAL_TOKEN --com

   or

    * travis login --github-token YOUR_PERSONAL_TOKEN --pro
    
- travis encrypt-file premium-student-321118-adbe9ed0b7ce.json -r rupeshpanwar/multi-k8s --com

<img width="862" alt="image" src="https://user-images.githubusercontent.com/75510135/127251040-d05ddda0-f42e-432f-a30a-3b603fff1efb.png">
- take the cmd from above step to add into travis file

- openssl aes-256-cbc -K $encrypted_1d15443f7143_key -iv $encrypted_1d15443f7143_iv -in premium-student-321118-adbe9ed0b7ce.json.enc -out premium-student-321118-adbe9ed0b7ce.json -d


Make sure to change this script:

    script:
      - docker run USERNAME/react-test npm test -- --coverage

To use the CI flag and remove coverage:

    script:
      - docker run -e CI=true USERNAME/react-test npm test
      
 - quick note while making the deployment script for Travis

<img width="1218" alt="image" src="https://user-images.githubusercontent.com/75510135/127265304-914e8b88-c95f-41a6-bcb5-e06057ab9114.png">

<img width="1218" alt="image" src="https://user-images.githubusercontent.com/75510135/127265497-ec3cd221-4cd3-4831-8ae6-dc3331ff2ca8.png">

<img width="1218" alt="image" src="https://user-images.githubusercontent.com/75510135/127265749-8e3ddb6b-baef-4d2a-8527-97e316238937.png">

- if anything breakes out

<img width="1218" alt="image" src="https://user-images.githubusercontent.com/75510135/127265860-7e21d955-1a25-4c95-89a3-af2630bbc4f4.png">

<img width="1218" alt="image" src="https://user-images.githubusercontent.com/75510135/127266014-2b787ef2-f1e4-458c-a7a7-5bbb12eff39a.png">

<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127269445-2fe65470-ac23-4bfe-b97e-88bb7860ebcc.png">
<img width="1082" alt="image" src="https://user-images.githubusercontent.com/75510135/127269478-8bb81066-2d20-425f-a1ea-dab945ac18d5.png">

<img width="1082" alt="image" src="https://user-images.githubusercontent.com/75510135/127269492-e156f672-da02-4222-ba48-85dc6244d55b.png">

- create secret on GKE

<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127269585-fc9b0879-faaa-4869-87e6-0cca19d2abd8.png">

<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127269657-d7c0ef62-e4ed-44c4-a34b-59386cb16972.png">

- open cloud shell

<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127269791-6549240b-3d4a-47e7-b3d3-7420a2cc9331.png">

- run , gcloud config set project projectId

<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127270207-42b48760-da18-4d41-afd0-0d812271bfd0.png">

- then , gcloud config set compute/zone us-central1-c 
- next run , gcloud container clusters get-credentials multi-container 
<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127270482-b7ffb447-144e-4057-ab60-856d718edf4c.png">

- create secret
kubectl create secret generic pgpassword --from-literal PGPASSWORD=xxxx

<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127271138-35f231e0-dfaf-4a40-8af5-84d3effd6c3c.png">

link to the docs:

https://helm.sh/docs/intro/install/#from-script

Link to the docs:

https://kubernetes.github.io/ingress-nginx/deploy/#using-helm

# Deploy Ingress Controller/service
<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127271627-cf108af2-2f2a-4564-a9e3-7b96979adfee.png">

<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127271966-8e368515-8b41-4021-ad9b-e21ecc75a7b2.png">

<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127272471-391e0194-5344-443d-ad92-0fb69ee72c55.png">

<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127272502-b3fc5ce6-4ac9-4f6c-a47f-2f976a0e644e.png">

<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127272569-4b0d7c42-7e7e-4973-be8d-67277c2b3017.png">
<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127272897-8b76b5d8-fe4b-4418-b500-7dd0ff74cde4.png">

```
 curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3
    chmod 700 get_helm.sh
    ./get_helm.sh
 
 <img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127273119-d77c15a7-b2e6-4a19-a323-bdc440dde0c8.png">

<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127273201-7b422522-1573-4b4c-a828-47ab4b207808.png">

<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127273502-0566805e-1823-4f7d-830c-7c2a0106f4fc.png">

<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127273739-814ba186-7c95-414e-9d7c-c84a29201841.png">

<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127274022-6d2477c2-6967-49a9-9fca-184f6dc4e485.png">

- run on cloud shell, kubectl create serviceaccount --namespace kube-system tiller

 - then run ,  rpanwar@cloudshell:~ (premium-student-321118)$ kubectl create clusterrolebinding tiller-cluster-rule --clusterrole=cluster-admin --serviceaccount=kube-system:tiller
clusterrolebinding.rbac.authorization.k8s.io/tiller-cluster-rule created

- Installing Ingress
```
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update

helm install ingress-nginx ingress-nginx/ingress-nginx


<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127277128-83fab8dd-7825-4f42-a674-0eb6e3ead54d.png">


<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127277250-a3b47557-01bf-43b0-93f1-48c01cb3140e.png">

<img width="1552" alt="image" src="https://user-images.githubusercontent.com/75510135/127277733-f7d04f69-36ad-4380-97d1-7abf70c34e9b.png">
# Finally deploying the code
- commit code to Github

- git add . , git commit -m '' , git push

-this will trigger Travis
<img width="1086" alt="image" src="https://user-images.githubusercontent.com/75510135/127282766-9087a198-d1b4-4524-a71d-9b540fe39392.png">

<img width="1086" alt="image" src="https://user-images.githubusercontent.com/75510135/127282982-7aa380ee-190c-4a79-b686-4eb75038f5d0.png">

# End-2end workflow
<img width="1086" alt="image" src="https://user-images.githubusercontent.com/75510135/127290807-e9dbcb39-f76c-4b4d-965e-3f4acadcd2e0.png">

sudo: required
services:
  - docker
env:
  global:
    - SHA=$(git rev-parse HEAD)
    - CLOUDSDK_CORE_DISABLE_PROMPTS=1
before_install:
  - openssl aes-256-cbc -K $encrypted_1d15443f7143_key -iv $encrypted_1d15443f7143_iv -in premium-student-321118-adbe9ed0b7ce.json.enc -out premium-student-321118-adbe9ed0b7ce.json -d
  - curl https://sdk.cloud.google.com | bash > /dev/null;
  - source $HOME/google-cloud-sdk/path.bash.inc
  - gcloud components update kubectl
  - gcloud auth activate-service-account --key-file premium-student-321118-adbe9ed0b7ce.json
  - gcloud config set project premium-student-321118
  - gcloud config set compute/zone us-central1-c
  - gcloud container clusters get-credentials multi-container
  - echo "$DOCKER_PASSWORD" | docker login -u "$DOCKER_ID" --password-stdin
  - docker build -t rupeshpanwar/react-test -f ./client/Dockerfile.dev ./client

script:
  - docker run rupeshpanwar/react-test npm test -- --coverage

deploy:
  provider: script
  script: bash ./deploy.sh
  on:
    branch: main


