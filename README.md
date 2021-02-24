# Docker

---
## BareMetal and VirtualMachine

<img src="BareMetal_VirtualMachine.PNG"/>

---
## VM Creation On Physical Machine or BareMetal

<img src="VMCreationOnPhysicalMachine.PNG"/>

---
## VM Scale Up and Scale Down

<img src="VMScaleUpandScaleDown.PNG"/>

---
## Web Application Deployment

<img src="ApplicationDeployment.PNG"/>

---
## Application Deployment On Different Environments

<img src="ApplicationDeploymentOnDifferentEnvironments.PNG"/>

---
## VM and Containers

<img src="VMandContainers.PNG"/>

---
## Virtualization and Containerization

<img src="VirtualizationandContainerization.PNG"/>

---
## Docker

<img src="Docker.PNG"/>

---
## Docker Products

<img src="DockerProducts.PNG"/>

---
## Docker Installation

<img src="DockerInstallation.PNG"/>

---
## Docker Client Server Architecture

<img src="DockerClientServerArchitecture.PNG"/>

---
## Docker Commands
```
docker images --> to see the local registry images

docker ps --> to see the running containers

docker ps -a --> to see the running and dead(exited) containers

docker pull --> to pull docker image from docker hub or other registry to local registry

docker build --> to build a docker custom image

docker run --> to create a container 

docker search --> to search images from docker cli(Dockerhub)



Docker Root Directory:
/var/lib/docker



docker stop - gracefull
docker kill - forcefull
```
---
## Docker Commands Practice
```
274  docker version
  275  clear
  276  docker --help
  277  clear
  278  docker images
  279  docker run --help
  280  clear
  281  docker run
  282  clear
  283  docker run hello-world
  284  clear
  285  docker images
  286  docker ps
  287  docker ps -a
  288  history
  289  clear
  290  docker run --name helloworld hello-world
  291  docker ps -a
  292  clear
  293  docker ps -a
  294  clear
  295  docker search httpd
  296  clear
  297  docker pull alpine
  298  docker images
  299  clear
  300  docker ps -a
  301  docker run --name satc1 alpine:latest ping google.com
  302  clear
  303  docker run --name satc1 alpine:latest
  304  docker run --name satc2 alpine:latest
  305  docker ps
  306  docker ps -a
  307  clear
  308  cd /var/lib/docker
  309  ls
  310  clear
  311  docker run --name satc3 alpine:latest ping google.com
  312  clear
  313  docker run --name satc3 -d alpine:latest ping google.com
  314  docker run --name satc4 -d alpine:latest ping google.com
  315  clear
  316  docker ps
  317  clear
  318  docker ps
  319  docker exec -it satc4
  320  docker exec -it satc4 /bin/bash
  321  docker exec --help
  322  clear
  323  docker exec -it satc4 /bin/sh
  324  clear
  328  docker ps
  329  docker exec satc5 /bin/sh
  330  clear
  331  docker ps
  332  docker stop satc4
  333  docker ps
  334  docker start satc4
  335  docker ps
  336  clear
  337  docker ps
  338  docker kill satc4
  339  docker ps
  340  docker pause satc5
  341  docker ps
  342  clear
  343  docker unpause satc5
  344  docker ps
  345  docker inspect satc6
  346  clear
  347  docker ps
  348  docker exec -it satc6 /bin/sh
  349  history
  350  docker --help
  351  clear
  352  docker ps
  353  docker ps -a
  354  docker rm satc2
  355  docker ps -a
  356  clear
  357  docker images
  358  docker rmi hello-world
  359  ls
  360  clera
  361  clear
  362  ls
  363  clear
  364  docker images
  365  docker rmi hello-world -f
  366  docker images
  367  clear
  368  history
  210  docker logs satc1
  211  docker logs -f satc1
  212  clear
  213  docker logs -f satc1
  214  clear
  215  docker logs -f satc1

  ```
---
## Create and Connect to Container

<img src="CreateandConnecttoContainer.PNG"/>

---
## Image

<img src="Image.PNG"/>

---
## VM Image vs Docker Image

<img src="VMImagevsDockerImage.PNG"/>

---
## Image for Containers

<img src="ImageforContainers.PNG"/>

---
## Windows Containers Vs Linux Containers

<img src="WindowsVsLinuxContainers.PNG"/>

---
## Parent Process for Container Life Time

<img src="ParentProcessforContainerLifeTime.PNG"/>

---
## Types of Registry

<img src="TypesofRegistry.PNG"/>

---
## Difference between CMD and ENTRYPOINT

- Both CMD and ENTRYPOINT instructions define what command gets executed when running a container. There are few rules that describe their co-operation.

- Dockerfile should specify at least one of CMD or ENTRYPOINT commands.

- ENTRYPOINT should be defined when using the container as an executable.

- CMD should be used as a way of defining default arguments for an ENTRYPOINT command or for executing an ad-hoc command in a container.

- CMD will be overridden when running the container with alternative arguments.

**URL** 
- https://docs.docker.com/engine/reference/builder/#understand-how-cmd-and-entrypoint-interact
- https://phoenixnap.com/kb/docker-cmd-vs-entrypoint#:~:text=CMD%20is%20an%20instruction%20that,container%20with%20a%20specific%20executable.

---
# Application Containerization

<img src="ApplicationContainerization.PNG"/>

---
# Docker Namespaces

<img src="DockerNamespaces.PNG"/>

---
# Image Sharing

<img src="ImageSharing.PNG"/>

---
# Company Private Registry Setup

<img src="Company_PrivateRegistry_Setup.PNG"/>

---
# Application Custom Image Deploy to Diff Environments

<img src="ApplicationCustomImageDeploytoDiffEnvironments.PNG"/>

---
# Create Custom Image and Create Container

<img src="CreateCustomImageandCreateContainer.PNG"/>

---
# Building Custom Image Using Docker Build Command

<img src="BuildingCustomImageUsingDockerBuild.PNG"/>

---
# Map or Publish or Expose Container Port with Host VM Port

<img src="MapContainerPortwithHostVMPort.PNG"/>

---
# Command History
```
  378  cd /usr/local
  379  ls
  380  cd docker_practice/
  381  ls
  382  history
  383  cd /usr/local
  384  ls
  385  cd docker_practice/
  386  ls
  387  cleaer
  388  clear
  389  mkdir httpdapp
  390  cd httpdapp/
  391  cat > httpd.dockerfile
  392  cat httpd.dockerfile
  393  clear
  394  docker build -t sathttpd_img:v1 .
  395  docker build -t sathttpd_img:v1 -f httpd.dockerfile .
  396  clear
  397  vi httpd.dockerfile
  398  docker build -t sathttpd_img:v1 -f httpd.dockerfile .
  399  ls
  400  cat httpd.dockerfile
  401  yum install git -y
  402  clear
  403  ls
  404  cat httpd.dockerfile
  405  mkdir webapp
  406  git clone https://gitlab.com/chinnu1028/beginner-html-site-styled.git
  407  ls
  408  rm -rf webapp/
  409  mv beginner-html-site-styled/ webapp
  410  ls
  411  clear
  412  docker build -t sathttpd_img:v1 -f httpd.dockerfile .
  413  cat httpd.dockerfile
  414  curl ifconfig.io
  415  clar
  416  clear
  417  docker ps
  418  docker ps -a
  419  clear
  420  docker images
  421  docker run --name sathttpdc1 -d sathttpd_img:v1
  422  curl ifconfig.io
  423  cat httpd.dockerfile
  424  docker run --name sathttpdc1 -d -p 80:80 sathttpd_img:v1
  425  docker run --name sathttpdc2 -d -p 80:80 sathttpd_img:v1
  426  docker ps
  427  docker rm sathttpdc1 -f
  428  clear
  429  docker ps
  430  cd ..
  431  ls
  432  mkdir tomcatapp
  433  cd tomcatapp/
  434  cat > Dockerfile
  435  cat Dockerfile
  436  clear
  437  cat Dockerfile
  438  docker ps
  439  cd ..
  440  ls
  441  cd httpdapp/
  442  clear
  443  docke rps
  444  docker ps
  445  docker rm sathhtpdc2
  446  docker rm sathtpdc2
  447  docker rm sathttpdc2
  448  docker rm sathttpdc2 -f
  449  clear
  450  docke rps
  451  docker ps
  452  clear
  453  history
  454  vi httpd.dockerfile
  455  clear
  456  docker build -t sathttpd_test:v1 -f httpd.dockerfile .
  457  docker run --name sathttpdc3 -d sathttpd_test:v1 -p 80:80
  458  docker ps
  459  clear
  460  history
  461  docker run --name sathttpdc3 -d -p 80:80 sathttpd_test:v1
  462  docker run --name sathttpdc4 -d -p 80:80 sathttpd_test:v1
  463  docker ps
  464  clear
  465  cd ..
  466  ls
  467  cd tomcatapp/
  468  ls
  469  git clone https://gitlab.com/chinnu1028/springboot.git
  470  ls
  471  cat Dockerfile
  472  clear
  473  ls
  474  cd springboot/
  475  ls
  476  cd project-java-spring-webapp/
  477  ls
  478  pqd
  479  pwd
  480  cd ..
  481  ls
  482  cd ..
  483  ls
  484  pwd
  485  vi Dockerfile
  486  clear
  487  docker build -t tomcatapp:v1 .
  488  docker run --name sattomc1 -d -p 8080:8080 tomcatapp:v1
  489  curl ifconfig.io
  490  cat Dockerfile
  491  clear
  492  ls
  493  cat Dockerfile
  494  docker ps
  495  docker exec -it sattomc1 /bin/sh
  496  clear
  497  docker ps
  498  docker rm sattomc1
  499  ls
  500  docker rm sattomc1 -f
  501  clear
  502  ls
  503  cd springboot/
  504  ls
  505  cd project-java-spring-webapp/
  506  ls
  507  mv ../../Dockerfile .
  508  ls
  509  clear
  510  pwd
  511  ls
  512  docker images
  513  docker rm sathttpd tomcatapp:v1
  514  docker rm sathttpd tomcatapp:v1 -f
  515  docker rmi sathttpd tomcatapp:v1
  516  ls
  517  docker images
  518  clear
  519  ls
  520  vi Dockerfile
  521  docker build -t tom:v1 .
  522  docker run --name sattomc1 -d -p 8080:8080 tom:v1
  523  docker ps
  524  docker exec -it sattomc1 /bin/sh
  525  clear
  526  ls
  527  pwd
  528  clear
  529  ls
  530  vi Dockerfile
  531  docker images
  532  docker rmi tom:v1
  533  docker rmi tom:v1 -f
  534  ls
  535  docker images
  536  df -h
  537  clear
  538  df -sh
  539  df -h
  540  clear
  541  ls
  542  docker images
  543  docker ps
  544  docker rm sattomc1 -f
  545  clear
  546  ls
  547  docker build -t tom:v1 .
  548  docker run --name sattommc1 -d -p 8080:8080 tom:v1
  549  docke rps
  550  docker ps
  551  docker exec -it sattommc1
  552  docker exec -it sattommc1 /bin/sh
  553  clear
  554  docker ps
  555  docker exec -it sattommc1 sh
  556  clear
  557  docker network
  558  docker network ls
  559  docker network create --help
  560  clear
  561  docker login
  562  docker ls
  563  docker images
  564  ls
  565  clear
  566  docker search alpine
  567  clear
  568  logout
  569  docker logout
  570  clear
```
---

