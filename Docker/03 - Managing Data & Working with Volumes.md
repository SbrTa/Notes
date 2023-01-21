# Managing Data & Working with Volumes 
  - All data are associated with the container. if you remove the container, data will also removed

### Volume
  - Managed by docker
  - Volume is great for persistent data
  - Volumes are folders on host machine which are mapped into container folder.
  - Changes in either folder will be reflected into the other folder
  - So even if container is removed, data will be stored in host machines volume
  - Volumes are two types
    - Annonymous volume
      - Closely attached to container. Gets deleted with container.
      - cmd 
        ```
          add VOLUME ["docker-path"] to Dockerfile
          or add -v docker-path to run cmd
          docker run -d -p 3000:80 --rm --name feedback-app -v /app/feedback feedback-app-image
        ```
    - Named volume
      - Doesn't gets deleted if we delete container. Used commonly.
      - cmd
        ```
          -v local-volume-name:docker-path //named volume
          docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback feedback-app-image
          docker volume ls
          docker volume --help
        ```

### Bind Mount
  - Managed by user
  - Bind Mount is great for persistent and editable data
  - Allow bind mount directory to access by docker
    ```Docker Desktop > Preferences > Resources > File Sharing > Add Directory``` 
  - ```-v absolute-path:docker-path```
  - ```docker run -d -p 3000:80 --name feedback-app -v feedback:/app/feedback -v "/Users/subrata/Desktop/Docker/003-003-A:/app" feedback-app-image```
  - This command will fail because node_moudules dir in local dir will overwrite docker container dir
  - In that case we can add node_module as annonymous volume
  - ```docker run -d -p 3000:80 --name feedback-app -v feedback:/app/feedback -v "/Users/subrata/Desktop/Docker/003-003-A:/app" -v /app/node_modules feedback-app-image```
