# Linux_Training
Welcome to my Linux training material for Sysadmin course. 
In this repository you can find all the material related to the course, please feel free to create Pull Requests in case you see some space to improve the current content. 

## Initialize the docker swarm 

Command to initialize the swarm on the master node
```
docker swarm init --listen-addr {IP_ADDRESS}
```
Then you need to use the join command on the worker node(s) to connect them to the master


## Docker Swarm Networks
Some of the Docker swarm networks which are used in the Manifests in this repository are created manually, you can use the following command to do it in advance, right after the initialization of the Docker Swarm 
```
docker network create --driver overlay --attachable {NETWORK_NAME}
```

The networks which I usually create in advance:

- db-network : this is where the applications can connect to the mariadb database.
- traefik-network : this is the network where you can expose your services to the outside world using traefik.

In order to create them you can run the following commands on the swarm master node.
```
docker network create --driver overlay --attachable db-network
docker network create --driver overlay --attachable traefik-network
```
