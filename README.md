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
### Using Win32DiskImager to write Raspbian to SD Card
### Enabling SSH before turning on the PI
```
echo>W:\ssh
```
### Configuration
```
sudo raspi-config
```
### Setting static network address
```
sudo nano /etc/dhcpcd.conf
```
```
interface eth0

static ip_address=192.168.1.100/24
static routers=192.168.1.1
static domain_name_servers=192.168.1.1

interface wlan0

static ip_address=192.168.1.200/24
static routers=192.168.1.1
static domain_name_servers=192.168.1.1
```
### Setting WiFi
```
#sudo iwlist wlan0 scan
sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
[ROOT] wpa_passphrase "ssid" "password" >> /etc/wpa_supplicant/wpa_supplicant.conf
sudo wpa_cli reconfigure
```

## Using a standard web cam
_Used camer: Msonic MR1803E_
```
sudo apt-get update && sudo apt-get upgrade
sudo apt-get install fswebcam
fswebcam -r 640x480 --no-banner myimage.jpg
```

## Check public IP
```
curl ipinfo.io/ip
```
