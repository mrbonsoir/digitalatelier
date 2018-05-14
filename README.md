## digitalatelier

Yet another docker, this time I try to pack all the necessary stuffs I need if I want to work on my images. Since my *digital atelier* is made of a *jupyter notebook*, *Python code* and access to *hugin*, that's what you will find here, not to forget *imagemagick* of course.

### How to build and start the container?
You need to the run the script:
```
$path/digitalatelier/docker.sh
```
that will simply build the image or add modifications to existing docker image (e.g. to add a missing Python module) by calling the following docker command ``docker build . -t image_name``. Each time this command is ran, if the docker container is already active, it will ask you if you want to re-start it.


### How to stop the container?
Run the command:
```
$docker container ls
```
which should return the list of active docker containers:
```
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS               NAMES
49c44c77ed46        digitalatelier         "/bin/sh -c /digitala…"   16 minutes ago      Up 16 minutes       8888/tcp            random_name
```
then do
```
$kill docker random_name
```

### How to delete all containers?
```
$docker rm $(docker ps -a -q)
```

### How to delete all images?
```
$docker rm $(docker images -q)
```
