# KUBERNETES
---
## Problems In Container Based Application Hosting

<img src="ProblemsInContainerBasedApplicationHosting.PNG"/>

---
## Container Orchestration Tools

<img src="ContainerOrchestrationTools.PNG"/>

---
## Kubernetes_Manager

<img src="Kubernetes_Manager.PNG"/>

---
## Kubernetes_Basic_Architecture

<img src="Kubernetes_Basic_Architecture.PNG"/>

---
## K8s_Introduction

<img src="K8s_Introduction.PNG"/>

---
## K8s_Architecture

<img src="K8s_Architecture.PNG"/>

---
## K8s_Networking

<img src="K8s_Networking.PNG"/>

---
## K8s_Networking_Detailed

<img src="K8s_Networking_Detailed.PNG"/>

---
## K8s_Keywords

<img src="K8s_Keywords.PNG"/>

---
## k8s_master

<img src="k8s_master.PNG"/>

---
## k8s_minionnode

<img src="k8s_minionnode.PNG"/>

---
## K8s_Architecture_Cluster

<img src="K8s_Architecture_Cluster.PNG"/>

---
## POD

<img src="POD.PNG"/>

---
## POD_Detailed

<img src="POD_Detailed.PNG"/>

---
## Replication_Controller

<img src="Replication_Controller.PNG"/>

---
## Replication_Controller2

<img src="Replication_Controller2.PNG"/>

---
## k8s_Cluster_Deployment

<img src="k8s_Cluster_Deployment.PNG"/>

---
## POD_Creation_Workflow

<img src="POD_Creation_Workflow.PNG"/>

---
## DockerVsK8s

<img src="DockerVsK8s.PNG"/>

---
## DockerComposeVsKubectl

<img src="DockerComposeVsKubectl.PNG"/>

---
## k8s_Architecture3

<img src="k8s_Architecture3.PNG"/>

---
## K8s_Architecture4

<img src="K8s_Architecture4.PNG"/>

---
## K8s_Architecture5

<img src="K8s_Architecture5.PNG"/>

---
## IntroductionToK8sService

<img src="IntroductionToK8sService.PNG"/>

---
## ServiceandLabels_Insights2

<img src="ServiceandLabels_Insights2.PNG"/>

---
## ServiceandLabels_Insights

<img src="ServiceandLabels_Insights.PNG"/>

---
## k8s_ServiceTypes

<img src="k8s_ServiceTypes.PNG"/>

---
## k8s_Cluster_setup_KUBEADM

<img src="k8s_Cluster_setup_KUBEADM.PNG"/>

---
## MINIKUBE Cluster Installation and Setup (Single Node Cluster)
```
# Minikube Installation URL's:
Link1: https://minikube.sigs.k8s.io/docs/start/
Link2: https://minikube.sigs.k8s.io/docs/drivers/docker/
Link3: https://www.digitalocean.com/community/questions/how-to-fix-docker-got-permission-denied-while-trying-to-connect-to-the-docker-daemon-socket

# Commands:
	1  clear
    2  df -h
    3  free -m
    4  clear
    5  curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-latest.x86_64.rpm
    6  sudo rpm -ivh minikube-latest.x86_64.rpm
    7  minikube version
    8  sudo groupadd docker
    9  sudo usermod -aG docker ec2-user
   10  sudo yum install docker -y
   11  docker version
   12  clear
   13  sudo systemctl start docker
   14  sudo systemctl enable docker
   15  clear
   16  docker version
   17  sudo docker version
   18  clear
   19  minikube start --driver=docker
   20  minikube start --driver=docker
   21  docker run hello-world
   22  exit
   23  clear
   24  docker run hello-world
   25  clear
   26  history
   27  minikube start --driver=docker
   28  history
 30  curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
   31  curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
   32  echo "$(<kubectl.sha256) kubectl" | sha256sum --check
   33  sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
   34  kubectl version --client

#Minikube Start:
[ec2-user@ip-172-31-87-228 ~]$ minikube start --driver=docker
* minikube v1.18.0 on Amazon 2 (xen/amd64)
* Using the docker driver based on user configuration
* Starting control plane node minikube in cluster minikube
* Pulling base image ...
* Downloading Kubernetes v1.20.2 preload ...
    > preloaded-images-k8s-v9-v1....: 491.22 MiB / 491.22 MiB  100.00% 54.56 Mi
* Creating docker container (CPUs=2, Memory=2200MB) ...
* Preparing Kubernetes v1.20.2 on Docker 20.10.3 ...
  - Generating certificates and keys ...
  - Booting up control plane ...
  - Configuring RBAC rules ...
* Verifying Kubernetes components...
  - Using image gcr.io/k8s-minikube/storage-provisioner:v4
* Enabled addons: storage-provisioner, default-storageclass
* kubectl not found. If you need it, try: 'minikube kubectl -- get pods -A'
* Done! kubectl is now configured to use "minikube" cluster and "default" namespace by defau

Install Kubectl client:
Link4: https://kubernetes.io/docs/tasks/tools/install-kubectl/
```
---
## Complete MINIKUBE Commands:
```
    1  clear
    2  df -h
    3  free -m
    4  clear
    5  curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-latest.x86_64.rpm
    6  sudo rpm -ivh minikube-latest.x86_64.rpm
    7  minikube version
    8  sudo groupadd docker
    9  sudo usermod -aG docker ec2-user
   10  sudo yum install docker -y
   11  docker version
   12  clear
   13  sudo systemctl start docker
   14  sudo systemctl enable docker
   15  clear
   16  docker version
   17  sudo docker version
   18  clear
   19  minikube start --driver=docker
   20  minikube start --driver=docker
   21  docker run hello-world
   22  exit
   23  clear
   24  docker run hello-world
   25  clear
   26  history
   27  minikube start --driver=docker
   28  history
   29  clear
   30  curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
   31  curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
   32  echo "$(<kubectl.sha256) kubectl" | sha256sum --check
   33  sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
   34  kubectl version --client
   35  history
   36  clear
   37  kubectl get po
   38  cd /usr/local/
   39  mkdir practice
   40  sudo mkdir practice
   41  cd practice/
   42  clear
   43  cat > first.yaml
   44  sudo cat > first.yaml
   45  sudo vi first.yaml
   46  ls
   47  cat first.yaml
   48  clear
   49  kubectl apply -f first.yaml
   50  cat first.yaml
   51  sudo vi first.yaml
   52  clear
   53  kubectl apply -f first.yaml --dry-run=client
   54  kubectl get po
   55  kubectl apply -f first.yaml
   56  kubectl get po
   57  clear
   58  history
   59  clear
   60  ls
   61  kubectl get pods
   62  kubectl get po
   63  kubectl describe pods sat-pod1
   64  clear
   65  history
   66  kubectl get po
   67  clear
   68  kubectl --help
   69  clear
   70  kubectl run satpod2 --image=nginx --port=80
   71  kubectl get po
   72  kubectl port-forward 2232:80
   73  clear
   74  docker ps -qa
   75  sudo yum remove minikube -y
   76  clear
   77  minikube version
   78  minikube --version
   79  clear
   80  ls
   81  ls -a
   82  clear
   83  docker images
   84  docker rmi $(docker images -qa) -f
   85  docker rm $(docker ps -qa) -f
   86  docker rmi $(docker images -qa) -f
   87  clear
   88  docker images
   89  clear
   90  sudo -i
   91  clear
   92  sudo -i
   93  history
```
---
## Installing k8s cluster in VMS/DC/Baremetal -- using kubeadm

1. Create 3 VM's in AWS
- 1 master and 2 minion Nodes ( master - 4 GB RAM, 2 CPUS and 20 GB Diskspace, minionnodes - 1 GB RAM, 1 CPU and 8 GB Disksapce)

2. set hostnames for all 3 VM's
- hostnamectl set-hostname 'master'

3. create setup.sh script and write the following content into that. Execute this script on master and minion nodes.
[root@ip-172-31-46-37 ~]# cat > setup.sh 
#############################################################################
# selinux security off
setenforce  0
sed -i 's/SELINUX=enforcing/SELINUX=disabled/'  /etc/selinux/config

## swap memory also off
swapoff -a

## enable kernel bridge network support 
modprobe br_netfilter
echo '1' > /proc/sys/net/bridge/bridge-nf-call-iptables

##  installing docker & kubeadm 
cat  <<EOF  >/etc/yum.repos.d/kube.repo
[kube]
baseurl=https://packages.cloud.google.com/yum/repos/kubernetes-el7-x86_64
gpgcheck=0
EOF
yum  install kubeadm  docker -y 

## starting docker & kubelet daemon 
systemctl start docker  kubelet 
systemctl enable  docker  kubelet 
##############################################################################

4. chmod +x setup.sh

5. ./setup.sh

6. Do this only on Kubernetes Master
  In case of cloud services like aws, azure if you want to bind public with certificate of kubernetes and We are here using Calico Networking, so we need to pass some parameter  you can start Kubernetes_networking from this.
  [root@master ~]# kubeadm init --pod-network-cidr=192.168.0.0/16 --apiserver-advertise-address=0.0.0.0   --apiserver-cert-extra-sans=publicip,privateip,serviceip

7. Use the output of above command and paste it to all the worker nodes
Example: kubeadm join 172.31.88.229:6443 --token p2k6uz.n28z7csymyd8ax57 --discovery-token-ca-cert-hash sha256:26a81ba851e73e6339d79749c3cfcba0fe256b06ea21a4518438fe0dedfd548e

8. Do this only on Kubernetes Master
  [root@master ~]# mkdir -p $HOME/.kube
  [root@master ~]#  cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
  [root@master ~]# chown $(id -u):$(id -g) $HOME/.kube/config

9. Now apply calico project
   kubectl apply -f https://docs.projectcalico.org/v3.8/manifests/calico.yaml
   
   Or Download 3.16 latest version as now october 2020
   wget https://docs.projectcalico.org/manifests/calico.yaml
   kubectl apply -f calico.yaml

10. Now you can check nodes status
[root@master ~]# kubectl get nodes
NAME                 STATUS   ROLES    AGE     VERSION
master.example.com   Ready    master   11m     v1.12.2
node1.example.com    Ready    <none>   9m51s   v1.12.2
node2.example.com    Ready    <none>   9m25s   v1.12.2
node3.example.com    Ready    <none>   9m3s    v1.12.2
---




