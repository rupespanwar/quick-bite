# npx Create React App Generation

Instead of this:

npm install -g create-react-app

create-react-app client

Just do this:

npx create-react-app client

Official docs on CRA usage with npx are available here:

https://create-react-app.dev/docs/getting-started#quick-start

![image](https://user-images.githubusercontent.com/75510135/129002635-3c74aabb-aebb-400c-bb48-b48dcfee2688.png)
        Inside that directory, you can run several commands:

          npm start
            Starts the development server.

          npm run build
            Bundles the app into static files for production.

          npm test
            Starts the test runner.

          npm run eject
            Removes this tool and copies build dependencies, configuration files
            and scripts into the app directory. If you do this, you can’t go back!

        We suggest that you begin by typing:

          cd client
 
 # 2 servers
 ![image](https://user-images.githubusercontent.com/75510135/129008006-bb195116-eeb9-47e5-8a42-17b1c44c8155.png)

- npm start 
![image](https://user-images.githubusercontent.com/75510135/129008640-b4ca26cf-6452-4943-b75c-028cb4c5cfb9.png)

# Running both server => client / Server 
![image](https://user-images.githubusercontent.com/75510135/129010889-86580962-a137-4257-8432-a0786ad1c171.png)

- npm i --save concurrently
- npm run dev
# Create React App Proxy Update


Adding a proxy to our client-side package.json file. Create React App has since changed how this works and we no longer need to do this step. Instead, we need to create a special file to hold our proxy code.

1. In the client/ directory install the http-proxy-middleware library:

Important - We must install the latest 1.x.x release of this library. Go to the releases page here: 

https://github.com/chimurai/http-proxy-middleware/releases

Find the latest 1.x.x version and install that specific version.

eg:

npm install http-proxy-middleware@1.0.6

2. Create a setupProxy.js file in the client/src/ directory. There is no need to import this file anywhere, CRA looks for a file by this name and loads it.

3. Add your proxies to the setupProxy.js file:

            const { createProxyMiddleware } = require("http-proxy-middleware");
            module.exports = function (app) {
              app.use(
                ["/api", "/auth/google"],
                createProxyMiddleware({
                  target: "http://localhost:5000",
                })
              );
            };

4. Restart start your servers with npm run dev and the proxies should now work as expected. Note - anytime you make a change to the setupProxy file you'll need to restart your server.

Make sure you don't add the proxy configuration to the package.json file as shown in the video lectures. If you do, you'll get the following error:

[1] When specified, "proxy" in package.json must be a string.

[1] Instead, the type of "proxy" was "object".

[1] Either remove "proxy" from package.json, or make it a string.

***Do not add changeOrigin: true to your proxy script, it will completely break our redirects!***

![image](https://user-images.githubusercontent.com/75510135/129011853-87b9b579-8d53-4e39-a0bc-40d2a7513ab5.png)

![image](https://user-images.githubusercontent.com/75510135/129011889-8c94db94-e772-442f-a952-17a0d519e9d2.png)
# Setup proxy at frontend(client)
![image](https://user-images.githubusercontent.com/75510135/129028709-8bb66181-01b9-49e0-9238-c6f32e716b3c.png)
![image](https://user-images.githubusercontent.com/75510135/129028781-efbc26c4-a196-488c-ab46-398236611cc9.png)
![image](https://user-images.githubusercontent.com/75510135/129028876-87c3f8f3-80ff-4665-b30e-d234cc3e238a.png)

![image](https://user-images.githubusercontent.com/75510135/129193711-86a59a65-722e-437a-956d-225dedeb8fbf.png)
![image](https://user-images.githubusercontent.com/75510135/129194567-43ff8d32-cf26-4021-9df3-93b2ab0e78ab.png)
![image](https://user-images.githubusercontent.com/75510135/129194821-64cbc9d4-cca3-4600-99ca-767512d62d53.png)
# Why this architechture => BTS
![image](https://user-images.githubusercontent.com/75510135/129196170-d067f823-b379-4346-966a-db898556afed.png)
![image](https://user-images.githubusercontent.com/75510135/129196266-b60304a5-3d51-4735-82ed-f939709067c0.png)
![image](https://user-images.githubusercontent.com/75510135/129198006-79ced26e-29d7-492c-aea8-0cbefde88a52.png)
![image](https://user-images.githubusercontent.com/75510135/129200330-db1dc5ca-1981-46e5-8dbf-a58953283392.png)
![image](https://user-images.githubusercontent.com/75510135/129200504-5b53dfe6-654c-4543-b974-9944a348cbe7.png)
![image](https://user-images.githubusercontent.com/75510135/129201897-64190f58-7784-4f30-b413-9659af9689fe.png)
![image](https://user-images.githubusercontent.com/75510135/129202508-2e71e7f8-7e7b-4cba-a124-b692d7852317.png)

![image](https://user-images.githubusercontent.com/75510135/129202220-1054b403-6d63-4508-ac97-c0b0b7836079.png)
![image](https://user-images.githubusercontent.com/75510135/129202469-54842cb0-4def-44c2-8007-e6deb5067fb1.png)

**Async Await*********
![image](https://user-images.githubusercontent.com/75510135/129207192-1f125921-51b0-489e-b3cf-e2f1852bc56e.png)
![image](https://user-images.githubusercontent.com/75510135/129207282-9f10067e-7dc5-4abe-93bd-160b13d4b2dc.png)
![image](https://user-images.githubusercontent.com/75510135/129208979-ebdfbfe7-f029-45b0-bf4c-ec7cc84a9571.png)
![image](https://user-images.githubusercontent.com/75510135/129209386-ca06c9f9-897a-4021-926a-50159f5c23ac.png)
- babeljs.io
![image](https://user-images.githubusercontent.com/75510135/129446788-c99d8a23-61ba-4472-8b3e-533fa9e96d5b.png)
# Frontend Tech-flow, GReen => backend , Blue => Frontend
![image](https://user-images.githubusercontent.com/75510135/129446807-a159ef55-38c7-4dc8-871f-a92f60721115.png)
![image](https://user-images.githubusercontent.com/75510135/129446870-84734340-174c-41d4-a8e8-1033a8716fdd.png)
![image](https://user-images.githubusercontent.com/75510135/129446893-63a51c2b-c6c3-4be9-97a1-5c903f623437.png)
![image](https://user-images.githubusercontent.com/75510135/129446904-d862f99a-7858-48f3-93da-7dd14e256a64.png)
# Client React setup, Redux, React-router
- Delete default files
![image](https://user-images.githubusercontent.com/75510135/129447115-3aeb58d4-a99a-4e32-b89a-6fe86ee8b727.png)
![image](https://user-images.githubusercontent.com/75510135/129447164-9c34f19b-c99a-4ead-87ac-9e1e3a67582c.png)
![image](https://user-images.githubusercontent.com/75510135/129447403-38b16007-fcfa-44eb-8fa2-ecdb058b7e99.png)
- npm i --save redux react-redux react-router-dom

![image](https://user-images.githubusercontent.com/75510135/129448307-338fb51a-fa88-4e25-9009-aac48307aa6f.png)
![image](https://user-images.githubusercontent.com/75510135/129448312-0e4892d9-dc01-47df-8d8b-464ff2b43806.png)

# Redux setup
![image](https://user-images.githubusercontent.com/75510135/129448444-de42cf0e-19ad-4775-b10e-ea2ebb2f2544.png)
![image](https://user-images.githubusercontent.com/75510135/129448464-cbe182ad-b2f3-47f8-bfb9-2a1943252050.png)
![image](https://user-images.githubusercontent.com/75510135/129448488-1695c8a0-e926-4371-8b1b-14c8b89aa334.png)
![image](https://user-images.githubusercontent.com/75510135/129448558-c6dd011c-1066-40f0-a400-5aacaf1fb42b.png)
![image](https://user-images.githubusercontent.com/75510135/129448797-fbf6a733-00a8-45e0-8aea-30e98f6e82c3.png)






