# What is this?
* Docker container
* Steam
* Ubuntu 18.10 (cosmic)
* Very latest free amdgpu drivers from the [oibaf ppa](https://launchpad.net/~aphics-drivers)
* Vulkan
* Video
* Audio

# Functionality

### Working:
* 100%

### Not Working:
* Nothing found yet. If you run into any problems, need any extra dependencies or know of any improvements or fixes, please let me know so this can be improved.

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
        sleepiestmario/steam-amdgpu:cosmic
```
