# Docker Installation Guide

This docker installation guide is based off the Docker's official website https://docs.docker.com/

## Step 1

Cloning this repository from Docker Docs https://docs.docker.com/get-started/workshop/02_our_app/

```c
git clone https://github.com/docker/getting-started-app.git
```

## Step 2

Adding **Dockerfile** with this content

```dockerfile
# syntax=docker/dockerfile:1

FROM node:lts-alpine
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
EXPOSE 3000
```

## step 3

Open to the apps **Directory**

```
cd /path/to/getting-started-app
```

Create an image then run docker build

```
docker build -t getting-started .
```

Then wait for the build to finish.

![docker image 1](https://github.com/CodeArisu/cs19-final/blob/main/images/docker1.png?raw=true)

note: make sure that the "Dockerfile" is correctly spelled and capitalized, otherwise it will return an error.

## step 4

Run the container

```
docker run -d -p 127.0.0.1:3000:3000 getting-started
```

Then go to browser and type http://localhost:3000, the app should be present and fully working.

![docker image 3](https://github.com/CodeArisu/cs19-final/blob/main/images/docker3.png?raw=true)

## step 5 (Optional) 

If its not showing try (on terminal) to see if the container or image is running or you mistyped/misconfig the project.

```
docker ps
```

This should display to your terminal:

![docker image 2](https://github.com/CodeArisu/cs19-final/blob/main/images/docker2.png?raw=true)

If you want to stop the container use:

```
docker stop <container_name_or_id>
```

note: should be inside the directory in order to work.

## Demo Video

Here is the link for the setup: https://drive.google.com/file/d/1ZOsOKv9JnQ_-GJVcdgS2pROqXW8TsuIK/view?usp=sharing

# Getting started

This repository is a sample application for users following the getting started guide at https://docs.docker.com/get-started/.

The application is based on the application from the getting started tutorial at https://github.com/docker/getting-started
