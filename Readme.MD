# Devops-training

* Note: A container is a unit of software that encapsulates everything needed to build, ship, and run applications.  
* Docker architecture consists of the Docker client, the Docker host, and the container registry. 
* The Docker host contains objects such as the Dockerfiles, images, containers, networks, storage volumes, and other objects, such as plugins and add-ons. 
* Docker uses networks to isolate container communications. 
* Docker uses volumes and binds mounts to persist data even after a container stops running. 
* Plugins, such as storage plugins, provide the ability to connect to external storage platforms. 

### DOCKER COMMANDS
==> docker build -t my-app:v1 .
==> docker images
==> docker build -t my-app:v1 . 
==> docker push -t my-app:v1
==> docker pull alpine