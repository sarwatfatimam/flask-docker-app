# Flask Docker App

A beginner-level project demonstrating how to Dockerize a simple Flask web application and use Docker Compose 
to manage multi-container applications. The project includes setting up a basic Flask application, creating a Dockerfile
to containerize the app, and using Docker Compose to orchestrate the app alongside a Redis service.

## What is Docker?
Docker is a platform that helps separate applications from the infrastructure. The application 
software can be built, shipped and deployed regardless of the underlying infrastructure. This is 
possible because docker provides an ability to package and run applications in an 
isolated environment called containers. e.g. if a developer is working on multiple projects, they
don't have to manage different requirements for each of the project. Developers can simply create 
multiple docker containers that are associated for a single project and 
then use docker-compose to run different containers as one application. Developers can then share the 
docker-compose with other developers to run the application in the same exact way without worrying 
about "it worked on my computer" or whether its windows or mac. 

## Docker Architecture 
Docker is based on a client-server architecture. The docker client (typically `docker` command) talks 
to the docker daemon (`dockerd` is the command used to start the docker daemon)
which does the heavy lifting of the building, running and distributing the docker containers. 
The docker client and docker daemon can be on the same system or a docker client can 
connect to a remote docker daemon as well. The docker client and the docker daemon communicate via 
a REST API, over UNIX socker or network interface.

Docker compose is a docker client as well which allows to work with multiple containers in a single application. 
A docker registry stores docker images. The Docker Hub is a public registry where docker looks for images by default.
A private docker registry can also be set up e.g. Azure Container Registry. 

## Docker Objects
Docker daemon is responsible for creating docker objects which includes images,containers, volumes, networks, plugins
etc. Docker images are instructions for setting up containers. They are often created on top of another image 
with commands to customize e.g. a docker image on Ubuntu with commands to install airflow. 
These commands are written in a docker file and each command is converted into separate layer in docker so e.g. 
if there is a change in one of the commands, only that particular layer is updated which makes docker faster than other
virtualization technologies. 

A container is an executable instance of an image. We can start, stop, create, delete or move a container via Docker API. 
A container is isolated from other applications or the host machine. A container is defined by its image and other 
configuration options provided when creating or starting it. 

## Initial Setup
1. Let's get back to our project. The first step would be to create a new conda environment for this specific project. 
2. Run `conda create --name flask-app python=3.10` and activate the conda environment using `conda activate flask-app`



