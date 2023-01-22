# Managing Data & Working with Volumes 
  - Container can read and write data to local machine via volume and bind mount
  - All data are associated with the container. if you remove the container, data will also removed
  - Annonymous volume - ```docker run -v /app/data ...```
  - Named volume - ```docker run -v name:/app/data ...```
  - Bind Mount - ```docker run -v /path/to/code:/app/code ...```

### Volume
  - Managed by docker
  - Volume is great for persistent data
  - Volumes are folders on host machine which are mapped into container folder.
  - Changes in either folder will be reflected into the other folder
  - So even if container is removed, data will be stored in host machines volume
  - Volumes are two types
    - Annonymous volume
      - Closely attached to container. 
      - Survives container shutdown and restart
      - Gets removed with container
      - Can not be shared accross containers
      - Since it is annonymous, can't be re-use, even on same image
      - CMD 
        ```
          add VOLUME ["docker-path"] to Dockerfile
          or add -v docker-path to run cmd
          docker run -d -p 3000:80 --rm --name feedback-app -v /app/feedback feedback-app-image
        ```
    - Named volume
      - Not tied to any specific container
      - Survive container shutdow, restart and also removal of container
      - Doesn't gets deleted if we delete container. 
      - Can be shared data accross multiple container
      - Can be re-use
      - CMD
        ```
          -v local-volume-name:docker-path //named volume
          docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback feedback-app-image
          docker volume ls
          docker volume --help
        ```

### Bind Mount
  - Managed by user
  - Bind Mount is great for persistent and editable data
  - Not tied to any specific container
  - Survive container shutdow, restart and also removal of container
  - Can be shared data accross multiple container
  - Can be re-use
  - Ideal for codebase directory. Updating code no need to build new image.
  - Allow bind mount directory to access by docker
    ```Docker Desktop > Preferences > Resources > File Sharing > Add Directory``` 
  - ```-v absolute-path:docker-path```
  - ```docker run -d -p 3000:80 --name feedback-app -v feedback:/app/feedback -v "/Users/subrata/Desktop/Docker/003-003-A:/app" feedback-app-image```
  - This command will fail because node_moudules dir in local dir will overwrite docker container dir
  - In that case we can add node_module as annonymous volume
  - ```docker run -d -p 3000:80 --name feedback-app -v feedback:/app/feedback -v "/Users/subrata/Desktop/Docker/003-003-A:/app" -v /app/node_modules feedback-app-image```
  - By default volumes and bind mounts are bi-synchrounous. Every change in local machine will propagate to docker and vise versa.
  - So, for source code directory docker container should not change local dir.
  - Volumes can be declared as read only ```local-dir:container-dir:ro```
  - ```docker run -d -p 3000:80 --name feedback-app -v feedback:/app/feedback -v "/Users/subrata/Desktop/Docker/003-003-A:/app:ro" -v /app/node_modules feedback-app-image```


### Good read
  - Why we need ```COPY . .``` when we are using bind mount?
    - If we use bind mount, COPY is not required. But we use bind mounts only for development purposes. So when we deploy the image without bind mount, it will fail.
  - .dockerignore
    - COPY . . copies all the files including node_modules and some other files we don't need to copy. So to ignore those files, we can add them to .dockerignore file / folder.
  - ENVironment Variables
    - Pass certain piece of data from outside to container
    - Add ```ENV Name Value``` to **Dockerfile**
    - We can update environment variable when running container with ```--env NAME:VALUE```
    - Environment variables are accessed by the application
    - Environment variables can be set in some other files. ```.env-dev```. When running the container we have to select the environment file with ```--env-file ./.env-dev```
  - Build ARGuments
    - Pass certain piece of data from outside to container
    - Add ```ARG Name = Value``` to **Dockerfile**
    - Arguments can not be used in code 
    - Can be used in Dockerfile, but not in CMD
    - Can be used when running container to overwrite the default argument. ``` --build-arg NAME=VALUE```
    - It can be useful to have same images for multiple container with different arguments.
    - Server port can be a good example to set in ARG
