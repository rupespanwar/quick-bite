# GutHub chitsheet
<img width="664" alt="image" src="https://user-images.githubusercontent.com/75510135/127159506-014e5c5b-b937-4765-9775-f0ee5e15bc79.png">

<img width="665" alt="image" src="https://user-images.githubusercontent.com/75510135/127159559-1e0b88d5-7849-4d00-82bc-beb73e5f35d1.png">

<img width="669" alt="image" src="https://user-images.githubusercontent.com/75510135/127159608-72ffc070-4e8d-4750-9a51-da0ffa1fa3a1.png">

<img width="676" alt="image" src="https://user-images.githubusercontent.com/75510135/127159640-877ba675-18fd-40d4-bedd-4be44d065557.png">

<img width="672" alt="image" src="https://user-images.githubusercontent.com/75510135/127159682-a540c337-e3b5-4633-b0ca-ac690f00cfde.png">

# Github Initial setup to commit the code on newly created branch
create a new repository on the command line

echo "# azCli" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/trackscs/azCli.git
git push -u origin main
                
…or push an existing repository from the command line

git remote add origin https://github.com/trackscs/azCli.git
git branch -M main
git push -u origin main

# To revert the branch
https://stackoverflow.com/questions/7099833/how-to-revert-a-merge-commit-thats-already-pushed-to-remote-branch

# Creating remote repositories

You can use the git remote add command to match a remote URL with a name. For example, you'd type the following in the command line:

git remote add origin  <REMOTE_URL> 

# Remote remote repo
git remote remove origin
