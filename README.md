##### This project is about investigating the encrypted database [CryptDB](https://css.csail.mit.edu/cryptdb/) developed at MIT in 2011.
* Currently, the most actively maintained cryptDB repository is located at [yiwenshao/Practical-Cryptdb](https://github.com/yiwenshao/Practical-Cryptdb).
* This Dockerfile deploys the project into a runnable docker container base on Ubuntu 16.04.

## How to setup:

##### 1. Make sure to have Docker installed

http://docs.docker.com/v1.8/installation/

###### This setup is for Linux. For OS X and Windows, install Docker Toolbox and skip the sudo part of the commands.

##### 2. Create a folder, clone project and navigate to folder containing the Dockerfile

    git clone https://github.com/agribu/Practical-Cryptdb_Docker.git

##### 3. Build docker image

    sudo docker build -t **name-of-image**:**version** **.**

    #Example:
    sudo docker build -t cryptdb:v1 .
    
    #To build without caching use:
    sudo docker build --no-cache=true -t cryptdb:v1 .

(Open the Docker Quickstart Terminal if OS X or Windows)

##### 4. Run docker container based built image

    sudo docker run -d --name **name-of-container** -p **port-in**:**port-out** -p **port-in**:**port-out** -e MYSQL_ROOT_PASSWORD='letmein' **name-of-image**:**version**

    #Example:
    sudo docker run -d --name cryptdb_v1 -p 3306:3306 -p 3399:3399 -e MYSQL_ROOT_PASSWORD='letmein' cryptdb:v1

(Important: The password must be 'letmein')

##### 5. For accessing a docker container, use

    sudo docker exec -it **name-of-container** bash

    #Example:
    sudo docker exec -it cryptdb_v1 bash



## How to play around:

```
./cdbserver.sh
./cdbclient.sh
```
