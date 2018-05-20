# Common conmmand

## Check version and info
```sh
$ nvidia-docker info
```
## Check available images or containers
```sh
$ nvidia-docker image ls
$ nvidia-docker container ls
```

## Build the docker
```sh
$ sudo nvidia-docker build . -t #name
```

## Run the docker
```sh
$ sudo nvidia-docker run -it -p 8001:8888 --name #containerName -v /home/yy/Documents/Docker/docker_fold:/usr/app #imageName:#imageTag /bin/bash
```

## Continue the existing docker
```sh
$ sudo nvidia-docker start #dockername
$ sudo nvidia-docker attach #dockername 
```


## Remove image or container
```
$ docker rmi #imageName
$ docker rm #imageName
```

## Open second terminal for same container
```
$ docker exec -it #containerName /bin/bash
```

## Fail to start container bug fix
```
$ sudo mknod -m 666 /dev/nvidia-uvm-tools c $(grep nvidia-uvm /proc/devices | awk '{print $1}') 1
```
