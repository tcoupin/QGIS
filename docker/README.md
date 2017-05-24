## Build environment in docker

### Build docker image

The build environment is based on Ubuntu Xenial.

```
docker build -t qgisbuild .
```

### Open a terminal into the container

First you have to allow root user to use your X server : `sudo xhost +local:root`.
TODO : You can make this change permanent ...

```
docker run --name qgis -it -v qgis-data:/root/.qgis -v $PWD/../:/root/qgis -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix:ro qgisbuild /bin/bash
```

Now you can follow instructions from [Install guide](../INSTALL) : compile your qgis and run it.