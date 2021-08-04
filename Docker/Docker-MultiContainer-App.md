# Single Conatiner App
<img width="1116" alt="image" src="https://user-images.githubusercontent.com/75510135/126852927-77044b82-cd7a-48d0-a7b7-e6c89a924643.png">

# Multi Container App Overview
<img width="1116" alt="image" src="https://user-images.githubusercontent.com/75510135/126853020-d01a2c42-48fc-46d2-92b4-090b10f6f8cc.png">
- Fronted
<img width="1116" alt="image" src="https://user-images.githubusercontent.com/75510135/126853066-5af9ac81-9997-44f8-853d-0e807b8302c8.png">

- Backend
<img width="1116" alt="image" src="https://user-images.githubusercontent.com/75510135/126853127-03c526b8-8222-4c76-ab82-dd17b926b90e.png">

<img width="1116" alt="image" src="https://user-images.githubusercontent.com/75510135/126853217-493d5037-f3e1-4b20-9829-678d08a2129b.png">

- Flow

<img width="1116" alt="image" src="https://user-images.githubusercontent.com/75510135/126853243-2938187e-af45-415f-a082-4c0ae0c9067e.png">

# Code
## Worker
<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126853724-4512e34f-a88a-40e2-8cda-22410601c998.png">

Reference # https://github.com/rupeshpanwar/docker-multicontainer
## Server
<img width="808" alt="image" src="https://user-images.githubusercontent.com/75510135/126854403-e9f9eb02-f9c0-4d44-a4eb-dc056f945123.png">
<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126855067-eef180c3-60e5-4906-899d-631bfc26618c.png">

reference : https://github.com/rupeshpanwar/docker-multicontainer

## React app
<img width="665" alt="image" src="https://user-images.githubusercontent.com/75510135/126855550-681578ba-816e-4223-aecc-e61e51471f20.png">

<img width="1116" alt="image" src="https://user-images.githubusercontent.com/75510135/126855587-749cdb8f-cc44-4d76-b86b-ce2c6c2b9ed6.png">

Reference: https://github.com/rupeshpanwar/docker-multicontainer/tree/main/client

# Dockerfile - for each of the components
<img width="1004" alt="image" src="https://user-images.githubusercontent.com/75510135/126865532-a2c91282-9e07-4f67-8ba6-98ba9262121d.png">

<img width="1004" alt="image" src="https://user-images.githubusercontent.com/75510135/126865570-6fedf735-84d6-427c-bb23-554e27711dc9.png">

- dockerfile for client(react app)

<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126866391-349badbb-e3ca-48b3-858f-ec837a3a27af.png">

<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126866394-607f4291-89d7-4b56-b467-bae1ea0c79c0.png">


- dockerfile for Server

<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126866369-0dbf4fb5-8f04-4d4c-9d23-91aba92a5794.png">

- dockerfile for worker

<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126866584-0512893c-8e3c-4755-9b29-5918bbb4404f.png">

# Adding Postgress as a service , working with Docker-Compose
<img width="1004" alt="image" src="https://user-images.githubusercontent.com/75510135/126866624-a58701be-59a0-4ced-b39f-ff9f10af9336.png">



<img width="1004" alt="image" src="https://user-images.githubusercontent.com/75510135/126866674-6042db76-825e-49c8-acb8-940d8b8ab3fc.png">

<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126867096-51bad62c-868d-48ef-b96e-ab56a661feb1.png">

- env vars for docker-compose
<img width="1004" alt="image" src="https://user-images.githubusercontent.com/75510135/126867135-aa3049a1-eccb-4536-aeb7-6d54fd3a966b.png">

- bring in all the env to docker-compose file(refer docs on docker hub for username, password for redis/postgress)

<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126867497-faec061b-4a50-4122-94ef-85945041a758.png">

## Note
      postgres:
        image: "postgres:latest"
        environment:
          - POSTGRES_PASSWORD=postgres_password
     

docker-compose down  && docker-compose up --build 
### Note API ~ Server
<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126868508-09da1ca9-93a7-4416-83b6-f172ba4d58ae.png">

# Worker & Client services
Required Client Service Update and Worker Environment Variables

In the next lecture, we will be adding a client and worker service. There are two required configuration updates that need to be made:

1) When adding the "Client" service, be sure to include the stdin_open: true configuration:

      client:
        stdin_open: true
        build:
          dockerfile: Dockerfile.dev
          context: ./client
        volumes:
          - /app/node_modules
          - ./client:/app

Otherwise, you will get a "React App exited with Code 0" error in your terminal when we attempt to start up the application.

2) When adding the "Worker" service, include the Redis host and port as environment variables:

      worker:
        build:
          dockerfile: Dockerfile.dev
          context: ./worker
        volumes:
          - /app/node_modules
          - ./worker:/app
        environment:
          - REDIS_HOST=redis
          - REDIS_PORT=6379

Otherwise, you will get a "Calculated Nothing Yet" error message.

<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126867811-2b6c1629-86d5-4dcb-9d47-7007e33c979e.png">

# Nginx path routing
<img width="1004" alt="image" src="https://user-images.githubusercontent.com/75510135/126867858-15e9d812-8489-410f-bfbc-0c2d5b68ce84.png">

<img width="1004" alt="image" src="https://user-images.githubusercontent.com/75510135/126867902-b9120bb6-0b2b-4cca-8c0d-53b9aed5036e.png">

<img width="1004" alt="image" src="https://user-images.githubusercontent.com/75510135/126867955-a0312eee-9a89-45d6-9f7b-db7bbce03fde.png">

<img width="1004" alt="image" src="https://user-images.githubusercontent.com/75510135/126867968-2f28c1c4-6f05-441f-9e97-9088a6bb4fe7.png">

<img width="1004" alt="image" src="https://user-images.githubusercontent.com/75510135/126868070-c1947db5-c952-4895-b19f-13ddb1044b56.png">

<img width="1004" alt="image" src="https://user-images.githubusercontent.com/75510135/126868103-362d2bf2-eac4-43d7-8e10-4f92fff3fd59.png">

<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126868420-cc69528d-c06e-4516-9aa5-40a53ef4f43a.png">


# Build a custom NGINX docker image
<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126868728-cfa31de5-624a-40c8-a7f8-c1e7573e2e71.png">

<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126868724-90cf48da-b4cb-44d5-9368-1293ba55aea0.png">

- update Docker-Compose yml

<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126868742-4c1067a8-3201-42d3-97d1-41c9bd667a8e.png">

- run docker compose to test

<img width="808" alt="image" src="https://user-images.githubusercontent.com/75510135/126868817-69262cf4-8795-46cf-af48-57cc58b0d4c7.png">
<img width="808" alt="image" src="https://user-images.githubusercontent.com/75510135/126868823-20204a59-6929-40a4-a82c-63441e222ea7.png">
<img width="808" alt="image" src="https://user-images.githubusercontent.com/75510135/126868829-ddd4592a-1e09-4563-a732-1b337fada5d3.png">

# Final Docker Compose yml file
```
version: '3'
services:
  postgres:
    image: 'postgres:latest'
    environment:
      - POSTGRES_PASSWORD=postgres_password
  redis:
    image: 'redis:latest'
  nginx:
    depends_on:
      - api
      - client
    restart: always
    build:
      dockerfile: Dockerfile.dev
      context: ./nginx
    ports:
      - '3050:80'
  api:
    build:
      dockerfile: Dockerfile.dev
      context: ./server
    volumes:
      - /app/node_modules
      - ./server:/app
    environment:
      - REDIS_HOST=redis
      - REDIS_PORT=6379
      - PGUSER=postgres
      - PGHOST=postgres
      - PGDATABASE=postgres
      - PGPASSWORD=postgres_password
      - PGPORT=5432
  client:
    stdin_open: true
    build:
      dockerfile: Dockerfile.dev
      context: ./client
    volumes:
      - /app/node_modules
      - ./client:/app
  worker:
    build:
      dockerfile: Dockerfile.dev
      context: ./worker
    volumes:
      - /app/node_modules
      - ./worker:/app
    environment:
      - REDIS_HOST=redis
      - REDIS_PORT=6379
```

# Final NgInx.conf file 
<img width="851" alt="image" src="https://user-images.githubusercontent.com/75510135/126870681-b8f73a2d-df71-4371-b4ad-570edde6f62e.png">


```
upstream client {
  server client:3000;
}

upstream api {
  server api:5000;
}

server {
  listen 80;

  location / {
    proxy_pass http://client;
  }

  location /sockjs-node {
    proxy_pass http://client;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection "Upgrade";
  }

  location /api {
    rewrite /api/(.*) /$1 break;
    proxy_pass http://api;
  }
}
```




REFER# https://github.com/rupeshpanwar/docker-multicontainer




