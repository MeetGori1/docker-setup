# docker-setup

**Set up Docker on Cloud Incatance**

-> install docker on ubuntu:

```
sudo apt install docker.io
docker --version
```

-> install docker compose on ubuntu:

```
DOCKER_CONFIG=${DOCKER_CONFIG:-$HOME/.docker}
mkdir -p $DOCKER_CONFIG/cli-plugins
curl -SL https://github.com/docker/compose/releases/download/v2.34.0/docker-compose-linux-x86_64 -o $DOCKER_CONFIG/cli-plugins/docker-compose
chmod +x $DOCKER_CONFIG/cli-plugins/docker-compose
docker compose version
```
---
**Docker Commands**
1. list current running containers
    ```
   docker ps
   ```
2. list all containers
   ```
   docker ps -a
   ```

3. Stop All running containers
   ```
   sudo docker stop $(sudo docker ps -a -q)
   ```
4. Remove all containers
   ```
   sudo docker rm $(sudo docker ps -a -q)
   ```
5. remove all images
   ```
    sudo docker rmi -f $(docker images -q)
   ```

   ---
   **Push image to docker hub**
   1. need to add dockerfile in code
   2. then build image from it
       ```
          docker build -t <image-name> .
       ```
   3. run in detach mode
      ```
      docker run -d -p 3000:3000 traveling-site-image
      ```
   4. then commit
      ```
      docker commit <container name> <new image name>
      ```
   5. then tag image
      ```
      docker tag <new image name> <username/newimagename:tag> 
      ```
   6. then login to docker
      ```
      docker login
      ```
   7. then push to docker hub
      ```
      docker push <username/newimagename:tag>
      ```
