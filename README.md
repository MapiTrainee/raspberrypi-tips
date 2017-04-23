# raspberrypi-tips

## Using a standard web cam
_Used camer: Msonic MR1803E_

```
sudo apt-get update && sudo apt-get upgrade
sudo apt-get install fswebcam
fswebcam -r 640x480 --no-banner myimage.jpg
```