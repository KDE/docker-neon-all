# KDE neon Docker images - All packages

Updated daily with the latest from KDE neon, itself automatically updated with the latest KDE software.

## Running

Best run from the neondocker script:
https://community.kde.org/Neon/Docker

Flavours available are: `kdeneon/all:unstable`, `kdeneon/all:testing`, `kdeneon/all:user`, `kdeneon/all:plasma`

For flavours with all applications installed see `kdeneon/all`.

By default it will run a full session with startkde on DISPLAY=:1, you can use Xephyr as an X server window.

```
Xephyr -screen 1024x768 :1 &
docker run -v /tmp/.X11-unix:/tmp/.X11-unix kdeneon/all:unstable
```

Or you can tell it to run on DISPLAY=:0 and run a single app

```
xhost +
docker run -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=:0 --security-opt seccomp=unconfined kdeneon/all:unstable dolphin
```
