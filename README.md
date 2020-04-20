# Blinks detection

This repo contains algorithm that detects blinks. If the eyes close more than 2 seconds, the caption "Alert" 
will appear in the screen! Source of a video - a stream from the web camera. This work is an extension of
[this work](https://www.pyimagesearch.com/2017/04/24/eye-blink-detection-opencv-python-dlib/). 
Libraries used in this project you can see in [requirements.txt](https://github.com/ZamiraKholmatova/Blinks_detection/blob/master/requirements.txt).
To work with this project you need to have Python3 and pip. 

## How to run this code?

You have several options to run this code:
1. You can download this repo and run this code on favourite environment. 
But you need to install all libraries noticed in 
[requirements.txt](https://github.com/ZamiraKholmatova/Blinks_detection/blob/master/requirements.txt).
It can be useful to know, how to install dlib. So, you can see instructions [here](https://www.pyimagesearch.com/2017/03/27/how-to-install-dlib/).
2. You need to install [docker](https://docs.docker.com/get-docker/).
To allow contenerized application to work properly, run 
```
xhost +local:docker
```
To know more about it, go [here](http://wiki.ros.org/docker/Tutorials/GUI)
After it you can just run in your terminal 
```
docker run --rm -it --net=host --ipc=host -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix --env="QT_X11_NO_MITSHM=1"  --privileged --device=/dev/video0:/dev/video0 zamirakholmatova/blinks_detection
```
Otherwise, you can build an image from Dockerfile:
```
 docker build -t blinks .
```
And then simply run:
```
docker run --rm -it --net=host --ipc=host -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix --env="QT_X11_NO_MITSHM=1"  --privileged --device=/dev/video0:/dev/video0 blinks
```

```
