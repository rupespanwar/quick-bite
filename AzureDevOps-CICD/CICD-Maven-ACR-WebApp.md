# Create ACR in portal.azure.com
![image](https://user-images.githubusercontent.com/75510135/129329252-a03d540a-1783-4bf0-a505-75b21ce3d910.png)

# Create Dockerfile in project folder
        FROM openjdk:8-jdk-alpine
        RUN apk add --update ttf-dejavu && rm -rf /var/cache/apk/*
        VOLUME /tmp
        COPY target/backend-0.0.1-SNAPSHOT-spring-boot.jar backend.jar
        #COPY ./email-drafts/ /email-drafts/
        RUN ls -laR /email-drafts/*
        CMD java "-Xms1024M -Xmx2048M"
        EXPOSE 80
        ENTRYPOINT exec java -Xms1024M -Xmx2048M -jar  backend.jar
 
 # push Dockerfile to repo in Az DevOps
 
 # Create Build pipeline (CI)
         trigger:
          branches:
            include:
            - release

        # Variables
        variables:
          tag: '$(Build.BuildId)'

        stages:
        # Build Stage 
          - stage: Build
            displayName: Build Stage
            jobs:
            - job: Build
              displayName: Build Job
              pool:
                vmImage: 'ubuntu-latest'
              steps: 

              - task: Maven@3
                displayName: 'Maven Package'
                inputs:
                  mavenPomFile: 'backend/pom.xml'
                  javaHomeOption: 'JDKVersion'
                  jdkVersionOption: '1.8'
                  jdkArchitectureOption: 'x64'
              - task: CopyFiles@2
                inputs:
                  Contents: '**/target/*.jar'
                  TargetFolder: $(Build.ArtifactStagingDirectory)
                  CleanTargetFolder: true
                  flattenFolders: true

              # Task-1: Build Docker Image and push to Azure Container Registry ACR
              - task: Docker@2
                displayName: Build and push an image to ACR
                inputs:
                  containerRegistry: 'Prod-Acr-Svc-Conn'
                  repository: 'backend-prod'
                  command: 'buildAndPush'
                  Dockerfile: 'backend/dockerfile'
                  tags: '$(tag)'
                    ## Publish Artifacts pipeline code in addition to Build and Push 
              - bash: echo Contents in System Default Working Directory; ls -R $(System.DefaultWorkingDirectory) 

              - bash: echo Before copying Contents in Build Artifact Directory; ls -R $(Build.ArtifactStagingDirectory) 

                # Task-2: Copy files (Copy files from a source folder to target folder)
                # Source Directory: $(System.DefaultWorkingDirectory)/kube-manifests
                # Target Directory: $(Build.ArtifactStagingDirectory)
              - task: CopyFiles@2
                inputs:
                    SourceFolder: '$(System.DefaultWorkingDirectory)'
                    Contents: '**'
                    TargetFolder: '$(Build.ArtifactStagingDirectory)'
                    OverWrite: true
              # List files from Build Artifact Staging Directory - After Copy

              - bash: echo After copying to Build Artifact Directory; ls -R $(Build.ArtifactStagingDirectory) 
                  # Task-3: Publish build artifacts (Publish build to Azure Pipelines) 
              - task: PublishBuildArtifacts@1
                inputs:
                    PathtoPublish: '$(Build.ArtifactStagingDirectory)'
                    ArtifactName: 'maven-prod'
                    publishLocation: 'Container'


# Docker Image will be push and available in ACR
![image](https://user-images.githubusercontent.com/75510135/129329842-ca67a181-a790-4e56-9f78-f5d847b279cd.png)

# Create WebApp using Docker Image
![image](https://user-images.githubusercontent.com/75510135/129329914-b2d3a387-ebdb-4ad8-b21b-51be328119a9.png)

# Now create Release pipeline(CD) to deploy App to WebApp
![image](https://user-images.githubusercontent.com/75510135/129330408-b4aa3c1f-4695-4ddd-8564-5b74a284a58d.png)
![image](https://user-images.githubusercontent.com/75510135/129330475-a7711c69-4760-4902-9f3d-b138807af9ce.png)

        steps:
        - task: AzureRmWebAppDeployment@4
          displayName: 'Deploy BE App To Prod'
          inputs:
            azureSubscription: 'Prod-Arm-Svc-Conn'
            appType: webAppContainer
            WebAppName: 'backend'
            DockerNamespace: azacrdev001.azurecr.io
            DockerRepository: 'prod'
            DockerImageTag: '$(Build.BuildId)'
            
# Application.properties
        server.port=80
        spring.datasource.jdbc-url=jdbc:postgresql://azdev.postgres.database.azure.com:5432/temp_db?currentSchema="shcema_name"
        spring.datasource.driverClassName=org.postgresql.Driver
        spring.jpa.database-platform=org.hibernate.dialect.PostgreSQLDialect
        spring.jpa.show-sql=true

        spring.datasource.hikari.connection-timeout = 20000
        spring.datasource.hikari.minimum-idle= 10
        spring.datasource.hikari.maximum-pool-size= 100
        spring.datasource.hikari.idle-timeout=10000
        spring.datasource.hikari.max-lifetime= 1000
        spring.datasource.hikari.auto-commit =true

        logging.level.com.zaxxer.hikari=DEBUG

        maxAllowedBytes=4194304

        file.upload.path=C:/temp/
        file.uploadDir=C:/temp/
        file.wholesaler.path=C:/temp

        spring.servlet.multipart.max-file-size=50MB
        spring.servlet.multipart.max-request-size=50MB

        jwt.expirationDateInMs=900000
        jwt.refreshExpirationDateInMs=1296000000

        spring.data.rest.enable-enum-translation=true
        spring.jackson.serialization.write-enums-using-to-string=true
        spring.jackson.serialization.fail-on-empty-beans=false
        spring.jackson.deserialization.read-enums-using-to-string=true

        spring.jpa.properties.hibernate.jdbc.lob.non_contextual_creation=true
        azure.blobstorage.default-container=tyreupload
        azure.blobstorage.new-format-file=new-format-files
        azure.blobstorage.old-format-file=old-format-files
        azure.blobstorage.old-format-files-processed=old-format-files-processed

        email.url=https://email.azurewebsites.net/v1/email

        ## Contact Us API ##
        email.api.url=https://email.azurewebsites.net/v1/email
        support.email.address=help@outlook.com

        #OTP expiry in minutes for Forgot Password and Admin Password Reset features
        otp.expiry=60

        excel.rows.read.cache=2000
        excel.rows.write.cache=2000
        ## Azure Key Vault
        azure.keyvault.enabled=true
        azure.keyvault.uri=https://az-kv.vault.azure.net/

        ##Dealer API details
        dealerApi.tokenUrl=http://az-ws-dev.azurewebsites.net:80/user
        dealerApi.url=http://az-ws-dev.azurewebsites.net:80/api/matching/
        ## JWT Cookies
        authentication-test.auth.accessTokenCookieName=AuthToken
        authentication-test.auth.refreshTokenCookieName=RefreshToken
        authentication-test.auth.secure=true

        allowedorigins = ${runtimeAllowedorigins:http://localhost:4200,https://frontend-01.azurewebsites.net,https://backend.azurewebsites.net}
   
   
