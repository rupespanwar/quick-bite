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

    
    
