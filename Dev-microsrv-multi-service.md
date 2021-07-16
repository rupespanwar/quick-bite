
# Big challenge
<img width="703" alt="image" src="https://user-images.githubusercontent.com/75510135/125434594-d957dafd-cc60-44cf-a6bc-a1c9301f8001.png">

<img width="710" alt="image" src="https://user-images.githubusercontent.com/75510135/125435247-7a4b36fb-f0a3-4d2e-991e-9529f868e75e.png">

- Solution

<img width="725" alt="image" src="https://user-images.githubusercontent.com/75510135/125436475-07b352b1-e451-48d2-9ada-068ab2c916ac.png">

<img width="925" alt="image" src="https://user-images.githubusercontent.com/75510135/125437209-76037592-f4e8-4cd8-9f9a-1b10df177f6e.png">

# Resources
<img width="718" alt="image" src="https://user-images.githubusercontent.com/75510135/125452066-12091d13-678e-49cd-bad8-3f168a53bd95.png">

<img width="688" alt="image" src="https://user-images.githubusercontent.com/75510135/125452135-b2889b51-ec81-403e-bef6-af8b79a9a7a0.png">

<img width="708" alt="image" src="https://user-images.githubusercontent.com/75510135/125452573-0b390c84-adaf-4ead-bdc7-6ac497903a8c.png">

<img width="823" alt="image" src="https://user-images.githubusercontent.com/75510135/125452718-c727b89b-124d-4edb-abcf-c3b8540da9b9.png">
# Auth Service Setup
<img width="880" alt="image" src="https://user-images.githubusercontent.com/75510135/125452812-6df8fa92-bb7d-465d-b04b-be1f3d41596c.png">
<img width="689" alt="image" src="https://user-images.githubusercontent.com/75510135/125708824-4d7f6f91-274e-422c-a4a1-3d358bca7f10.png">
<img width="733" alt="image" src="https://user-images.githubusercontent.com/75510135/125708927-30c9a473-93fa-4c84-a366-6e2766e7f192.png">

auth $ tsc --init

- here is the basic code for the app  @ start
https://github.com/rupeshpanwar/microsvc-mulitisvc-app

<img width="1146" alt="image" src="https://user-images.githubusercontent.com/75510135/125664191-819d9b6d-7592-42e7-844d-881b04810a74.png">
# App Code
<img width="1146" alt="image" src="https://user-images.githubusercontent.com/75510135/125708543-b20cf4e0-0fd7-434e-8205-2a3a0ef95fbb.png">
Note on Code Reloading

Hi!

If you did not see your server restart after changing the index.ts file, do the following:

    Open the package.json file in the ‘auth’ directory

    Find the ‘start’ script

Update the start script to the following:

ts-node-dev --poll src/index.ts 



# Dockerization to prepare containerization for K8S

- my code
<img width="544" alt="image" src="https://user-images.githubusercontent.com/75510135/125711405-9c18ce18-2311-4198-af76-ef5da3101baa.png">

<img width="944" alt="image" src="https://user-images.githubusercontent.com/75510135/125711423-f53785a4-fbeb-4257-b733-d314430aa3eb.png">
- trainer's one
<img width="1146" alt="image" src="https://user-images.githubusercontent.com/75510135/125707533-bbebe16a-9010-460e-bbc5-f532f3d71c8b.png">
<img width="1146" alt="image" src="https://user-images.githubusercontent.com/75510135/125707554-808ebfbe-b5e9-4487-92b4-697c9b9be786.png">
<img width="1146" alt="image" src="https://user-images.githubusercontent.com/75510135/125707598-8c9bbd0b-3118-4d52-aa36-29b91eb5b1a1.png">
<img width="1146" alt="image" src="https://user-images.githubusercontent.com/75510135/125707829-52f9ac52-c0fc-4881-9f4d-da38c3e37ae1.png">
<img width="1146" alt="image" src="https://user-images.githubusercontent.com/75510135/125707966-cb21d1bb-ee40-407d-95f5-b938289d8945.png">

# Skaffold - to sync up the latest changes and deploy to container on change
<img width="1146" alt="image" src="https://user-images.githubusercontent.com/75510135/125708351-b5950be2-8bfc-46df-b8e1-352157896ca2.png">

<img width="1146" alt="image" src="https://user-images.githubusercontent.com/75510135/125708411-d99c4bb7-972d-408f-bed9-004247cb9322.png">

# Note on Code Reloading

Hi!

If you did not see your server restart after changing the index.ts file, do the following:

    Open the package.json file in the ‘auth’ directory

    Find the ‘start’ script

Update the start script to the following:

ts-node-dev --poll src/index.ts 


# Ingress - networking.k8s.io/v1beta1 Ingress is deprecated

When skaffold dev in the upcoming lecture you may encounter a warning about the v1beta1 API version that is being used:

Warning: networking.k8s.io/v1beta1 Ingress is deprecated in v1.19+, unavailable in v1.22+; use networking.k8s.io/v1 Ingress

To be clear, any changes to the Ingress will be optional and this API will be supported until Kubernetes v1.22. If you are currently experiencing any errors or issues with your Ingress this warning is not the cause of it.

If you wish to update to the v1 API, only a few very minor changes are needed:

https://kubernetes.io/docs/concepts/services-networking/ingress/

Notably, a pathType needs to be added, and how we specify the backend service name and port has changed:

    apiVersion: networking.k8s.io/v1
    kind: Ingress
    metadata:
      name: ingress-service
      annotations:
        kubernetes.io/ingress.class: nginx
        nginx.ingress.kubernetes.io/use-regex: "true"
    spec:
      rules:
        - host: ticketing.dev
          http:
            paths:
              - path: /api/users/?(.*)
                pathType: Prefix
                backend:
                  service:
                    name: auth-srv
                    port:
                      number: 3000

While the old API is still supported we will include a separate v1 Ingress file attached to each appropriate lecture that students can refer to.


# Ingress-Nginx setup
<img width="1146" alt="image" src="https://user-images.githubusercontent.com/75510135/125894727-ab8197dc-03c8-465a-a410-a4df6527de73.png">

<img width="978" alt="image" src="https://user-images.githubusercontent.com/75510135/125895460-abcd79f5-101c-4d85-abad-ca0aac051fb0.png">

```
apiVersion: extensions/v1beta1
kind: Ingress
metadata:
  name: ingress-service
  annotation:
    kubernetes.io/ingress.class: nginx
    nginx.ingress.kubernetes.io/use-regex: 'true'
spec: 
  rules:
    - host: ticketing.dev
      http:
        paths:
          - path: /api/users/?(.*)
            backend:
              serviceName: auth-srv
              servicePort: 3000
 ```
 
 
 <img width="1231" alt="image" src="https://user-images.githubusercontent.com/75510135/125897109-457523b5-ddd1-4fd9-b444-e8cbaf7e27d0.png">



