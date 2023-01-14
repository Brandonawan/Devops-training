# Devops-training
DevOps is a set of practices, tools, and a cultural philosophy that automate and integrate the processes between software development and IT teams.

### DOCKER 
* A container is a unit of software that encapsulates everything needed to build, ship, and run applications.  
* Containers lower deployment time and costs, improve utilization, automate processes, and support next-gen applications (microservices). Major container vendors include Docker, Podman, LXC, and Vagrant. 
* Docker is an open platform used for developing, shipping, and running applications as containers. 
* Docker containers are not a good fit for applications based on monolithic architecture or applications that require high performance or security. 
* Docker architecture consists of the Docker client, the Docker host, and the container registry. 
* The Docker host contains objects such as the Dockerfiles, images, containers, networks, storage volumes, and other objects, such as plugins and add-ons. 
* Docker uses networks to isolate container communications. 
* Docker uses volumes and binds mounts to persist data even after a container stops running. 
* Plugins, such as storage plugins, provide the ability to connect to external storage platforms. 

### DOCKER COMMANDS
* docker build -t my-app:v1 .
* docker images
* docker run --name webapp alpine
* docker run -t my-app:v1 . 
* docker stop <conatiner:id> or name
* docker rm <container:id>
* docker rmi <image:name>
* docker inspect <container:id>
* docker log <container:id>
* docker push -t my-app:v1
* docker pull alpine
* docker run python:3.6 cat /etc/*release*  //To know the OS python image is based on
* docker run -d -p 8080:8080 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts-jdk11


### KUBERNETES
 * Nodes are the worker machines in kubernetes, (can be virtual or physical machine) and manage by the control plane.
 * Nodes contain pods which are the smallest deployment entity in kubernetes.
 * kubectl (kube command tool line)
 * kubectl [command] [type] [name] [flags]
 [command] = any operation to be performed ( create, get, apply, delete)
 [type] = resource type (pod, deployment, replicaset)
 [name] = resource name (if applicable)
 [flags] = special options or modificatiers that override default values.

 * Container orchestration automates the container lifecycle resulting in faster deployments, reduced errors, higher availability, and more robust security. 

* Kubernetes Is a highly portable, horizontally scalable, open-source container orchestration system with automated deployment and simplified management capabilities.  

Kubernetes architecture consists of a control plane and one or more worker planes. 

* A control plane includes controllers, an API server, a scheduler, and an etcd. 

* A worker plane includes nodes, a kubelet, container runtime, and kube-proxy. 

* Kubernetes objects include Namespaces, Pods, ReplicaSets, Deployments, and Services. 

* Namespaces help in isolating groups of resources within a single cluster. 

* Pods represent a process or an instance of an app running in the cluster. 

* ReplicaSets create and manage horizontally scaled running Pods. 

* Deployments provide updates for Pods and ReplicaSets. 

* A service in Kubernetes is a REST object that provides policies for accessing the pods and cluster. 

* Kubernetes capabilities include automated rollouts and rollbacks, storage orchestration, horizontal scaling, automated bin packing, secret and configuration management, Ipv4/Ipv6 dual-stack support, batch execution, self-healing, service discovery, load balancing, and extensible design. 

* Services in Kubernetes are REST objects that provide policies for accessing the pods and cluster. ClusterIP provides Inter-service communication within the cluster; a NodePort Service creates and routes the incoming requests automatically to the ClusterIP Service; the External Load Balancer, or ELB, creates NodePort and ClusterIP Services automatically and External Name service represents external storage as well as enables Pods from different namespaces to talk to each other.

* Ingress is an API object that provides routing rules to manage external users' access to multiple services in a Kubernetes cluster; whereas using a DaemonSet ensures that there is at least one copy of the pod on all nodes; a StatefulSet manages stateful applications, manages Pod deployment and scaling, maintains a sticky identity for each Pod request and provides persistent storage volumes for your workloads and lastly a Job creates pods and tracks the Pod completion process; Jobs are retried until completed.

### KUBERNETES COMMANDS
* kubectl version
* kubectl config get-clusters
* kubectl describe
* kubectl get pods
* kubectl get pods -o wide

### LINUX COMMANDS
* `crontab -e`  (cron job)
* `ls -lt` (shows newest to oldest files or folders)
* `ls -lt` (shows oldest to newest files or folders)
* `ls -a` (show hidden files)
* `ls -al` (show file permissions etc)
* `file /home`  (display the type of file, in linux everything is a file)
* mkdir -p (multiple directories at a time)
* PS1 (Use to customise the bash prompt,e.g echo $PS1, PS1="Ubuntu-Server" or PS1="[\d \t \u@\h]"
* scp -P 2222 /home/brandon/AppBreweryWallpaper.jpg brandon@hostname.com:/home/brandon/project
* ssh-copy-id admin@192.168.0.102 -p 2222

##### WORKING WITH HARDWARE
* `uname -r` (know kernel version)
* `dmesg | grep usb` (gets all events printed by the kernel, grep usb is to get usb activities)
* `lspci` (list peripheral components)
* `lsblk` (list block storage)
* `lscpu` 
* `lsmem --summary` (list and summarizes memory) 0r `free -m` (-m in megabyte, -g in gigabytes)
* `lshw`  (gets details of the entire hardware 

##### WORKING WITH BOOT
* `runlevel`  (show which boot level e.g N 5 (graphical.target), N 3 (multi-user.target)) or 
* `systemctl get-default`  (to also verify target level)
* `systemctl set-default multi-user.target`  (changed from graphical to multi-user)

##### WORKING PACKAGE MANAGEMENT (RPM, YUM, DKPG, APT-GET, APT)
###### ==> RPM (Redhat Package Manager)
* INSTALL `rpm -ivh telnet.rpm`
* UNINSTALL `rpm -e telnet.rpm`
* UPGRADE `rpm -Uhv telnet.rpm`
* QUERY `rpm -q telnet.rpm`
* VERIFYING `rpm -vf <path to file>`  or `rpm -qa | grep wget`

###### ==> YUM PACKAGE MANAGER
* INSTALL `yum install httpd`
* UNINSTALL `yum remove httpd`
* UPGRADE `yum upgrade telnet` or `yum update` (update all packages)
* `yum repolist` 

###### ==> DKPG PACKAGE MANAGER
* INSTALL  `sudo dpkg --install [.deb file]` or `sudo dpkg --install [path/to/.deb file]`
For error run `sudo apt -f install`
* UNINSTALL  `dkpg -r telnet.deb`
* LIST  `dkpg -l telnet.deb`
* STATUS `dkpg -s telnet.deb`
* VERIFYING  `dkpg -p <path to file>`

### GIT COMMANDS
==> A branch in git is simply a pointer to a specific commit
==> A commits can point to different blobs(piece of information) and trees.
==> Git rebase produces a different git history compare to merging.
* Print last commit `git log -n 1`
* Print commits and file `git log --name-only`
* `git branch sarah`
* `git checkout sarah`
* `git checkout -b sarah`
* `git branch -d sarah`
* `git branch`
* Shows which branch a branch was created from, first checkout into that branch `git log --graph --decorate`
* This reverts the changes to the ones on this commit, makes a new revert history and retain file `git revert bef18eacf` 
* Removes commit history and files by 3 commit ahead `git reset --hard HEAD~3` 
* Removes commit history but preserves the files in the working area by 3 commit `git reset --soft HEAD~3`
* `git stash list`
* `git stash show stash@{1}`
* `git stash pop sash@{1}`
* shows all states of the repo `git reflog`
