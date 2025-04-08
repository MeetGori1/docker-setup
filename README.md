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
