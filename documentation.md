---
---

# VIBE Cloud

Sign up instructions here.

# Docker

The VIBE notebooks can be run within a Docker container by using the included Dockerfile to create a local image of the VIBE environment. The Dockerfile is based on the [docker-stacks](https://github.com/jupyter/docker-stacks) SciPy notebook example provided by Jupyter. Commands for running the Jupyter notebooks with Docker are given below.

```bash
# Build a Docker image from the Dockerfile
# Run this command from within the folder containing the Dockerfile
# In this example the image will be named `myimage`
docker build -t myimage .

# Create and run a new container and publish its ports to the host machine
# In this example the created container is named `myvibe`
docker run --name myvibe -it -p 8888:8888 myimage bash

# From within the container run JupyterLab using the command shown below. This
# command will create a URL that can be copied and pasted into the web browser
# of the local machine.
jupyter lab --ip 0.0.0.0 --no-browser --allow-root

# Atlernatively you can create, run docker container and jupyterlab using the
# command below. The generated URL can be copied into web browser of local
# machine.
docker run --rm -p 8888:8888 -e JUPYTER_ENABLE_LAB=yes -v "$PWD":/home/jovyan/work myimage
```

To quit the Jupyter notebook, choose File then Shutdown from the JupyterLab menu. Then, quit the Docker container by entering the `exit` command in the terminal.

Use the following commands to restart the container and run JupyterLab.

```bash
# Start the existing `myvibe` container and run JupyterLab from the container
# Don't forget to copy and paste the URL into your local web browser
docker start myvibe
docker exec -it myvibe bash
jupyter lab --ip 0.0.0.0 --no-browser --allow-root

# After exiting the container terminal session with `exit`, stop the running
# container with the following command
docker stop myvibe

# If `myvibe` was successfully stopped, it will not show in the list of running
# containers. View the list of running contains with the `ps` command.
docker ps
```

The Docker image and container take up several gigabytes of storage on the local machine. To remove the container and image from your computer, perform the commands shown next.

```bash
# Remove the `myvibe` container
docker rm myvibe

# Next, remove the Docker image named `myimage`
docker rmi myimage
```
