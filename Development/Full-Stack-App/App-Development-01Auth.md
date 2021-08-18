# App overview
**https://github.com/rupeshpanwar/React-Nodejs-fullstack.git**
<img width="276" alt="image" src="https://user-images.githubusercontent.com/75510135/128623787-8d718a5b-d500-44c4-9435-29f14f9e0383.png">


<img width="477" alt="image" src="https://user-images.githubusercontent.com/75510135/128623864-2688d4a7-da1b-45f8-a766-308373d511c6.png">

## tools n order
<img width="435" alt="image" src="https://user-images.githubusercontent.com/75510135/128624012-ef3614bb-658d-42c0-9d34-e3c5a8b2cd96.png">

# mockup
<img width="496" alt="image" src="https://user-images.githubusercontent.com/75510135/128624170-82b7f5ef-7f64-4618-b802-45a1a5507d3a.png">

<img width="636" alt="image" src="https://user-images.githubusercontent.com/75510135/128624211-4716dfd0-3c73-436c-8fac-0eec2489da6e.png">

<img width="553" alt="image" src="https://user-images.githubusercontent.com/75510135/128624244-80e19101-6804-430a-9b3a-bbe736fd6014.png">

<img width="812" alt="image" src="https://user-images.githubusercontent.com/75510135/128624254-543b4f21-73e5-4e82-a2f3-980f999a2b0b.png">

<img width="520" alt="image" src="https://user-images.githubusercontent.com/75510135/128624519-38e58ab3-f5c7-458e-a293-46c8cb666ccf.png">

# App architecture and basic React app flow
<img width="364" alt="image" src="https://user-images.githubusercontent.com/75510135/128624672-ccb874cd-2e74-42f4-9f14-19522a7f008f.png">

# Express / node side API [Server]
        cd Full-Stack-App/
        mkdir server
        cd server
        npm init -y
        history
<img width="540" alt="image" src="https://user-images.githubusercontent.com/75510135/128624796-0f49a866-1add-4c1c-a00f-a75f03a39162.png">

* server $ npm i --save express

**? why node n express**
<img width="483" alt="image" src="https://user-images.githubusercontent.com/75510135/128625007-57fecbfc-76c8-4fdd-a7e5-e94aeb6332d9.png">

**Behind the scene**
<img width="536" alt="image" src="https://user-images.githubusercontent.com/75510135/128625068-e8b333cd-4070-4691-8a9a-652bffcdf5ea.png">

## route basics
<img width="736" alt="image" src="https://user-images.githubusercontent.com/75510135/128630231-dd04df72-79b6-4107-a713-a3f45a1c0b6a.png">
<img width="419" alt="image" src="https://user-images.githubusercontent.com/75510135/128630273-627ee38e-7d0c-4eee-8fda-78069a0b08fc.png">




- Generating express app
- test by running > node index.js
## Deploy to Heroku checklist
<img width="479" alt="image" src="https://user-images.githubusercontent.com/75510135/128632720-0a6f104d-aea8-4955-a183-0d61d42fdd66.png">
- spcify node env
<img width="584" alt="image" src="https://user-images.githubusercontent.com/75510135/128633019-d461d9f2-b87b-44a4-9986-9e68e5cae4cb.png">
- specify start script
<img width="559" alt="image" src="https://user-images.githubusercontent.com/75510135/128633087-ad0baa40-7adb-48d3-8ca4-20242a8152a9.png">
- .gitignore
<img width="518" alt="image" src="https://user-images.githubusercontent.com/75510135/128633153-234758d6-29cf-4b8c-99d1-c824b2e21e77.png">

## Heroku CLI deployment
<img width="551" alt="image" src="https://user-images.githubusercontent.com/75510135/128633238-4e5a7092-4538-4100-b648-038a70dcefa9.png">
- Create Heroku account
<img width="1025" alt="image" src="https://user-images.githubusercontent.com/75510135/128633503-c592ad75-0851-4145-a7d0-b2821e2beb47.png">
- commit the code to github
```
                                - install the git first
                                git init
                                git add .
                                git commit -m 'basic setup'
                        - install Heroku CLI and create App
                        - > brew install heroku
                        - > heroku -v
                        - Deploy App with Git
                        - > heroku login
                        - >  $ heroku create
 ```
Creating app... done, ⬢ frozen-scrubland-28418
https://frozen-scrubland-28418.herokuapp.com/ | https://git.heroku.com/frozen-scrubland-28418.git
- git remote add heroku https://git.heroku.com/frozen-scrubland-28418.git
-  Heroku Deploys project
```
                                    git init
                                    heroku git:remote -a frozen-scrubland-28418
                                    git add .
                                    git commit -am 'make it better'
                                    git push heroku master
                                    heroku open
                                    heroku logs
  ```
https://thawing-fortress-96360.herokuapp.com/ 
https://git.heroku.com/thawing-fortress-96360.git

# intro to google auth
<img width="511" alt="image" src="https://user-images.githubusercontent.com/75510135/128638928-776b18d4-67d0-4a34-986b-4943b2b1a88e.png">

<img width="514" alt="image" src="https://user-images.githubusercontent.com/75510135/128638990-e31dcb36-3585-4700-9381-3a7c76dcee0c.png">

<img width="495" alt="image" src="https://user-images.githubusercontent.com/75510135/128639032-00ce4c56-dea5-48ab-a1dc-4af5222b53d7.png">

<img width="726" alt="image" src="https://user-images.githubusercontent.com/75510135/128639076-83fdbf9a-0b90-4225-a4be-353605df5765.png">

<img width="770" alt="image" src="https://user-images.githubusercontent.com/75510135/128639191-f98455f8-0dc5-46b8-94fc-581900eeb7d5.png">
<img width="511" alt="image" src="https://user-images.githubusercontent.com/75510135/128639212-b4de5fe3-0785-4796-89a3-74d574699dc5.png">

# passport js
<img width="714" alt="image" src="https://user-images.githubusercontent.com/75510135/128639278-814c6ec7-655a-4cb2-a27d-af62384f66d6.png">

<img width="445" alt="image" src="https://user-images.githubusercontent.com/75510135/128639336-080313a4-f79a-4048-bcb6-023f8c969495.png">

* <img width="275" alt="image" src="https://user-images.githubusercontent.com/75510135/128649486-1e9477c9-0c08-4e6a-bdf3-50ca97466ba9.png">

# passport setup
* $ npm i --save passport passport-google-oauth20
<img width="528" alt="image" src="https://user-images.githubusercontent.com/75510135/128650706-fbf8e6c1-a178-4532-8eff-9621e4a566a6.png">

* create client id 
* login into https://console.cloud.google.com
<img width="909" alt="image" src="https://user-images.githubusercontent.com/75510135/128651264-c57ee31e-a1b2-4b39-8255-a8d387836815.png">
<img width="565" alt="image" src="https://user-images.githubusercontent.com/75510135/128651286-a6ed76bb-7c66-4649-b7fb-cf72efa43e4f.png">
<img width="981" alt="image" src="https://user-images.githubusercontent.com/75510135/128651310-4d6aca7f-bb84-4c9c-a45a-2ac118e0f0ad.png">
<img width="801" alt="image" src="https://user-images.githubusercontent.com/75510135/128651336-1137d513-9308-4f05-8db6-b503d16439cc.png">
<img width="1132" alt="image" src="https://user-images.githubusercontent.com/75510135/128651370-1fad2f9d-3a3a-4743-ba37-c23e75a83b05.png">

<img width="1127" alt="image" src="https://user-images.githubusercontent.com/75510135/128651464-c1cd5df0-e773-40b3-86c2-a7b449429556.png">
<img width="1132" alt="image" src="https://user-images.githubusercontent.com/75510135/128651479-fcc5971a-f0a6-4642-b75c-be748636ebea.png">
<img width="880" alt="image" src="https://user-images.githubusercontent.com/75510135/128651593-299b4f03-8814-4fe1-a9ef-0a29d884ae98.png">
<img width="788" alt="image" src="https://user-images.githubusercontent.com/75510135/128651649-9d327b0b-bb20-497c-93bb-fbcbd5e5a0d1.png">
<img width="1128" alt="image" src="https://user-images.githubusercontent.com/75510135/128651690-d8230179-74a1-4a07-8ae4-5403cd98058e.png">

## Client ID
<img width="472" alt="image" src="https://user-images.githubusercontent.com/75510135/128656982-7e6dc678-5b65-44e7-a5b8-ad450bca6482.png">
<img width="388" alt="image" src="https://user-images.githubusercontent.com/75510135/128657476-ce34aabb-c5cd-4699-b794-f330651d3df1.png">
<img width="417" alt="image" src="https://user-images.githubusercontent.com/75510135/128657516-48955e43-8e82-49ba-b6ce-e7f134109770.png">

## BHS(behind the scene
<img width="590" alt="image" src="https://user-images.githubusercontent.com/75510135/128657153-c5f9f1eb-9795-4e8a-902e-338414e68544.png">


### consume google cliend ID now
<img width="587" alt="image" src="https://user-images.githubusercontent.com/75510135/128659311-96c59b74-df94-41dc-92f9-8cffdc17b8b9.png">

**https://github.com/rupeshpanwar/React-Nodejs-fullstack.git**

* Test by http://localhost:5000/auth/google

<img width="666" alt="image" src="https://user-images.githubusercontent.com/75510135/128660232-40282a93-dc56-4efc-8865-fce8d228c9a6.png">
<img width="1041" alt="image" src="https://user-images.githubusercontent.com/75510135/128662726-5b9d843d-c75c-4aaf-b0ef-e7858e5f30fa.png">

                                https://accounts.google.com/o/oauth2/v2/auth/oauthchooseaccount?response_type=code&
                                redirect_uri=http%3A%2F%2Flocalhost%3A5000%2Fauth%2Fgoogle%2Fcallback&
                                scope=profile%20email&client_id=85941131422-c7vm8p4f4q94edn7qpahdhutj3m5eaq5.apps.googleusercontent.com&
                                flowName=GeneralOAuthFlow
                               
                               
## complete the loop back for google oauth
<img width="830" alt="image" src="https://user-images.githubusercontent.com/75510135/128664007-b55e0308-ef3f-4b17-ba1c-373833f3d24a.png">

<img width="730" alt="image" src="https://user-images.githubusercontent.com/75510135/128664000-34feac3c-4277-4c10-b148-e6330df761b5.png">

## extract user profile information to submit to DB
<img width="830" alt="image" src="https://user-images.githubusercontent.com/75510135/128665323-3331353a-cbaa-40be-bff5-521a78103ded.png">

#####################################################################
## Nodemon setup
* npm i --save nodemon
* npm run dev
<img width="512" alt="image" src="https://user-images.githubusercontent.com/75510135/128665857-3fd087ec-129d-467f-8801-7ee0910a191b.png">


#####################################################################
## Server structure refactor
<img width="466" alt="image" src="https://user-images.githubusercontent.com/75510135/128666105-2d63ff77-ad15-42c2-9aca-94e63dccae20.png">
<img width="867" alt="image" src="https://user-images.githubusercontent.com/75510135/128676053-95bcf9c5-e440-4278-a71a-7d22ed6ef367.png">
#####################################################################
## Authentication mechanism
<img width="503" alt="image" src="https://user-images.githubusercontent.com/75510135/128679064-da5f0f6f-7b45-462a-b50d-8b7ef540b2f1.png">

<img width="612" alt="image" src="https://user-images.githubusercontent.com/75510135/128677467-0f29e744-05df-4d4c-a71d-9e6aeec5311d.png">

<img width="640" alt="image" src="https://user-images.githubusercontent.com/75510135/128677663-9d88b6d3-6c90-4582-b52a-26fce179e002.png">

* cookie based authentication

<img width="616" alt="image" src="https://user-images.githubusercontent.com/75510135/128678246-18a180e6-52e9-4a8b-aa8b-5960cc8b887f.png">

### Sign in User with oauth

<img width="598" alt="image" src="https://user-images.githubusercontent.com/75510135/128687108-8013fc06-6024-4219-8fca-1ab6ce1e28f9.png">

<img width="346" alt="image" src="https://user-images.githubusercontent.com/75510135/128687170-b71965c8-65af-4446-99a0-1d7165bf097f.png">

<img width="316" alt="image" src="https://user-images.githubusercontent.com/75510135/128688290-c3caf425-1c98-47ba-8fd3-6f432c0ef020.png">

<img width="830" alt="image" src="https://user-images.githubusercontent.com/75510135/128690082-5e892b09-df88-4160-b2d1-33128322a723.png">

### BHS
![image](https://user-images.githubusercontent.com/75510135/128690619-90784a50-3fc4-49e3-b535-0cc1aff5c3fc.png)

#
#####################################################################
## Mongo DB
![image](https://user-images.githubusercontent.com/75510135/128693749-fb44a369-16c3-4aee-b531-a9fdbc5fdb57.png)
### BHS
![image](https://user-images.githubusercontent.com/75510135/128696641-cfbc8521-e3f1-4e71-8347-5b94df66b15f.png)
![image](https://user-images.githubusercontent.com/75510135/128697081-0603f661-40c3-4c36-a423-7e44e9da81ba.png)

## Create MongoDB cluster
- https://cloud.mongodb.com

1.  Go to https://www.mongodb.com/cloud/atlas and click the "Start Free" button (or Sign In if you already have account)
2.  Create your MongoDB user account
3.  After creating your account, you will be prompted to create your first cluster.
Leave all free tier options selected - AWS, North America: N. Virginia etc.
4. Scroll down on this page to name your app:
5. Click the "Create Cluster" button:
6.  The cluster will take a few minutes or more to generate, eventually you will see a page like this:
7. Click the "CONNECT" button in your cluster's sandbox.  You will get the following screen asking you to whitelist your address.
Click the "Add your Current IP Address" button.
8. You will then need to create a database user and password - I would highly suggest using the "Autogenerate" button to avoid escaping issues.
After doing so, click the "Create MongoDB User" button.
9.  After creating the user, you should get this success dialog box. Click the "Choose a connection method" button.
10. Select "Connect Your Application"
11. Copy the address under "Connection String Only"
When you paste this string into your application, you will need to replace <username> and <password> with the actual info created earlier and swap out the <dbname> placeholder with any arbitrary name.
Click the "Close" button and head back over to your Emaily application.
12.  In your config/keys.js file create the mongoURI key-value pair if you haven't already done so.
Remember the comma if adding in-between other key-value pairs:

                                      googleClientID: 'redacted',
                                      googleClientSecret: 'redacted',
                                      mongoURI: '',
                                      cookieKey: 'redacted',

                                Add the connection string by pasting the entire SRV address string you copied in the screen before.
                                Remember to replace <username> with the user's actual username.
                                Remember to replace <password> with the user's actual password
                                Remember to replace <dbname> with any name you'd like.
                                mongoURI: 'COPY_THE_SRV_ADDRESS_STRING_HERE'
                                example:
                                mongoURI: 'mongodb+srv://p00gz:0JYnugifgjsP9UD6@emaily-uwsj6.mongodb.net/test?retryWrites=true'
                                Your root index.js connect function should still look like this:
                                mongoose.connect(keys.mongoURI);
                                Restart your Node server if you have not already done so.
13. In a few lectures, you will be testing adding users to your database cluster.
To see these results, navigate back to your cluster's dashboard and click the 'emaily' project link:
14. Select the 'Collections' tab:
15. You should see the collection of users and user objects that have successfully authenticated to your app:

![image](https://user-images.githubusercontent.com/75510135/128802679-d52d481e-8537-457a-98f5-958b7beee327.png)

        
        
### Connect mongoose to Mongo db
    - npm i --save mongoose
- Change your connect method to look like this:
![image](https://user-images.githubusercontent.com/75510135/128803798-4bee4ab2-2424-4a3b-b97c-25157069ce65.png)
![image](https://user-images.githubusercontent.com/75510135/128804596-32934ca6-ee56-4bff-ae31-b87100068279.png)
**BTS**
        ![image](https://user-images.githubusercontent.com/75510135/128804757-e12d7e45-9c68-461f-a724-3ccfcc943f1b.png)
![image](https://user-images.githubusercontent.com/75510135/128805067-4dad3f15-d19a-4b5f-af34-e14338d1379b.png)
## Create User model
        ![image](https://user-images.githubusercontent.com/75510135/128807288-2115b959-c71f-4bc4-b20f-900ca7faadd7.png)
![image](https://user-images.githubusercontent.com/75510135/128807411-95bd869c-f464-4ed6-b127-3107851339d1.png)
## saving the model/users
![image](https://user-images.githubusercontent.com/75510135/128808870-8deadf1d-296c-4459-b964-749ceff4008c.png)

![image](https://user-images.githubusercontent.com/75510135/128808917-6ddd7679-caf2-4dd2-a507-59a4572e578c.png)

![image](https://user-images.githubusercontent.com/75510135/128808959-4509efa2-de6b-4af0-baf7-8baf8684596d.png)

## Check if User exists during oAuth
![image](https://user-images.githubusercontent.com/75510135/128837379-a4cfae83-32d4-4a04-addf-e2c1eef7fe67.png)

![image](https://user-images.githubusercontent.com/75510135/128841124-eb7e4db8-8fae-4352-b5c3-89ebe6431c5d.png)

## Passport call back
![image](https://user-images.githubusercontent.com/75510135/128841605-f662363d-3ddf-4422-b414-d92626d1b45e.png)

 ![image](https://user-images.githubusercontent.com/75510135/128842939-0495ec0a-d0b8-4c68-b9e5-77dc837a4d65.png)

## Encoding users -- SETUP COOKIE
![image](https://user-images.githubusercontent.com/75510135/128853806-00c545c4-ad5f-4298-84ee-99b7f23e8cd8.png)
![image](https://user-images.githubusercontent.com/75510135/128854141-2f1bd825-4229-4834-afb8-7c282032bc1c.png)

![image](https://user-images.githubusercontent.com/75510135/128856153-62d8f38c-4a49-4347-b1a9-9b2e9043d4af.png)
![image](https://user-images.githubusercontent.com/75510135/128858602-8f4eac4d-6414-49a2-9564-095ac2eaf97a.png)
### Enabling cookie
 - npm i --save cookie-session
![image](https://user-images.githubusercontent.com/75510135/128861491-80130ed5-4def-4c0d-9c7a-ebde93fb35b2.png)

![image](https://user-images.githubusercontent.com/75510135/128863135-193042ad-0449-491d-89c5-a98f7e1d5c73.png)

#####################################################################
## User logout
![image](https://user-images.githubusercontent.com/75510135/128880136-2f672406-589a-4422-8e87-cd35c6cb4889.png)


#####################################################################
## optional
## Middleware
![image](https://user-images.githubusercontent.com/75510135/128880547-d7f63749-068a-4a5f-889a-3fa47f5ad792.png)
![image](https://user-images.githubusercontent.com/75510135/128880861-3e8b9408-f079-467c-816d-ca2bdf925086.png)
![image](https://user-images.githubusercontent.com/75510135/128882312-b803cabe-6654-4afd-b222-d40510f15be6.png)
![image](https://user-images.githubusercontent.com/75510135/128882873-e272f246-0f64-4c7d-821d-804719ac1c43.png)

### Auth workflow
![image](https://user-images.githubusercontent.com/75510135/128883914-29378b21-0a74-435b-b376-352f8438f399.png)
![image](https://user-images.githubusercontent.com/75510135/128883982-3bc1e37a-2914-4d48-b41e-666462857182.png)
![image](https://user-images.githubusercontent.com/75510135/128884053-b47f0a43-8fb4-4af4-bb0e-8175205a58a7.png)

![image](https://user-images.githubusercontent.com/75510135/128883764-5dc606c6-e440-49cd-b2db-8da8ddb981a7.png)

        
        
        






