# Dev vs Prod env
![image](https://user-images.githubusercontent.com/75510135/128899868-a355b461-ef04-4c6d-812e-d7d4da6fd184.png)

![image](https://user-images.githubusercontent.com/75510135/128900201-4a5b5a09-cb5f-42e5-a767-b8461283a805.png)

# MongoDB  Production Setup and Configuration

to be creating a separate production database for use with Heroku. Here are the steps required to do this with MongoDB Atlas. (The most important part is the global whitelisting in step 9)

1. Sign in to your MongoDB account

2. Once logged in, you will be taken to your MongoDB Atlas Dashboard. Click the current project button listed under "Context" and click the "New Project" link. As a free tier user, you can have only one cluster per project, however, you can have as many projects as you wish.

3. Name your project and then click the "Next" Button:

4. Click the "Create Project" button:

5. After the project finishes initializing, you will be taken to the "Clusters" page of your Database. Click the "Build a Cluster" button

6. Leave all of the Free Tier options selected and scroll down to the bottom. Click the "Create a Cluster" button:

7. After the Cluster has been created, you will be taken back to the Clusters page of the database. Click the "Connect" button


8. Click the "Add a Different IP Address button:


9. Enter 0.0.0.0/0 into the IP Address field and click the "Add IP Address" button. This part is extremely important as our Heroku server will not be able to connect to our database unless we whitelist all IP addresses.

 - In a real production app, you would typically have a static IP and a Fully Qualified Domain Name. In this case, we would whitelist only the static IP. You can read up on this more here:

 - https://help.heroku.com/JS13Y78I/i-need-to-whitelist-heroku-dynos-what-are-ip-address-ranges-in-use-at-heroku


10. Next, enter a new username and then click the "Autogenerate Secure Password" button. Then click "Create MongoDB User"


11. After the user is created, click the "Choose a Connection Method" button:


12. Select "Connect Your Application"


13. Copy the address under "Connection String Only"

    - When you paste this string into the Heroku Dashboard, you will need to replace <username> and <password> with the actual info created earlier and swap out the <dbname> placeholder with any arbitrary name.

14. Click the "Close" button and head back over to your application.
  

  
# Create DB for prod
![image](https://user-images.githubusercontent.com/75510135/128974922-12c12605-5c82-4929-82bc-712fd1cdde07.png)

# Create API project for prod
![image](https://user-images.githubusercontent.com/75510135/128974970-7f130c2b-b2c3-444d-bdc5-7bc8e7faf89c.png)
![image](https://user-images.githubusercontent.com/75510135/128975140-8496955f-43d9-40e2-9f5a-8e1da676b592.png)

 ![image](https://user-images.githubusercontent.com/75510135/128975422-a0adbac3-6e27-420f-a03d-d537819b3764.png)

 - heroku create
-  https://tranquil-headland-09217.herokuapp.com
-  https://git.heroku.com/tranquil-headland-09217.git
![image](https://user-images.githubusercontent.com/75510135/128975713-558d9869-80ec-4dbb-97ff-19f59cad27e7.png)

# set ENV for dev/prod
 ![image](https://user-images.githubusercontent.com/75510135/128982109-8eab98be-980c-40d3-88b8-077774cb880c.png)

 ![image](https://user-images.githubusercontent.com/75510135/128982149-fa627e17-7f9b-4436-bc0c-c04a33a34ee7.png)

 ![image](https://user-images.githubusercontent.com/75510135/128986143-67ed3155-70e8-4020-b26b-79e01cbbdf97.png)

 # commit the code to HEROKU
         heroku login
         heroku git:remote -a arcane-retreat-68635
         git add .
         git commit -am "make it better"
         git push heroku master
         heroku open
         heroku logs --tail
 ![image](https://user-images.githubusercontent.com/75510135/128993443-e12b744e-de4e-432e-b2a0-8c4cc5ba20dd.png)


 
![image](https://user-images.githubusercontent.com/75510135/128975713-558d9869-80ec-4dbb-97ff-19f59cad27e7.png)
 # set the proxy to true
![image](https://user-images.githubusercontent.com/75510135/129001070-b3d4e1c6-5333-4395-9d0c-7c75d0bfd633.png)
