# Testing Post-event service via Postman
<img width="730" alt="image" src="https://user-images.githubusercontent.com/75510135/125284159-be935d80-e336-11eb-8a1c-2e6ab1a834ea.png">

<img width="903" alt="image" src="https://user-images.githubusercontent.com/75510135/125284642-5133fc80-e337-11eb-9745-39fa9f9429f0.png">
- Testing

<img width="1339" alt="image" src="https://user-images.githubusercontent.com/75510135/125285775-9efd3480-e338-11eb-9f05-a9b84c428247.png">

<img width="1276" alt="image" src="https://user-images.githubusercontent.com/75510135/125285817-acb2ba00-e338-11eb-86c6-c7cb32499f6b.png">

- check logs
<img width="979" alt="image" src="https://user-images.githubusercontent.com/75510135/125285659-81c86600-e338-11eb-92d8-7e091aca3dd4.png">

# process to update remaining services-components
<img width="893" alt="image" src="https://user-images.githubusercontent.com/75510135/125294986-65c9c200-e342-11eb-9081-b4b7d7dc9924.png">

- Replace localhost to http://event-bus-service:4005 in all remaining components, comments, query, moderation
- build docker image for each of these  [docker build -t rupeshpanwar/comments/query/moderation]
- push each of these docker image       [docker push rupeshpanwar/comments/query/moderation]

# Issue in building the image
- Solution 
- export DOCKER_BUILDKIT=0
  export COMPOSE_DOCKER_CLI_BUILD=0
  
 

