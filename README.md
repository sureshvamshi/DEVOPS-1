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
```
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
```
---
## Commands to create PODS and Services
```
 1  hostname
    2  hostnamectl set-hostname master
    3  hostname
    4  clear
    5  sudo reboot
    6  cat > setup.sh
    7  clear
    8  ls
    9  ls -l
   10  chmod +x setup.sh
   11  ls -l
   12  ./setup.sh
   13  kubeadm init --pod-network-cidr=192.168.0.0/16 --apiserver-advertise-address=0.0.0.0   --apiserver-cert-extra-sans=publicip,privateip,serviceip
   14  clear
   15  kubectl get nodes
   16  mkdir -p $HOME/.kube
   17  cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
   18  chown $(id -u):$(id -g) $HOME/.kube/config
   19  wget https://docs.projectcalico.org/manifests/calico.yaml
   20  kubectl apply -f calico.yaml
   21  clear
   22  kubectl get nodes
   23  cat /etc/kubernetes/admin.conf
   24  clear
   25  ls
   26  ls -a
   27  cd .kube/
   28  ls
   29  cat config
   30  clear
   31  cd ..
   32  ls
   33  clear
   34  kubectl get nodes
   35  kubectl get pods
   36  clear
   37  kubectl client --version
   38  kubectl version --client
   39  clear
   40  kubectl get nodes
   41  kubectl get pods
   42  kubectl run satp1 --image=httpd --port=80
   43  kubectl get pods
   44  kubectl get pods -o wide
   45  kubectl run satp2 --image=httpd --port=80
   46  kubectl get pods -o wide
   47  clear
   48  kubectl get pods -o wide
   49  kubectl describe pods satp1
   50  clear
   51  ls
   52  cd /usr/local
   53  clear
   54  ls
   55  cd practice/
   56  ls
   57  cat first.yaml
   58  kubectl api-resources
   59  clear
   60  kubectl api-resources
   61  clear
   62  cat first.yaml
   63  clear
   64  ls
   65  ls -a
   66  ls /home/ec2-user
   67  pwd
   68  ls ~
   69  cat -n ~/calico.yaml
   70  clear
   71  ls
   72  cat first.yaml
   73  clear
   74  ls
   75  kubectl run satpod2 --image=httpd --port=80 --dry-run=client
   76  kubectl run satpod2 --image=httpd --port=80 --dry-run=client -o yaml
   77  ls
   78  kubectl run satpod2 --image=httpd --port=80 --dry-run=client -o yaml > second.yaml
   79  clear
   80  ls
   81  cat second.yaml
   82  kubectl apply -f second.yaml
   83  kubectl get po
   84  clear
   85  kubectl get po
   86  kubectl api-resource
   87  kubectl api-resources
   88  clear
   89  kubectl get pods
   90  kubectl describe satpod2
   91  kubectl describe pods satpod2
   92  clear
   93  kubectl get pods
   94  kubectl get pods -o wide
   95  kubectl get pods --show-labels
   96  clear
   97  ls
   98  vi second.yaml
   99  kubectl apply -f second.yaml
  100  clear
  101  kubectl apply -f second.yaml --dry-run=client
  102  vi second.yaml
  103  kubectl apply -f second.yaml --dry-run=client
  104  kubectl apply -f second.yaml
  105  kubectl get po
  106  clear
  107  kubectl get po satpod3 -o wide
  108  kubectl get po satpod3 --show-labels
  109  clear
  110  kubectl create service nodeport svc1 --port 2213 --dry-run=client
  111  kubectl create service nodeport svc1 --port 2213:80 --dry-run=client
  112  kubectl create service nodeport svc1 --tcp 2213:80 --dry-run=client
  113  kubectl create service nodeport svc1 --tcp 2213:80 --dry-run=client -o yaml
  114  kubectl get po satpod3 --show-labels
  115  kubectl create service nodeport svc1 --tcp 2213:80 --dry-run=client -o yaml > svc1.yaml
  116  clear
  117  ls
  118  vi svc1.yaml
  119  ls
  120  kubectl get svc
  121  kubectl apply -f svc1.yaml
  122  kubectl get svc
  123  curl ifconfig.io
  124  kubectl get svc -o wide
  125  clear
  126  kubectl get pods
  127  kubectl delete pods --all
  128  kubectl delete svc --all -f
  129  kubectl delete svc --all
  130* kubectl get svc
  131  clear
  132  ls
  133  kubectl apply -f second.yaml
  134*
  135  kubeclt apply -f svc1.yaml
  136  kubectl apply -f svc1.yaml
  137  kubectl get svc -o wide
  138  kubectl get svc --show-labels
  139  clear
  140  kubectl delete pods --all
  141  kubectl delete svc --all
  142  clear
  143  kubectl get po
  144  clear
  145  history
```
---
## To check the complete POD details
```
[ec2-user@ip-172-31-87-228 practice]$ kubectl describe pods sat-pod1
Name:         sat-pod1
Namespace:    default
Priority:     0
Node:         minikube/192.168.49.2
Start Time:   Tue, 02 Mar 2021 02:54:30 +0000
Labels:       <none>
Annotations:  <none>
Status:       Running
IP:           172.17.0.3
IPs:
  IP:  172.17.0.3
Containers:
  satc1:
    Container ID:   docker://e4e7aa5e1b98b9dd3793ff6b87d92914390312b7782786e53473be89ac847a91
    Image:          httpd
    Image ID:       docker-pullable://httpd@sha256:3c252c919ef2445a6a41dde913a56202754821af87c049c4312bf81bdbc6df4b
    Port:           80/TCP
    Host Port:      0/TCP
    State:          Running
      Started:      Tue, 02 Mar 2021 02:54:36 +0000
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from default-token-q2wm6 (ro)
Conditions:
  Type              Status
  Initialized       True
  Ready             True
  ContainersReady   True
  PodScheduled      True
Volumes:
  default-token-q2wm6:
    Type:        Secret (a volume populated by a Secret)
    SecretName:  default-token-q2wm6
    Optional:    false
QoS Class:       BestEffort
Node-Selectors:  <none>
Tolerations:     node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                 node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:
  Type    Reason     Age   From               Message
  ----    ------     ----  ----               -------
  Normal  Scheduled  106s  default-scheduler  Successfully assigned default/sat-pod1 to minikube
  Normal  Pulling    105s  kubelet            Pulling image "httpd"
  Normal  Pulled     101s  kubelet            Successfully pulled image "httpd" in 3.542033429s
  Normal  Created    100s  kubelet            Created container satc1
  Normal  Started    100s  kubelet            Started container satc1
```
---
## Create Replication Controller, Expose as a Service & Scale up and down.
```
1.created a yaml for RC
     - created RC api resource
     - created a POD
2.scaled up and down
3.exposed RC as a service (NodePort)
```
---
**commands:**
```
 243  kubectl api-resources
  244  clear
  245  ls
 246  kubectl apply -f rc.yaml --dry-run=client
  247  kubectl get rc
  248  kubectl delete rc
  249  kubectl delete rc --all
  250  clear
  251  kubectl apply -f rc.yaml --dry-run=client
  252  kubectl apply -f rc.yaml
  253  kubectl get rc
  254  kubectl get po
  255  kubectl delete pod sat-rc-1-sntxh
  256  kubectl get po
  257  clear
  258  kubectl --help
  259  clear
  260  kubectl replace -f rc.yaml
  261  kubectl get po
  262  kubectl replace -f rc.yaml --force
  263  kubectl get rc
  264  clear
  265  kubectl get po
  266  clear
  267  kubectl --help
  268  clear
  269  kubectl get rc
  270  kubectl scale rc sat-rc-1 --replicas=3
  271  kubectl get po
  272  kubectl scale rc sat-rc-1 --replicas=5
  273  kubectl get po
  274  kubectl scale rc sat-rc-1 --replicas=2
  275  kubectl get po
  276  clear
  277  kubectl get po
  278  kubectl scale rc sat-rc-1 --replicas=1
  279  kubectl get po
  280  clear
  281  kubectl get rc
  282  kubectl get po
  283  kubectl describe po sat-rc-1-rqkh7
  284  clear
  285  ls
  286  cat svc1.yaml
  287  clear
  288  kubectl --help
  289  clear
  290  kubectl get rc
  291  kubectl expose rc sat-rc-1 --type NodePort --port 2354 --target-port 80 --name rcsvc1
  292  kubectl get svc
  293  curl ifconfig.io
  294  clear
  295  cat rc.yaml
  296  clear
  297  history
306  kubectl get rc -o wide
310  kubectl get pods --show-labels
```
---
**Problems of Containers resolved:**
```
1. management
api-resources
 - service
 - replication controller
 - node controller

2. High Availability (HA)
 - Replication Controller
 - Replica Set

3. Scale up and Down
 - Replication Controller
 - Replica Set
 - Deployment
```
---
## Introduction To Deployment API Resource

<img src="IntroductionToDeploymentAPIResource.PNG"/>

---
## Deployment API Resource

<img src="DeploymentAPIResource.PNG"/>

---
## Create Deployment Api Resource, Expose as a Service and Roll-back
```
1. created deployment api resource
   - deployment created
   - replica set created
   - pod is created
2. exposed deployment as a service(NodePort)
3. deployment resource scaled up and down
4. deployment roll-back
```
---

**Deployment Resource Details:**
```
[root@master practice]# kubectl describe deploy satdep1
Name:                   satdep1
Namespace:              default
CreationTimestamp:      Wed, 03 Mar 2021 03:57:12 +0000
Labels:                 app=satdep1
Annotations:            deployment.kubernetes.io/revision: 1
Selector:               app=deppod1
Replicas:               3 desired | 3 updated | 3 total | 3 available | 0 unavailable
StrategyType:           RollingUpdate
MinReadySeconds:        0
RollingUpdateStrategy:  25% max unavailable, 25% max surge
Pod Template:
  Labels:  app=deppod1
  Containers:
   depc1:
    Image:        nginx
    Port:         <none>
    Host Port:    <none>
    Environment:  <none>
    Mounts:       <none>
  Volumes:        <none>
Conditions:
  Type           Status  Reason
  ----           ------  ------
  Progressing    True    NewReplicaSetAvailable
  Available      True    MinimumReplicasAvailable
OldReplicaSets:  <none>
NewReplicaSet:   satdep1-78c87d988d (3/3 replicas created)
Events:
  Type    Reason             Age    From                   Message
  ----    ------             ----   ----                   -------
  Normal  ScalingReplicaSet  11m    deployment-controller  Scaled up replica set satdep1-78c87d988d to 1
  Normal  ScalingReplicaSet  2m41s  deployment-controller  Scaled up replica set satdep1-78c87d988d to 3
```
---

**commands:**
```
310  kubectl get pods --show-labels
  311  history
  312  clear
  313  cd /usr/local/practice/
  314  ls
  315  clear
  316  docker version
  317  clear
  318  kubectl get deployments
  319  clear
  320  kubectl create deployment satdep1 --image=nginx --dry-run=client -o yaml
  321  kubectl create deployment satdep1 --image=nginx --dry-run=client -o yaml > dep.yaml
  322  clear
  323  vi dep.yaml
  324  clear
  325  kubectl apply -f dep.yaml
  326  kubectl get dep
  327  kubectl get deploy
  328  kubectl get deploy -o wide
  329  kubect get RS
  330  kubect get rs
  331  kubectl get rs
  332  kubectl get rs -o wide
  333  kubectl get po
  334  clear
  335  kubectl get deploy
  336  kubectl expose deploy satdep1 --type NodePort --port 2564 --target-port 80 --name depsvc1
  337  kubectl get svc
  338  kubectl --help
  339  clear
  340  kubectl get deploy
  341  kubectl scale deploy satdep1 --replicas=3
  342  kubectl get po
  343  kubectl deploy --help
  344  kubectl deployment --help
  345  kubectl deployments --help
  346  kubectl --help
  347  clear
  348  kubectl get deploy
  349  kubectl describe deploy satdep1
  350  clear
  351  kubectl rollout history deploy satdep1
  352  kubectl replace deploy satdep1 --force
  353  kubectl replace deploy satdep1 -f
  354  clear
  355  kubectl  set image  deployment  ashu-depweb jan2021=dockerashu/jan2021:webv2
  356  docker images
  357  clear
  358  kubectl create deploy satdep2 --image=satish1010/httpd:sat1 --dry-run=client
  359  kubectl create deploy satdep2 --image=satish1010/httpd:sat1 --dry-run=client -o yaml
  360  kubectl create deploy satdep2 --image=satish1010/httpd:sat1 --dry-run=client -o yaml > dep2.yaml
  361  clear
  362  ls
  363  kubectl apply -f dep2.yaml
  364  kubectl get deploy
  365  docker images
  366  clear
  367  git --version
  368  yum install git -y
  369  clear
  370  ls
  371  git clone https://gitlab.com/chinnu1028/beginner-html-site-styled.git
  372  ls
  373  cd beginner-html-site-styled/
  374  ls
  375  docker build -t satish1010/httpd:deploy .
  376  clear
  377  ls
  378  docker images
  379  clear
  380  docker push satish1010/httpd:deploy
  381  docker login
  382  docker push satish1010/httpd:deploy
  383  clear
  384  ls
  385  cd ..
  386  ls
  387  celar
  388  clear
  389  ls
  390  kubectl get deploy
  391  kubectl delete deploy --all
  392  kubectl get deploy
  393  kubectl get pod
  394  clear
  395  ls
  396  vi dep2.yaml
  397  clear
  398  kubectl apply -f dep2.yaml
  399  kubectl get deploy
  400  kubectl get pods
  401  clear
  402  kubectl get deploy
  403  kubectl expose deploy satdep2 --type NodePort --port 3425 --target-port 80 --name depsvc2
  404  kubectl get svc -o wide
  405  kubectl describe deploy satdep2
  406  clear
  407  kubectl rollout history deploy satdep2
  408  ls
  409  cd beginner-html-site-styled/
  410  ls
  411  cat index.html
  412  vi index.html
  413  clear
  414  ls
  415  history
  416  docker build -t satish1010/httpd:deploy2 .
  417  docker push satish1010/httpd:deploy2
  418  clear
  419  ls
  420  cd ..
  421  ls
  422  kubectl  set image  deployment  satdep2 jan2021=satish1010/httpd:deploy2
  423  cat dep2.yaml
  424  clear
  425  kubectl  set image  deployment  satdep2 httpd=satish1010/httpd:deploy2
  426  kubectl rollout history
  427  kubectl rollout history deploy satdep2
  428  kubectl describe deploy satdep2
  429  clear
  430  kubectl get deploy
  431  kubectl get svc
  432  kubectl get pod
  433  kubectl rollout history deploy satdep2
  434  kubectl describe deploy satdep2
  435  clear
  436  kubectl rollout undo deploy satdep2
  437  kubectl rollout history deploy satdep2
  438  kubectl describe deploy satdep2
  439  clear
  440  kubectl  set image  deployment  satdep2 httpd=satish1010/httpd:deploy
  441  kubectl  set image  deployment  satdep2 httpd=satish1010/httpd:deploy2
  442  history
```
---


