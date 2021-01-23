# GIT

---
## DistributedGIT

<img src="DistributedGIT.PNG"/>


---
**BranchingStrategy**

<img src="BranchingStrategy.PNG"/>


---
#GITWorkFlow

<img src="GITWorkFlow.PNG"/>


---
#GIT Architecture

<img src="GIT_Architecture.png"/>

----
#Working on GITHUB repository:

SSH key create and upload:
1. create ssh key using gitbash client
2. upload ssh key to github server

Create a Test Repository, Download to local Repository and Upload to Remote Repository:
1. create repository "TEST" in github server
2. copy ssh url of TEST repository from github server
3. create a folder (portal) in your laptop home directory(c:/users/username) 
4. open git bash client
5. go to portal path (newly created folder - look at 3rd step)
6. use git clone command to get remote repository into local repository 
7.    ex: git clone git@github.com:chinnu1028/TEST.git
8. using following url go to github page and download zip file(please see the snapshot below)
9. extract or unzip the downloaded folder
10. copy and paste all the files and folders from extracted Folder(maven-project2-master) to portal directory(which is created in 3rd step)
11. git status (it shows unstaged changes) 
12. git add . (this command will add all the files and folders from working directory to staging area)
13. git status (it shows staged changes)
14. git commit -m "added files and folders" (it saves all the changes from staging to local repository)
15. git push ( it upload all added files from local repository to remote repository)
16. go to github check the TEST repository, now you see the uploaded files and directories.



