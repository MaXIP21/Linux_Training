# Linux_Training
Welcome to my Linux training material for Sysadmin course. 
In this repository you can find all the material related to the course, please feel free to create Pull Requests in case you see some space to improve the current content. 

## Initialize the docker swarm 

Command to initialize the swarm on the master node
```
  $ docker swarm init --listen-addr {IP_ADDRESS}
```
Then you need to use the join command on the worker node(s) to connect them to the master


## Docker Swarm Networks
Some of the Docker swarm networks which are used in the Manifests in this repository are created manually, you can use the following command to do it in advance, right after the initialization of the Docker Swarm 
```
  $ docker network create --driver overlay --attachable {NETWORK_NAME}
```
