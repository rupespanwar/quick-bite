# Project Outline
<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126731643-1b238a23-5b35-4b09-931e-cad739bf75bb.png">

<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126731655-667c3114-eda9-477d-8ff3-ad3016d0e6b3.png">

## Node Server Setup
<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126731914-17fc3f92-49de-48cf-a5e6-9d449c4c05c4.png">

<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126732014-ac48108b-bfd8-40d7-8b8f-e8d686a64571.png">

<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126732078-f052c69d-089b-4492-82d3-dad6f22ae46d.png">
### Create Dockerfile
<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126732129-3d81c031-beb9-4bfb-b2ac-3851dcb2b1ca.png">

<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126732308-f382bf99-b665-4c93-a726-16cdf0105dd5.png">

Required WORKDIR update - "Could not detect node name", "idealTree" errors

10-24-2020

The v15 version of Node has recently been released and is causing issues with some of our project code.

In the next lecture you may get the following error when building the Dockerfile:

npm ERR! could not detect node name from path or package

or

npm ERR! idealTree already exists

To resolve this, add a WORKDIR right after the FROM instruction: (we will be adding this very soon anyway)

    FROM node:alpine
     
    WORKDIR /usr/app

Also, you will no longer get the error regarding the missing package.json as shown at around 7:16 in the video. With Node v15 / npm v7, if you run npm install in a directory without a package.json, an empty package.json is now created for you and will no longer throw this error. However, a properly written package.json listing your dependencies is still required to run a Node based application.

<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126736297-7fbb50c0-ff16-47d7-b11b-e30dd9882718.png">

<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126736440-0821d678-4409-4857-9490-290df28e9f4c.png">

<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126736562-151fe661-c03e-4030-b55d-4255b4d6e781.png">

<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126736595-6daa1ffa-2ba2-4703-9830-dd6b727505c6.png">

- build process

<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126736797-aa918438-34a6-4b59-9078-128c28917590.png">

<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126736992-5ab54653-ac80-465a-a4d9-fa45fde19624.png">

<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126737086-83e64885-146b-4f0f-8b14-ecf2faffdd7a.png">

<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126737228-4b450397-34e9-4ae8-90e9-8fba04c244db.png">

#### Container PORT
<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126737460-b8979609-2021-4905-bc9d-685dde6fb2cf.png">

<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126737484-0e82a83d-cf7f-473c-b28c-0e7b8bac1bdb.png">

<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126737606-1440c489-1f1e-4637-bdf5-f0980596ce38.png">

<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126737644-c17b07d1-9691-43a3-b650-a794cee01511.png">

<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126737652-935dd2bf-fd01-47c9-99b8-f16120fae3d1.png">

### WORKING DIR
<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126737947-c26a8b3f-1bbf-4d14-8732-9ff1e5531d41.png">

<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126738269-64203b71-c4db-4c5a-9794-1aaf8f298d45.png">

<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126737957-8612a1a9-081a-413f-81ea-34bcfbe62eb7.png">

<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126738214-76435b7f-22a1-48d1-a06d-69d74724dfdd.png">

### Unnecessary rebuilds - build based on package.json
<img width="1158" alt="image" src="https://user-images.githubusercontent.com/75510135/126738933-73c9731a-9f0c-481a-aeb1-1ff15416b867.png">



