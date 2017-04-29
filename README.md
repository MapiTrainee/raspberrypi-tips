# raspberrypi-tips

## Raspbian installation
### Formatting SD card with diskpart on Windows 10
```
cmd -> diskpart
list disk
select disk #sd_card_disk_number
clean
create partition primary
select partition 1
active
format FS=FAT32 quick
assign letter=W
```

### Enable SSH before turning on the PI
```
echo>W:\ssh
```

## Using a standard web cam
_Used camer: Msonic MR1803E_
```
sudo apt-get update && sudo apt-get upgrade
sudo apt-get install fswebcam
fswebcam -r 640x480 --no-banner myimage.jpg
```
