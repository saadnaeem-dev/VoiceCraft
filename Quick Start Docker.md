### 1. clone the repo on in a directory on a drive with plenty of free space
```
git clone git@github.com:jasonppy/VoiceCraft.git
cd VoiceCraft
```

### 2. assumes you have docker installed with nvidia container container-toolkit (windows has this built into the driver)
```
https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/1.13.5/install-guide.html
sudo apt-get install -y nvidia-container-toolkit-base || yay -Syu nvidia-container-toolkit || echo etc...
```

### 3. First build the docker image
```docker build --tag "voicecraft" .```

### 4. Try to start an existing container otherwise create a new one passing in all GPUs
```
``./start-jupyter.sh  # linux
start-jupyter.bat   # windows
```

### 5. now open a webpage on the host box to the URL shown at the bottom of:
```docker logs jupyter```

### 6. optionally look inside from another terminal
```
docker exec -it jupyter /bin/bash
export USER=(your_linux_username_used_above)
export HOME=/home/$USER
sudo apt-get update
```

### 7. confirm video card(s) are visible inside container
```
nvidia-smi
```

### 8. Now in browser, open inference_tts.ipynb and work through one cell at a time
> echo GOOD LUCK