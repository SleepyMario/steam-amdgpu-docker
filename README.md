# What is this?
* Docker container
* Steam
* Ubuntu 18.04/18.10/19.04
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
        -v /tmp/.X11-unix:/tmp/.X11-unix \
        --device /dev/dri/:/dev/dri \
        -v /run/user/$UID/pulse/native:/tmp/pulse \
        -v /dev/shm:/dev/shm \
        -v /etc/machine-id:/etc/machine-id \
        -v /dev/kfd:/dev/kfd \
        -v /dev:/dev \
        -v /PATH/TO/USER/:/home/steam/ \
        sleepiestmario/steam-amdgpu-bionic:18.04
```

# List of tested games:
* Age of Wonders III
* Dota 2
* Europa Universalis IV
* Civilization V
* Civilization VI
* Sonic & SEGA All Stars Racing
* _Please let me know about any other games, so I can add them to the list._
