# ITI - Docker Lab 🐋

## Task 1: Working with Docker Hello-world Image
### Objective
Learn how to run a container using the hello-world image and manage containers and images.

### Steps
#### 1. Run a Container with hello-world Image
```bash  sudo docker run hello-world
```
#### 2. Check Container Status and Explain
```bash docker ps
```
    Status: executed and stopped
#### 3. Start the Stopped Container
```bash docker start amazing_bose
```
#### 4. Remove the Container
```bash docker rm amazing_bose
```
#### 5. Remove the Image
```bash docker rmi hello-world
```
---

## Task 2: Running Container with Ubuntu Image
### Objective
Run an Ubuntu container in interactive mode, create a file inside it, and manage containers.

### Steps
#### 1. Run Ubuntu Container in Interactive Mode
```bash
sudo docker pull ubuntu
docker run -it ubuntu
```
#### 2. Create a File inside the Container
```bash
touch hello.txt
```
#### 3. Stop and Remove the Container
```bash
exit
docker rm interesting_cannon
```
#### 4. Check File Status
```bash not found
```
#### 5. What happened to hello-docker file?
```bash removed
```
#### 6. Remove All Stopped Containers
```bash docker container prune y
```
#### 7. Bonus: Remove All Containers in One Command
```bash docker rm $(docker ps -aq)
```

---
## Task 3: Creating a Custom Nginx Docker Image
### Objective
Create a custom Docker image using Nginx and a local HTML file.

### Steps
#### 1. Create a Local HTML File
```bash nano index.html
```
#### 2. Write Dockerfile and Copy the HTML file to the Docker Image
```bash
nano Dockerfile
docker build -t custom-nginx .
```
#### 3. Run Container with New Image
```bash custom-nginx
```

#### 4. Test the Container, open your browser and navigate to http://localhost:8088 to check if everything is okay
```bash Works fine
```

