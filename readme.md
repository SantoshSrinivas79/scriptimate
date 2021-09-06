Generate webm/mp4 videos by animating svg files (e.g. exported from figma or drawn in Inkscape).

# Prerequirements 
You need to have next packages on your system (Ubuntu or Windows WSL2):

```
sudo apt-get install libnss3-dev libatk-bridge2.0-0 libcups2 libgtk-3-0 libgbm-dev ffmpeg
```

(All apart `ffmpeg` required to run pupeeter which is used to generate high-qaulity frames, some taken from here https://gist.github.com/winuxue/cfef08e2f5fe9dfc16a1d67a4ad38a01)s

Required version of ffmpeg >=4.x (Will be installed automatically in Ubuntu 20.04+, when in 18.04 it will be 3.x, which is not compatible)

If you are using custom changable texts, please make sure you have all fonts installed which you use:

```
sudo apt install fonts-roboto
```

# Hello world example


# How to run examples from this repo

1. Pull the repo
2. `cd example`
3. Execute `npx scriptimate@latest -i 1_helloworld.smte`




# Advanced ussage

Under the hood next commands are used:

```
ffmpeg -framerate 25/1 -i frames/%07d.jpg -c:v libx264 -r 25 out.mp4 -y
```

```
ffmpeg -framerate 25/1 -i frames/%07d.jpg -c:v libvpx-vp9 -b:v 2M -r 25 out.webm -y
```
