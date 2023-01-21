# Managing Data & Working with Volumes 
  - All data are associated with the container. if you remove the container, data will also removed

### Volume
  - Managed by docker
  - Volume is great for persistent data
  - Volumes are folders on host machine which are mapped into container folder.
  - Changes in either folder will be reflected into the other folder
  - So even if container is removed, data will be stored in host machines volume
  - Volumes are two types
    - Annonymous volume: Closely attached to container. Gets deleted with container.
    - Named volume: Doesn't gets deleted if we delete container. Used commonly.
  - cmd
    ```
      -v local-volume-name:docker-dir //named volume
      docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback feedback-app-image //names volume
      docker volume ls
      docker volume --help
    ```

### Bind Mount
  - Managed by user
  - Bind Mount is great for persistent and editable data
  - 
