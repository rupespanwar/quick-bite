# App overview
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
Creating app... done, ⬢ frozen-scrubland-28418
https://frozen-scrubland-28418.herokuapp.com/ | https://git.heroku.com/frozen-scrubland-28418.git
- git remote add heroku https://git.heroku.com/frozen-scrubland-28418.git
-  Heroku Deploys project
            git init
            heroku git:remote -a frozen-scrubland-28418
            git add .
            git commit -am 'make it better'
            git push heroku master
            heroku open
            heroku logs











