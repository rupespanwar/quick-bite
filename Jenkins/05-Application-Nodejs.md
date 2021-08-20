<img width="665" alt="image" src="https://user-images.githubusercontent.com/75510135/130104245-70a4a6c0-ec94-4c53-815b-807acf07c13a.png">
<img width="856" alt="image" src="https://user-images.githubusercontent.com/75510135/130104375-75604635-bbc5-41f0-af25-5e99cc6ca620.png">
<img width="879" alt="image" src="https://user-images.githubusercontent.com/75510135/130104453-8e622b69-3384-48c7-9cc4-78245d6d95f7.png">
<img width="871" alt="image" src="https://user-images.githubusercontent.com/75510135/130104847-167e419a-159c-4aa0-845f-ad976a54b24c.png">
<img width="895" alt="image" src="https://user-images.githubusercontent.com/75510135/130105043-48fce2b3-ab2c-4161-ab16-43b51867f173.png">
- sample Nodejs app

<img width="971" alt="image" src="https://user-images.githubusercontent.com/75510135/130105928-7843b95a-5bfd-4381-a9e8-732cebf604ff.png">
- build the application first manually
- click on Manage jenkins
<img width="1127" alt="image" src="https://user-images.githubusercontent.com/75510135/130106204-002a2269-cb90-4544-b706-1be3e10729b0.png">

# configure Jenkins for NodeJs application
- click on Manage Jenkins, then click on Manage Plugins
<img width="985" alt="image" src="https://user-images.githubusercontent.com/75510135/130221994-15ec28ee-7543-4088-b08f-a67ce44e1521.png">

- under Available, search for NodeJs , if not installed else look under Installed
<img width="1079" alt="image" src="https://user-images.githubusercontent.com/75510135/130222145-76afdb3d-8970-4ca3-9828-9cbb21fd18f0.png">
- now click on Global Configuration Tool
<img width="1106" alt="image" src="https://user-images.githubusercontent.com/75510135/130222238-85255b06-6407-4470-b61b-79eaa99fefc5.png">
<img width="1007" alt="image" src="https://user-images.githubusercontent.com/75510135/130222283-d1151579-0f2d-4940-90f1-f18378a82c2c.png">
<img width="853" alt="image" src="https://user-images.githubusercontent.com/75510135/130222332-5256176f-9a76-4017-8e32-28f938ed17bb.png">

# now test 
- click on new item
<img width="1099" alt="image" src="https://user-images.githubusercontent.com/75510135/130222436-ca20e4b5-b239-4cf9-b320-9d81df15748d.png">
- enter item name , select freestyle project
<img width="997" alt="image" src="https://user-images.githubusercontent.com/75510135/130222508-438af8a1-366a-4c3d-9fc9-33f9d154360b.png">
- provide github link(https one)
<img width="948" alt="image" src="https://user-images.githubusercontent.com/75510135/130222691-aa6d92bc-bcfa-4ebe-8654-e1cda7f1d21e.png">
- under Build Environment , select "provide Node & npm bin/folder to Path"
<img width="965" alt="image" src="https://user-images.githubusercontent.com/75510135/130222844-eb59d9d8-a2a1-4897-a13a-079988ddf351.png">
- under Build, select "Execute NodeJs script"
<img width="799" alt="image" src="https://user-images.githubusercontent.com/75510135/130222906-1c9744bc-a804-4cd3-8977-b663422cfa15.png">
- then click on Save 
- click on build now
<img width="724" alt="image" src="https://user-images.githubusercontent.com/75510135/130223010-fd296750-8029-43b4-ba52-8d6a96d13735.png">
- under Build History, click on recent ran job
<img width="306" alt="image" src="https://user-images.githubusercontent.com/75510135/130223324-8f99af33-7737-4832-99ab-d8a91a02049d.png">

- look for Console output for current build
<img width="1100" alt="image" src="https://user-images.githubusercontent.com/75510135/130223250-470ba84d-3155-477d-9324-1dbb998870f9.png">
- under workspace , check the code is pulled from github
<img width="1002" alt="image" src="https://user-images.githubusercontent.com/75510135/130223386-47e521af-c1b5-4c74-9561-b85048012fc0.png">













