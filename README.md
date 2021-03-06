# LINUX
---
File Management:
---
Linux Directory structure or File Hirarchy:
```
/
 - bin (linux operating system and commands)
 - sbin
 - home/ec2-user, satish
 - opt
 - root - root user (administrator user in windows)
 - usr/local/satish/raju
 - var
 - tmp/
```
Linux Files/Folder Path types:
```
. --> current directory
ex: ls .

complete path or absolute path:
ex: cp /usr/local/satish/raju /tmp
    ls /usr/local/satish

relative path:
ls satish/raju
```
**cp command**
```
syntax:
cp options sourcelocation destinationlocation

cp -r 
1. copy files
2. copy folders or directories
```
**create files and write content**
```
cd - --> to go back to previous directory
touch --> to create a file 
cat, vi --> to create files and also write content
:wq! - save and exit
```
```
Linux:
files(filecontent)
folders

mv --> rename or move from one location to another location

rm --> delete files and folders
 - delete files ex: rm -rf filename
 - delete folder ex: rm -rf directoryname
 
```
**commands**
```
   25  ls
   26  cd /usr/local
   27  ls
   28  mkdir satish
   29  ls
   30  cd satish
   31  clear
   32  ls
   33  mkdir jaggu raju
   34  ls
   35  touch new.txt new2.txt new3.txt
   36  ls
   37  clea
   38  clear
   39  pwd
   40  ls
   41  cp /usr/local/satish/raju /tmp
   42  cp --help
   43  clear
   44  cp -r /usr/local/satish/raju /tmp
   45  cd /tmp
   46  ls
   47  clear
   48  cd -
   49  clear
   50  ls
   51  ls --help
   52  clear
   53  ls
   54  ls -l
   55  date
   56  cat > new2.txt
   57  clear
   58  ls -l
   59  date
   60  ls -lr
   61  ls -lt
   62  touch .file.txt
   63  clear
   64  ls
   65  ls -a
   66  mkdir .dir
   67  ls
   68  ls -a
   69  pwd
   70  clear
   71  ls
   72  cat > file2.txt
   73  ls
   74  cat file2.txt
   75  cat new3.txt
   76  clear
   77  ls
   78  vi new.txt
   79  ls
   80  cat new.txt
   81  clear
   82  ls
   83  mv new3.txt satish.txt
   84  ls
   85  clear
   86  ls
   87  rm new.txt
   88  ls
   89  rm -f new.txt
   90  ls
   91  rm jaggu
   92  rm -r jaggu
   93  rm -rf jaggu
   94  clear
   95  ls
   96  rm -rf file2.txt
   97  ls
   98  rm -rf raju
   99  ls
  100  rm satish.txt
  101  rm -f satish.txt
  102  ls
  103  clear
  104  pwd
  105  cd ~
  106  pwd
  107  cd -
  108  clear
  109  ls
  110  pwd
  111  cd ..
  112  ls
  113  pwd
  114  ls satish/
  115  ls /usr/local/satish
  116  .
  117  clear
  118  ls
  119  ls .
  120  ls satish/
  121  ls /usr/local/satish
  122  pwd
  123  .
  124  clear
  125  ls
  126  cd satish
  127  ls
  128  clear
  129  cd /tmp
  130  ls
  131  cd raju/
  132  ls
  133  pwd
  134  mkdir satish
  135  ls
  136  pwd
  137  mkdir /tmp/jaggu
  138  ls
  139  cd ..
  140  ls
  141  clear
  142  pwd
  143  ls
  144  cd raju/
  145  ls
  146  cd satish/
  147  pwd
  148  cd ..
  149  pwd
  150  clear
  151  ls
  152  cd satish/
  153  ls
  154  pwd
  155  cd ../..
  156  pwd
  157  cd raju/satish
  158  pwd
  159  cd ../..
  160  cd raju/satish
  161  pwd
  162  cd ../../..
  163  pwd
  164  history
  165  clear
  166  history
```
---




## USERS and GROUPS
---
```
**Types of user accounts in Linux**
  
  - Root user - (root user has all permissions)
  - Sudo user -(sudo user will have some of the root permissions but not all)
  - Non sudo user - (will have minimal permissions)

**Commands**
  
  - Sudo -i                           ---> to log in to root user
  - Sudo -su username                 ---> to log in to sudo user
  - Su username                       ---> to switch between the users (non sudo users) (root or sudo user can use this command)
 
**Note:**
  
  1. sudo user is not equal to root user.
  2. normal users cannot login to other user accounts.
```
---
## convert non-sudo user to sudo user
```
# add the non-sudo user to wheel group
  usermod -aG wheel non-sudouser

# add the non-sudo user to /etc/sudoers file
 sudo vi /etc/sudoers
 
# find the below line and uncomment it 
 %wheel ALL=(ALL)       NOPASSWD: ALL
```
---
**Examples**
```
# create a user --> useradd username
# change password --> passwd username
# delete user --> userdel username
# create a group --> groupadd groupname
# delete a group --> groupdel groupname
# create a user with existing group --> useradd -g users username 
# add existing user to existing group --> usermod -aG wheel username
```
---
## Important Commands
```
# netstat -anp | grep java/httpd/nginx   --> to check the port number of a application
# ps -ef | grep java    --> to check java process 
# sudo systemctl start servicename    --> to start a service
# sudo systemctl stop servicename    --> to stop a service
# sudo systemctl restart servicename    --> to restart a service
# sudo systemctl status servicename    --> to see the status of a service
# chmod 777 foldername/folderpath    --> to give permission to a folder
# sudo -su sudousername    --> to switch to sudo user
# sudo -i     --> to switch to root user
# top     --> to check the CPU usage
# find /etc -type f -name *filename*    --> to find the file localtion in etc folder
# grep -lr 80 /etc    --> to get the list of filename which have 80 word inside.
# id username    --> command to check a user uid, gid and groups list 

```
---
## DNS (Domain Name System/Server)

<img src="DNS.PNG"/>

---
## Variables
These are nothing but memory spaces and which will be used to store human readable format data or values inside and recall them using $ symbol whenever required.

**Types Of Variables**
<img src="Variables.PNG"/>

---
