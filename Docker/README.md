# Docker

2023-01-16 (01 - Getting Started - All)
  - What is Docker?
  - What is Container?
  - Virtual machine vs Docker container.
  
2023-01-17 (02 - Getting Started - [001-010])
  - What is Docker Image?
  - Docker Image vs Docker Container?
  - ```
      FROM node
      WORKDIR /app
      COPY package.json /app
      RUN npm install
      COPY  . /app
      EXPOSE 80
      CMD ["node", "server.js"]
    ```
  - ```
      docker build
      docker run -p 3000:80 image-id // 3000 local machine port, 80 docker port
      docker ps
      docker ps -a
      docker stop name
    ```
  - Layers in images
  
2023-01-18 (02 - Getting Started - [011-0])
  - ```
      docker --help
      docker ps     // all running container
      docker ps -a  //all container
      docker ps --help
      docker images // all image
    ```
  - ```docker run ...``` creates new container and start it
  - We can restart existing container by ```docker start container-name```. get the container name using ```docker ps -a```
  - ```docker run -p 3000:80 image-id``` runs container in attached mode. the console is blocked and shows log
  - ```docker run -p 3000:80 -d image-id``` -d is used to run container in detach mode. console is free.
  - we can attach again to a running container using ```docker attach container-name```
  - ```
        docker logs container-name  // get past logs
        docker logs -f container-name  // get past and follow logs
        docker start -a container-name // start container in attach mode
     ```
  - remove
    ``` 
      docker rm container-name // remove container
      docker rmi image-id // remove image. image can be removed iff it is not used by any container
      docker run -p 3000:80 -d -rm image-id //auomatically removes the container when stopped
    ```
  - copy file/folder
  ```
      docker cp test/. container-name:/test // copies all files from local test folder to container test folder
      docker cp container-name:/test/. test // copies all files from container test folder to local test folder
  ```
  - copy helps adding or removing some changes without rebuilding image
  - can be useful to copy logs from container to local machine
  - image tag and container name
  ```
      docker run -p 3000:80 --name custom-name image-id //set custom name of container
      docker build -t repository:tag  //repository is general name - app_name, tag is specifier - version_name or latest...
  ```
