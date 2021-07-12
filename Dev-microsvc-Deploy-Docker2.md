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
<img width="545" alt="image" src="https://user-images.githubusercontent.com/75510135/125295093-83972700-e342-11eb-8979-903276dafb0b.png">

- Replace localhost to http://event-bus-service:4005 in all remaining components, comments, query, moderation
- build docker image for each of these  [docker build -t rupeshpanwar/comments/query/moderation]
- push each of these docker image       [docker push rupeshpanwar/comments/query/moderation]
- create deployment and Clusterip service to expose the pod to each other
- 
# Issue in building the image
- Solution 
- export DOCKER_BUILDKIT=0
  export COMPOSE_DOCKER_CLI_BUILD=0
  
 <img width="732" alt="image" src="https://user-images.githubusercontent.com/75510135/125296020-7b8bb700-e343-11eb-9604-4a9b4faa328b.png">

<img width="987" alt="image" src="https://user-images.githubusercontent.com/75510135/125297722-1fc22d80-e345-11eb-9fd4-87ad091b3659.png">

<img width="1147" alt="image" src="https://user-images.githubusercontent.com/75510135/125298046-70398b00-e345-11eb-9c99-8e2e3399f796.png">

<img width="1153" alt="image" src="https://user-images.githubusercontent.com/75510135/125299685-00c49b00-e347-11eb-87b2-1d84e9e866ea.png">

- lastly update the Event-bus with new service(clusterip) for remaining components

<img width="935" alt="image" src="https://user-images.githubusercontent.com/75510135/125301087-42a21100-e348-11eb-9c7b-b64fb88db8b4.png">

<img width="501" alt="image" src="https://user-images.githubusercontent.com/75510135/125302157-5306bb80-e349-11eb-9408-168202b0a483.png">

<img width="591" alt="image" src="https://user-images.githubusercontent.com/75510135/125302285-6e71c680-e349-11eb-982d-a1f89fdea635.png">








