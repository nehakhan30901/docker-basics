This repository contains a tutorial for introduction to docker. A couple of simple images
will be used to understand how to build, run and manage your application with containers.

Install Docker:

# https://docs.docker.com/install/

Verify installation

```
docker run hello-world
```

Run a python application in container using python 2 base image from docker hub.

```
docker image build -t demo-py:v0.0 python_image/
```

To see the built image
```
docker images
```

Run Python2 container from the image

```
docker run --rm --name "demo-py-run" demo-py:v0.0
```

Update base image to use python3 instead.

```
docker image build -t demo-py:v1.0 python_image/
```

To list all images
```
docker images demo*
```

Run a new container with Python3 image and check the difference in the results of division for verification.
```
docker run --rm --name "demo-py3-run1" demo-py:v1.0
```

Update code to fix the bug.

```
docker image build -t demo-py:v1.1 python_image/
```

Run a new container with Python3 image and check the difference in the results of division for verification.
```
docker run --name "demo-py-run2" demo-py:v1.1 
```

To list all running containers
```
docker ps -a

```
To restart a stopped containers. option -a displays STDOUT/STDERR
```
docker start -a demo-py-run2
```

To remove an unused container container

```
docker rm demo-py-run2
```

To stop a running container

```
docker stop demo-py2-run1
```

To remove an image

```
docker rmi demo-py:v1.0
```

To remove all the containers

```
docker rm $(docker ps -a -q)
```

To remove all images

```
docker rmi $(docker images demo* -q)
```


# PART 2: Linux container

Build the container with alpine image
```
docker image build -t demo-linux linux_image/
```

Run the container 
```
docker run --name "demo-linux-run" demo-linux
```

Log into shell
```
docker exec -it demo-linux-run sh

```

Stop the running container

```
docker stop demo-linux-run
```