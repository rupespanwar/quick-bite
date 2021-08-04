# App Overview
<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126739601-24cf9406-345a-4dc1-ade9-236d22b23047.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126739613-3d9a522c-b746-42dd-9211-ab37fd9ab2cd.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126739784-de5930cd-6ee4-49db-8f01-8db34cdf7b48.png">

# Code
<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126740492-b8724faa-e003-4dbf-ae35-55dc92ea924b.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126740971-1edbd96a-9c3c-4703-b863-96534c921e38.png">

## Dockerfile
<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126742921-88a6877a-f9a3-4a3b-92f9-e322b0b0d8a9.png">

- create Redis container

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126743401-8f284778-9d26-4d4a-82ee-802510fae100.png">

- PiN(pain in neck)

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126743592-b81c87fe-7b4a-4b05-b23b-77957f791d6d.png">

# Docker-Compose.yml
<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126743698-b78fa205-0ed1-438c-a520-d78d931be8a5.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126743837-8c83699d-4d0d-443b-822f-5a67b1b6fc47.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126743978-0b3f4016-e0fa-409b-b842-e9d682251bc1.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126744653-9d6f2ad6-6e4d-4da3-82bb-785c821f140c.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126744998-0747efac-1115-47f2-9502-74ddaba795b3.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126746002-bb8d0c11-ade3-4407-80cd-cdc84a8d6ee3.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126746233-b11ce9ed-430c-4130-83d3-98363786a752.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126746497-c7a45d5f-98f3-4587-a799-1827fe0e5a66.png">

# Container maintenance 
<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126747674-83d3abc2-61e2-4426-b0bb-f8f8cf8132ac.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126747754-077fc49a-f1ff-4103-99a6-1e5e9775b6b6.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126747821-c839283b-cf15-4bb7-9e29-3e9d420cd4ba.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126753426-c1c3ae93-9100-413e-82ac-1cde645db853.png">




# PRODUCTION GRADE WORKFLOW
<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126755488-6fc9d5c8-ddec-463e-9dd2-6cb47c432412.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126756280-7c1c6fd3-0f1a-4620-9f3a-8e7e7f09b428.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126756372-31959443-dfbc-446f-840d-8bc2ccd0ca52.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126756418-b84b171b-ad1c-4eb4-8dc3-517e3ea14dd0.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126756443-bbd46308-8839-42a4-95c4-7e7044de32f4.png">

## create a demo app
Create React App Generation

updated 8-4-2020

In the next lecture, Stephen will be going over how to install Create React App globally and generate the application. This method of generating a React project is no longer recommended.

Instead of this:

npm install -g create-react-app

create-react-app frontend

We need to run this command:

npx create-react-app frontend

Documentation:

https://create-react-app.dev/docs/getting-started#npx

If you've previously installed create-react-app globally via npm install -g create-react-app, we recommend you uninstall the package using npm uninstall -g create-react-app to ensure that npx always uses the latest version.

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126757392-2efdd1ea-08d6-41b5-ab6a-188bc7ed94af.png">

### npm uninstall -g create-react-app && npm i -g npm@latest && npm cache clean -f && npx create-react-app my-app
<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126758347-fc70784c-e09e-4b69-a918-57fa7206c288.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126759025-e4f00c6d-474e-4f33-9c6d-def2004a5b30.png">

- npm run start

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126759100-4311e8a0-3b0e-4185-bae7-d87c8aa11aeb.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126759276-7a207224-61d1-43bb-9727-3a6ce6eaf71d.png">

- Prepare DOCKERFILE for dev

<img width="808" alt="image" src="https://user-images.githubusercontent.com/75510135/126759769-4019d430-9b22-4af4-aaa6-571ab529f326.png">

<img width="842" alt="image" src="https://user-images.githubusercontent.com/75510135/126760195-bcd1c7c5-714f-4745-ba0a-6b7435c0d86b.png">

React App Exits Immediately with Docker Run Command

3-22-2020

Due to a recent update in the Create React App library, we will need to change how we start our containers.

In the upcoming lecture, you'll need to add the -it flag to run the container in interactive mode:

docker run -it -p 3000:3000 IMAGE_ID 

## to make changes in code / use DOCKER VOLUME
<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126765609-37ca7e10-c777-45ee-9a13-e012c612df26.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126765793-a1bd6a0e-bc9e-4a9e-a95b-9134c1af9c68.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126766631-ce31f596-ea83-401d-b7da-feb7808a7d0c.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126766661-41d0c061-3c7a-42f1-876e-3f9a9a3cf5a0.png">
<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126766846-095fc789-df4a-4d30-92b1-3050dae1234c.png">

### React App Exited With Code 0

4-1-2020

Recently, a bug was introduced with the latest Create React App version that is causing the React app to exit when starting with Docker Compose.

To Resolve this:

Add stdin_open property to your docker-compose.yml file

      web:
        stdin_open: true

Make sure you rebuild your containers after making this change with  docker-compose down && docker-compose up --build

https://github.com/facebook/create-react-app/issues/8688

https://stackoverflow.com/questions/60790696/react-scripts-start-exiting-in-docker-foreground-cmd


<img width="808" alt="image" src="https://user-images.githubusercontent.com/75510135/126769318-54df84d2-3707-460e-bc43-bac59fef56f3.png">

<img width="1081" alt="image" src="https://user-images.githubusercontent.com/75510135/126769374-e070a3e0-4f52-4034-89d2-487212941ca2.png">

# Executing TESTs
<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126769783-fd39834b-01e5-4cc0-b474-1c588b34a626.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126769907-bde73a00-0d22-4aa3-b953-05e5836e65a0.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126770144-403f4d66-43f6-4753-a24e-9e5814c7dd99.png">

- CONTINUOUS running TESTS
<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126770381-00bb0cd3-e85e-46ad-ab7b-b21de2f69caf.png">

- run docker-compose.yml first

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126770490-941eb2ab-d7e9-4588-b853-e70232c700f8.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126770650-bba25407-9cd7-4572-8c03-6b15967c9d4b.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126770668-0ce1f050-c384-4c04-ad6b-c9cb6e11bfba.png">

<img width="808" alt="image" src="https://user-images.githubusercontent.com/75510135/126775096-0447837c-6be6-4eb8-9db2-1c0f8793f7b2.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126775152-7d142d2a-eb4d-4504-a8cb-405b61888218.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126775196-6f34d665-f6a0-47ba-b801-81277ddd57b1.png">

<img width="1090" alt="image" src="https://user-images.githubusercontent.com/75510135/126775511-691d9239-2fc7-4415-ba0e-3322d944855d.png">

# Need for NGINX
<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126778994-a48dc3df-656e-4efa-addf-99b8a28d58a2.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126779051-46b50484-2a61-4703-864b-760c21a0f4e5.png">

<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126779099-aa1e6ae1-5bc1-4345-802a-ce27cc51ede7.png">

## Multi-stage Docker build
<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126779431-7cf62e99-3e60-4ebe-b711-6c366b13734b.png">
<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126780182-925ab2cd-fdeb-4d81-b36c-dfb8798f7013.png">

Named Builders and AWS

updated 10-1-2020

In the next lecture, we will be creating a multi-step build in our production Dockerfile. When we deploy to AWS in section 7, this currently will fail if you attempt to use a named builder as shown.

To remedy this, we should create an unnamed builder like so:

Instead of this:

    FROM node:alpine as builder
    WORKDIR '/app'
    COPY package.json .
    RUN npm install
    COPY . .
    RUN npm run build
     
    FROM nginx
    COPY --from=builder /app/build /usr/share/nginx/html

Do this:

    FROM node:alpine
    WORKDIR '/app'
    COPY package.json .
    RUN npm install
    COPY . .
    RUN npm run build
     
    FROM nginx
    COPY --from=0 /app/build /usr/share/nginx/html
    
   
   
   
    
   <img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126781860-32abeae1-b3c7-42a2-b5ed-70f6f7fcdee2.png">
### multi stage docker file
<img width="808" alt="image" src="https://user-images.githubusercontent.com/75510135/126782238-d4be8c3d-109f-48e1-b01d-141b83774922.png">


<img width="1129" alt="image" src="https://user-images.githubusercontent.com/75510135/126782646-6930494c-2cc7-4230-ba32-2be5c5faa2ae.png">













