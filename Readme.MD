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
* docker build -t my-app:v1 . 
* docker push -t my-app:v1
* docker pull alpine


### KUBERNETES
 * Nodes are the worker machines in kubernetes, (can be virtual or physical machine) and manage by the control plane.
 * Nodes contain pods which are the smallest deployment entity in kubernetes.
 * kubectl (kube command tool line)
 * kubectl [command] [type] [name] [flags]
 [command] = any operation to be performed ( create, get, apply, delete)
 [type] = resource type (pod, deployment, replicaset)
 [name] = resource name (if applicable)
 [flags] = special options or modificatiers that override default values.
