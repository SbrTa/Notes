# Managing Data & Working with Volumes 
  - all data are associated with the container. if you remove the container, data will also removed
  - Volume helps persisting data
  - Volumes are folders on host machine which are mapped into container folder.
  - Changes in either folder will be reflected into the other folder
  - So even if container is removed, data will be stored in host machines volume
  - Annonymous volumed are closely attached to container. Gets deleted with container
  - Named volume doesn't gets deleted if we delete container
  - cmd
    ```
      -v local-volume-name:docker-dir
      docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback feedback-app
      docker volume ls
    ```
