# ITI - Docker Lab 🐋

## Part 1: Run a container using nginx image, and mount a directory from your host into the Docker container. example: /home/samy/nginx:/home/nginx (bind mount)

### Steps
#### 1. Run a container with Nginx and Bind Mount
```bash
sudo docker run -d -p 8090:80 --name my-nginx -v /home/azema/nginx:/home/nginx nginx:latest
```

## Part 2: Running Container with Ubuntu Image

### Steps
#### 1. Create 2 docker network (net-1 & net-2)
```bash
sudo docker network create net-1
sudo docker network create net-2
```
#### 2. Run 2 new containers using nginx:alpine image, and attach the net-1 to them.
##### For net-1:
```bash
sudo docker run -d --name nginx1 --network net-1 nginx:alpine
sudo docker run -d --name nginx2 --network net-1 nginx:alpine
```
#### 3. Run another 1 new containers using nginx:alpine image, and attach the net-2 to them.
##### For net-2:
```bash
docker run -d --name nginx3 --network net-2 nginx:alpine
```

#### 4. Inspect Containers:
```bash
docker inspect nginx1 nginx2 nginx3
```
#### 5. Enter a container in the net-1 network and try to ping a container in the net-2 network (What do you notice?) 
```bash
sudo docker exec -it nginx1 sh
```
##### Can not Ping the container

#### 6. Enter a container in the net-1 network and try to ping the other container in the same network (What do you notice?) 
##### Can Ping

#### 6. Explain the difference between Docker volumes and Bind Mount.
Docker Volumes:

Volumes are a way to persist data independently of the container's lifecycle.
They are managed by Docker and provide a layer of abstraction between the container and the host filesystem.
Changes made to data in a volume persist even if the container is stopped or deleted.
Volumes can be shared between multiple containers.
Bind Mounts:

Bind mounts directly link a directory on the host machine to a directory inside the container.
Changes made to the directory on the host are reflected inside the container, and vice versa.
Bind mounts are simpler to set up but tie the container's data directly to the host filesystem.
They are not portable and cannot be shared between containers.
Choosing Between Volumes and Bind Mounts:

Use volumes if you need persistent data that survives container deletion or needs to be shared between containers.
Use bind mounts for development purposes when you want to quickly access and
