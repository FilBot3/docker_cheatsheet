Docker Cheatsheet
=================

Get Docker Information  
```
docker info
```

Download a Docker Image
```
docker pull centos
```

Run an interactive shell with the image
```
docker run -i -t centos /bin/bash
```
This will start the container, and stop when exited

Start a long running Docker Process, "Daemonize"
```
docker run -d centos /bin/bash -c "while true; do echo hello world; sleep 1; done")
```

Show only running containers
```
docker ps
```

Show All Containers
```
docker ps -a
```

Capture a long running docker container UUID
```
JOB_UUID=$(docker run -d centos /bin/bash -c "while true; do echo hello world; sleep 1; done")
```

Stop a running container
```
docker stop $JOB_UUID
```

Start the container back up
```
docker start $JOB_UUID
```

Restart the container
```
docker restart $JOB_UUID
```

Forcibly kill a container
```
docker kill $JOB_UUID
```

Remove a container from the list, ensure that the container is stopped.
```
docker rm $JOB_UUID
```

Bind a container to a specific port
```
docker run -d -p 4444:4444 centos /bin/nc -l 4444
```

Save the container that has been modified
```
docker commit centos user/centos-modified
```

List all downloaded Docker images
```
docker images
```