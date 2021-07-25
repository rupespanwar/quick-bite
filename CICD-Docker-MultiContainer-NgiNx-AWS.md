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





