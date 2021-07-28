# Deployment Overview
<img width="1177" alt="image" src="https://user-images.githubusercontent.com/75510135/127202383-dbe866e7-fec8-4f0a-8013-99a963729466.png">

# Why GKE
<img width="1177" alt="image" src="https://user-images.githubusercontent.com/75510135/127202963-fbb8a542-74e1-460e-97cc-526531d889d9.png">

# STEP1 make a github repo
<img width="1023" alt="image" src="https://user-images.githubusercontent.com/75510135/127204258-ef4dadd9-6d84-4f17-897a-a39656f25f8b.png">

<img width="808" alt="image" src="https://user-images.githubusercontent.com/75510135/127205907-319c1546-1ffd-4523-9ec7-f139d7d078bb.png">

<img width="953" alt="image" src="https://user-images.githubusercontent.com/75510135/127206001-60bd2703-789c-4628-b709-e4cbc5c5cc58.png">

# STEP2 wire up git repo with Travis ci
<img width="953" alt="image" src="https://user-images.githubusercontent.com/75510135/127206484-ad46d022-9f7d-4649-b112-a90513215d77.png">

<img width="953" alt="image" src="https://user-images.githubusercontent.com/75510135/127206432-c7c3f162-41ae-4aad-b8f2-a2d7f9c78f9f.png">

<img width="953" alt="image" src="https://user-images.githubusercontent.com/75510135/127206578-9fbf9534-8698-479c-a88a-859611135bd1.png">

# STEP3 create GKE, google cloud project
<img width="953" alt="image" src="https://user-images.githubusercontent.com/75510135/127206966-31cc3efe-0b13-441f-9c6f-d23af68051c1.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127207821-e5d91b3c-1b9e-4ccf-bbf7-652e343ad3ec.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127208420-312f0dd3-1585-45e9-8b56-cdb359223ea1.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127242593-a7cd774e-d940-494b-bfde-34de289f6e20.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127242656-0dfb3971-789a-4871-b1de-d168fe0650b6.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127242923-13896b2e-57e7-49ba-a907-1de6cd3ed28b.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127242941-bfd644d3-533e-413f-8bfd-de066bb75cb8.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127242986-81bee97c-f0fa-4af3-9af7-2f6309af7a4e.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127243002-9af93a8d-07bc-4a12-867b-877857518763.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127243290-5017f8e6-1733-4d6b-baff-3487889d69b9.png">

# STEP4 Travis configuation
<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127243717-5b4e675d-5583-4e0e-9759-035dcedcefa0.png">

- install Google cloud CLI 
<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127245201-1cb652d9-d600-4b65-a51c-53a124fae17b.png">
- create service account
<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127245264-ce21ae4d-0b43-4248-992a-5cfe893c1f67.png">
<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127245559-7a0c505c-f692-47a1-b76e-7864efde0aa6.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127245618-b57593ad-9585-4638-8421-7fd37d6e9f79.png">

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/75510135/127245699-a72f2b83-ad99-47dc-a244-002b99bdbf44.png">
<img width="1317" alt="image" src="https://user-images.githubusercontent.com/75510135/127246068-4894c294-2626-49e5-8569-59bd04f1c179.png">

<img width="1317" alt="image" src="https://user-images.githubusercontent.com/75510135/127246086-c6c42949-3e3c-4993-b7cb-717672ba4584.png">

<img width="486" alt="image" src="https://user-images.githubusercontent.com/75510135/127246106-4968e526-89e6-47e1-8ff4-1bde571d0850.png">

- download travis cli
- https://github.com/travis-ci/travis.rb
<img width="1103" alt="image" src="https://user-images.githubusercontent.com/75510135/127246499-cd4ca9a5-e737-4fe0-9033-4288d214ea2b.png">
 - create a docker image to work on secret
<img width="1004" alt="image" src="https://user-images.githubusercontent.com/75510135/127246927-53ff4242-82ad-425b-8a3c-b47969a1a8bf.png">
- then run gem install travis

<img width="1004" alt="image" src="https://user-images.githubusercontent.com/75510135/127247225-a7186d8e-c876-49c5-8c90-7c22878cdf4f.png">

- then type > travis

<img width="1004" alt="image" src="https://user-images.githubusercontent.com/75510135/127247491-d77f36ed-4e23-4b49-bd96-df3bf03783ff.png">

- encrypt the file
<img width="1103" alt="image" src="https://user-images.githubusercontent.com/75510135/127249048-b6ed9f2f-2be5-4b29-8b50-035afcb81d56.png">

- login into Travis using Github token

multi-k8s-prod $ travis login --github-token GIT_HUB_TOKEN --com
Successfully logged in as rupeshpanwar!


- Note
     * travis login --github-token YOUR_PERSONAL_TOKEN --com

   or

    * travis login --github-token YOUR_PERSONAL_TOKEN --pro
    
- travis encrypt-file premium-student-321118-adbe9ed0b7ce.json -r rupeshpanwar/multi-k8s --com

<img width="862" alt="image" src="https://user-images.githubusercontent.com/75510135/127251040-d05ddda0-f42e-432f-a30a-3b603fff1efb.png">
- take the cmd from above step to add into travis file

- openssl aes-256-cbc -K $encrypted_1d15443f7143_key -iv $encrypted_1d15443f7143_iv -in premium-student-321118-adbe9ed0b7ce.json.enc -out premium-student-321118-adbe9ed0b7ce.json -d



