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
