# Building Multi-Container Applications with Docker
  - Create network. ```docker network create mynet```
  - Run mongodb under ```mynet```. ```docker run -d --rm --network mynet --name mydb mongo```
  - Set ```mydb`` as domain name in code base, since server and db will be under same docker network. So, they will communicate by their container name.
  - Build backend image. ```docker build -t mybackendimage .```
  - Run backend container under ```mynet``` and expose port 80 to localhost. We expose server port 80 to localhost port 80, because our front end will access backend through local machine. Frontend is in react. React runs on local machines browser, so even if react app runs under ther same network as backend, it can't communicate backend via container name. ```docker run -d --rm -p 80:80 --network mynet --name mybackend mybackendimage```
  - Set ```localhost``` as domain name in code base, since frontend will communicate server via local machine.
  - Build frontend image. ```docker build -t myfrontendimage .```
  - Run backend container under ```mynet``` and expose port 3000. Also run it in interactive mode, because interactive mode is mandatory for react app. ```docker run -d -it --rm -p 3000:3000 --network mynet --name myfrontend myfrontendimage```

### Persistend and secure data (mongodb)
  - Persisting mongodb
    - When the mongodb container is removed, the data is also gone. Because the data is stored somewhere in the container.
    - Mongodb stores data at ```/data/db``` directory inside container.
    - So, we have to add a volume to sync data to our prefered storage.
    - So, all data will be sync in your prefered location and load when you start the mongo container.
    - ```docker run -d --rm -v saome-path:/data/db --network mynet --name mydb mongo```
  - Secure mongodb
    - To make mongodb secure, we have to add username and password as environment.
    - ```docker run -d --rm -v saome-path:/data/db --network mynet --name mydb -e MONGO_INITDB_ROOT_USERNAME=subrata -e MONGO_INITDB_ROOT_PASSWORD=pass mongo```
    - Now the mongodb container is secured with username and password.
    - To access data from this secured database, we have to use username password.
    - ```mongodb://mydb:27017/dbname``` this will not work
    - ```mongodb://subrata:pass@mydb:27017/dbname?authSource=admin' this will work
    - Also, we can add environment variable and use it in code
    - DONE

### Live source code update (Backend)
  - When creating image, docker takes a snapshot of current codebase. So when there is a change in codebase, we need to create a new image and run a container using it
  - But we can use volume to sync code changes in real time
  - ```docker run -d --rm -p 80:80 --network mynet --name mybackend -v /Users/subrata/Desktop/Docker/005-A/backend:/app -v logs:/app/logs -v /app/node_modules mybackendimage```
  - ```-v /Users/subrata/Desktop/Docker/005-A/backend:/app``` - here we bind mount project directory to docker app directory, so every change in our local project will sync to docker.
  - ```logs:/app/logs``` - here we added a named volume to logs directory. So that it overwrites the bind mount. In that case the /app/logs directory won't sync with bind mount, instead it will sync with the named volume.
  - ```-v /app/node_modules``` - here we overwrite node modules from syncing local to docker by overwriting by annonymous volume.
  - Volume rule: if there are multiple volume, the volume with larger docker path wins and overwrite others.
  - With that code changes will sync to docker, but changes won't reflect. Because when we run the container, we use ```node app.js``` command to run the node server. So it takes a snapshot of the current codebase. So, we have to restart the container to see those changes.
  - In that case, we have to add an extra dependency (nodemon), which watches the project folder for file changes and if any change detected, it restarts the node server automatically.
  - Add those to package.json
    ```
        "scripts": {
          "test": "echo \"Error: no test specified\" && exit 1",
          "start": "nodemon app.js"
        },
        "devDependencies": {
          "nodemon": "^2.0.20"
        }
    ```
  - Also have to change run command in Dockerfile. ```CMD ["node","app.js"]``` -> ```CMD ["npm","start"]```
  - Now create a new image and run the container.
  - DONE

### Live source code update (Frontend)
  - All the code are on src folder. So we have to bind only the src folder. And no overwrite needed.
  - ```docker run -d -it --rm -p 3000:3000 --network mynet --name myfrontend -v /Users/subrata/Desktop/Docker/005-A/frontend/src:/app/src myfrontendimage```
  - We don't need anything to watch code changes. React already have those configuration.
  - DONE


Code: https://github.com/SbrTa/Notes/blob/main/Docker/code/005-A.zip
