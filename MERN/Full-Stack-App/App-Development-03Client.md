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



