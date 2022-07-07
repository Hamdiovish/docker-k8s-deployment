# docker-k8s-deployment
This project contains docker and kubernetes scripts and configuration files and includes below folders :
* docker-k8s-front : contains frontend demo's k8s configuration files
* docker-k8s-back : contains backend demo's k8s configuration files
* docker-k8s-compose : contains docker compose scripts for the demo
***

## Image versions
During the demo implementation, multiple versions have been created and below are their corresponding tags :
| Component | Tag(s) | Content |
|:--------------|:-------------:|--------------:|
| fsouayah/demo-frontend | 1.0.0, latest | Frontend demo project with k8s deployment and communication with fsouayah/demo-backend |
| fsouayah/demo-backend | 1.0.0, latest | Backend demo project with k8s deployment and communication with fsouayah/demo-frontend |
***

## Docker Compose for local deployment
There are two ways to spin up our project using docker-compose:
* using already built docker images
* building docker images on docker-compose launch

### *Using already built docker images*
In this step, the docker images for frontend and backend should have been already created (see readme files in each project).
Then you simply need to execute the below command within ~/docker-k8s-compose directory (it will execute docker-compose.yaml file bt default) :
```
docker-compose up
```

### *Building docker images on docker-compose launch*
In this step, the docker images will be created on the fly by targeting the Dockerfiles of the corresponding projects.
The command belows shows how to run docker-compose by specifying a custom script file name :
```
docker-compose -f docker-compose-dev.yaml up
```
This usecase is more relevant during development phase in the project's lifecycle