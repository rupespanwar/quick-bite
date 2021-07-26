# Reference git repo for code , dockerfile, travis ci , nginx
https://github.com/rupeshpanwar/docker-multicontainer.git

# Running App in local
<img width="1149" alt="image" src="https://user-images.githubusercontent.com/75510135/126870794-6722fa80-c227-4f6a-b2c3-36e4e59b4860.png">

# Single Container Setup flow
<img width="1149" alt="image" src="https://user-images.githubusercontent.com/75510135/126870802-1d63e32b-b620-4466-832d-88d8f59981ee.png">

# Multi Container Setup flow
<img width="1149" alt="image" src="https://user-images.githubusercontent.com/75510135/126870930-09d0ea24-113d-4703-b5bd-47ce20182e24.png">


# Production Dockerfile
## Dockerfile - worker
<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126871187-48c8d4a2-22f1-4865-8d38-6f79c319d43a.png">
**Change in CMD [start]**
<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126871191-e35f2828-90d7-46e4-8244-9fbd7cd553ec.png">

## Dockerfile - server[api]
<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126871286-f4d4cfd9-8173-4eb8-80d5-b89b7eab9519.png">
<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126871293-3b99ec92-03d4-441f-b61a-33c7fb87a8dd.png">

## Dockerfile- NgiNx 
<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126871352-e7ef37d8-c050-4e82-9b57-e4160f617cfb.png">

## Dockerfile - client
### single container app
<img width="1149" alt="image" src="https://user-images.githubusercontent.com/75510135/126871433-ebfb58e0-7ee2-43b9-9538-54fa1b275de6.png">
<img width="1149" alt="image" src="https://user-images.githubusercontent.com/75510135/126871484-b02aaaf4-421c-4f4f-864f-50e1d148aa05.png">

### multi container app
<img width="1149" alt="image" src="https://user-images.githubusercontent.com/75510135/126871478-91957666-9b29-48f6-92fe-9693760aa253.png">

<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126871720-51705ae1-84e3-4e0c-964c-c1264e2df61b.png">

<img width="970" alt="image" src="https://user-images.githubusercontent.com/75510135/126871892-bc7bec35-5c3f-4d20-9f81-61c93a46d8bc.png">

```
FROM node:alpine
WORKDIR "/app"
COPY ./package.json ./
RUN npm install
COPY . .
CMD npm run build

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=0 /etc/build /usr/share/nginx/html
```

***Just a note before Travis CI is configured****
<img width="970" alt="image" src="https://user-images.githubusercontent.com/75510135/126871969-7ca18178-dece-4907-804e-8d3095d6df39.png">

# STEP1 Push the code to Gihub  
    https://github.com/rupeshpanwar/docker-multicontainer.git
    
   git add .
   git commit -m 'Client - code'
   git push

# STEP2 Login to Travis CI , configure this newly pushed repo
- go to setting 

<img width="1018" alt="image" src="https://user-images.githubusercontent.com/75510135/126897513-ef6f87fd-6a12-4c86-9a81-c50eeef36fde.png">

- Sync Account to fetch above repo
<img width="1018" alt="image" src="https://user-images.githubusercontent.com/75510135/126897681-0ee83803-d926-4a88-b0fb-fbb91dc7763f.png">

<img width="901" alt="image" src="https://user-images.githubusercontent.com/75510135/126897677-ff0989aa-869e-4ce9-99ef-43d4467a6a3b.png">

<img width="1018" alt="image" src="https://user-images.githubusercontent.com/75510135/126897770-3dd780e7-e403-4766-9cbe-03bbb22d3f30.png">

    script:
      - docker run -e CI=true USERNAME/react-test npm test
      
# STEP3 Create Travis ci yml file, environment vars to login into Docker(to push image to docker)
- click on more option, settings

<img width="1018" alt="image" src="https://user-images.githubusercontent.com/75510135/126898007-a43996f3-22c5-4152-9b38-589d83f1ad18.png">
- Under Env var section , create 2 new vars as below

<img width="1018" alt="image" src="https://user-images.githubusercontent.com/75510135/126898108-2e0098f7-fbe5-4ac2-9fcd-109b58797e14.png">

- create Travis yml file

<img width="1014" alt="image" src="https://user-images.githubusercontent.com/75510135/126898669-e5f5d1ca-9d2e-4fb5-85bc-13dbd58a3f26.png">

```
sudo: required
services:
  - docker
before_install:
  - docker build -t rupeshpanwar/react-test -f ./client/Dockerfile.dev ./client
script:
  - docker run  -e CI=true rupeshpanwar/react-test npm run test -- --coverage

after_success:
  - docker build -t rupeshpanwar/multi-client ./client
  - docker build -t rupeshpanwar/multi-nginx ./nginx
  - docker build -t rupeshpanwar/multi-server ./server
  - docker build -t rupeshpanwar/multi-worker ./worker
  # Login into Docker CLI
  - echo "$DOCKER_PASSWORDS" | docker login -u "$DOCKER_ID" --password-stdin
  - docker push rupeshpanwar/multi-client
  - docker push rupeshpanwar/multi-nginx
  - docker push rupeshpanwar/multi-server
  - docker push rupeshpanwar/multi-worker
  
```
- push travis file to git 

<img width="808" alt="image" src="https://user-images.githubusercontent.com/75510135/126898768-df41c12e-97c7-47c6-9e5f-4ca5c46b1939.png">

- Check Travis dashboard for CI trigger

<img width="994" alt="image" src="https://user-images.githubusercontent.com/75510135/126898787-354310a6-d390-46f7-a631-b38a768382f0.png">

<img width="994" alt="image" src="https://user-images.githubusercontent.com/75510135/126898802-96e420a7-64a0-46ae-b07e-fbafb83db453.png">

<img width="950" alt="image" src="https://user-images.githubusercontent.com/75510135/126898831-65d63eda-8c7d-44c3-bd03-3a97169fdbb7.png">

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126899237-14b1190b-1cbb-412c-93a4-902787a35b1e.png">

- cross check images on docker hub

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126899284-df7eaab4-b84b-4b20-b23b-66f1085d9ba1.png">


# Deployment to AWS - CD
## Single container app
<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126901904-ca7bc063-eeb5-40aa-8b83-afcd55fb7afb.png">

## Multi container app
<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126901928-d3429e8c-28bd-4084-8737-de36039f09c7.png">

- prepare Dockerrun json to deploy on AWS

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126901963-c9cdde8b-7b50-4da7-bca9-35bdf064cdaf.png">

~ to Docker-compose
<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126901999-f60c7f18-c081-4fd6-a498-cd4b449ae84b.png">

# Reference
<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126902098-a6a0395e-dd6f-4208-af12-6a160202967c.png">

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126902114-9b3caa93-d3b9-4522-8d67-d749afeb86b9.png">
<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126902125-30ea0d86-d0a3-4653-a40a-ee79e7d10254.png">

## it uses links to connect nginx container to client/server container
<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126903065-4566b07d-dfa7-4d50-895e-ebc3b5466a9f.png">
# STEP4 create Dockerrun to deploy to AWS
<img width="883" alt="image" src="https://user-images.githubusercontent.com/75510135/126903089-eff074b0-67b8-4e4b-877b-333859ddbd75.png">

```
{
    "AWSEBDockerrunVersion": 2,
    "containerDefinitions": [
        {
            "name": "client",
            "image": "rupeshpanwar/multi-client",
            "hostname": "client",
            "essential": false
        },
        {
            "name": "server",
            "image": "rupeshpanwar/multi-server",
            "hostname": "api",
            "essential": false
        },
        {
            "name": "worker",
            "image": "rupeshpanwar/multi-worker",
            "hostname": "worker",
            "essential": false
        },
        {
            "name": "nginx",
            "image": "rupeshpanwar/multi-nginx",
            "hostname": "nginx",
            "essential": true,
            "portMappings": [{
                "hostPort": 80,
                "containerPort": 80
            }],
            "links": ["client","server"]
        }
    ]
}
```

# STEP5 Create EBS environment
- create Application

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126903325-ee2ace5a-eade-4061-a33d-efb42bb9c473.png">

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126903337-de11f1e0-14f0-40d3-9f8f-e21c38f9de8b.png">

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126903359-33778b37-b37f-4ab8-a1b7-89f8c5020472.png">

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126903378-8241ce58-3dc5-4889-9291-573a89d38a36.png">

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126903694-2181200b-cd73-459d-ac09-eb697ba88e43.png">

## Data Service provider
<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126903750-e8c25ec1-4e54-4cd8-979c-23b86fbd8ca6.png">

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126903788-f51f4c6f-4f26-4363-8247-cf99e6bd7a7d.png">
<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126903839-c7ab7598-2f61-4c08-8c28-5f7b334aab31.png">

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126903973-6a78abcc-81e5-404f-9f61-4938527c32c1.png">

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126906080-a4cdf583-4a8f-4413-b35a-255b8a955c9c.png">

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126917649-4ca0237c-1470-4ecb-aff1-d19ce833b7df.png">

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126917679-ea8b0edd-f84b-40ca-80f1-0f73705b5398.png">

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126917735-39efdf15-cec2-4b03-8516-614ab2970cb6.png">

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126917789-e27f8dd3-ca56-45dc-9de6-dd267a961abb.png">

## Create RDS maanaged Postgres
<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126918014-4590785f-9af3-4284-b1ae-1dfa5b129185.png">
<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126918025-353f3ffb-3ec8-40c7-b58c-eb064dc66708.png">

<img width="1111" alt="image" src="https://user-images.githubusercontent.com/75510135/126918048-0d0e2a61-828a-4d39-ad06-55ad324dcf0c.png">

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126918081-08c24a98-fcc3-47d5-b6fd-9653093c3fb3.png">

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126918127-a1c54849-4f27-498d-8b10-c97af77edd4f.png">

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126918142-1fafc852-54b0-4396-8839-90a14146d4ed.png">

## Create Redis instance

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126918312-f0a891e2-26c5-4e61-93e9-90c28510db3c.png">
<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126918320-188ac206-47d3-4611-955f-b124397eb8c9.png">
<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126918339-1a35cb9c-3bd2-45c6-bb4c-a904203ae853.png">
<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126918354-4817805f-7e85-45de-ace9-9923561c5f6a.png">
<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126918379-858a3288-3fec-4593-9ca8-51a9d48619e0.png">

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126918391-40414fed-7f94-48e9-9254-0121a28ff12c.png">

<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126918404-ed270798-acb8-466b-94c1-87440d207fa7.png">
<img width="1155" alt="image" src="https://user-images.githubusercontent.com/75510135/126918413-50fe1b87-45ce-4378-a85d-72585ef6a721.png">
















