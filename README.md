# What is this?
* Docker container
* Steam
* Ubuntu 18.04 (bionic)/Ubuntu 18.10 (Cosmic)/Ubuntu 19.04 (Disco)
* Very latest free amdgpu drivers from the [oibaf ppa](https://launchpad.net/~oibaf/+archive/ubuntu/graphics-drivers)
* Vulkan
* Video
* Audio

# Functionality

### Working:
* Everything but one. See the next section.

### Not Working:
* Joysticks. Any help/fixes would be greatly appreciated!  

# How to Run 
Edit the command below according to your needs and execute it. 
```sh
docker run -d --rm -ti -e DISPLAY=$DISPLAY \
	--name steam-amdgpu-$BRANCH \
        -v /tmp/.X11-unix:/tmp/.X11-unix \
        --device /dev/dri/:/dev/dri \
        -v /run/user/$UID/pulse/native:/tmp/pulse \
        -v /dev/shm:/dev/shm \
        -v /etc/machine-id:/etc/machine-id \
        -v /dev/kfd:/dev/kfd \
        -v /dev:/dev \
        -v /PATH/TO/USER/:/home/steam/ \
        sleepiestmario/steam-amdgpu:$BRANCH
```
