# Networking (Cross) Container Communication

### Container to WWW
  - By default container can sent any request to public www
  
### Container to Local Host
  - By default container can't communicate with local host machine
  - ```localhost:port/path``` doesn't work
  - You have to change the domain from ```localhost``` to ```host.docker.internal```
  - ```host.docker.internal:port/path``` works fine. ```mongodb://host.docker.internal:27017/my_db```

### Container to Container
  - Run a container, ie - mongodb : ```docker run -d --name mongodb mongo```
  - Inspect the container details : ```docker container inspect mongodb```
  - Copy the IPAddress: ```"IPAddress": "172.17.0.2"```
  - Use this IP address in your code to communicate with this mongodb container. ```mongodb://172.17.0.2:27017/my_db```
  - Every time you re run mongodb container, the mongo db IP will change. So, you have to update the mongo db IP address every time in your code.
  - In that case we can use docker network.
  - The idea is run all the container under a single network. So that they can inter-connect.
  - docker network --help
    ```
      docker network --help
      Commands:
        connect     Connect a container to a network
        create      Create a network
        disconnect  Disconnect a container from a network
        inspect     Display detailed information on one or more networks
        ls          List networks
        prune       Remove all unused networks
        rm          Remove one or more networks
    ```
    - Create network : ```docker network create my-network```
    - Run mongodb container with ```--network network_name``` command : ```docker run -d --name mongodb --network my-network mongo```
    - Instead of ```localhost``` or ```host.docker.internal``` or ```specific IP```, use ```container_name (mongodb)``` as domain name in your code. ```mongodb://mongodb:27017/my_db```
    - Now run you app under same network : ```docker run -d --rm -p 3000:3000 --name network-test --network my-network network-test-image```
    - Your app container now can communicate with mongodb container
    - In docker network, no need to expose port. We expose port to connect container to outside world.
    
   
  
