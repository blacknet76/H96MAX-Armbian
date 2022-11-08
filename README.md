# H96MAX-Armbian

Das ist ein Armbian Debian Bullseye Image für die H96 MAX TV Box

## Mein selbst erstelltes Image
Download:
https://drive.google.com/file/d/1XTGRRoEV5ZZIpqqpJ7IMvUMuyvWYLckC/view?usp=share_link

Mein Image wurde mit folgenden Parametern erstellt
```
./compile.sh  BOARD=rk3318-box BRANCH=current RELEASE=bullseye BUILD_MINIMAL=yes BUILD_DESKTOP=no KERNEL_ONLY=no KERNEL_CONFIGURE=no COMPRESS_OUTPUTIMAGE=sha,gpg,img
```

##  Das Image von jock
https://users.armbian.com/jock/rk3318/

Download:
https://users.armbian.com/jock/rk3318/Armbian_22.05.0-trunk_Rk3318-box_bullseye_current_5.15.35_minimal.img.xz

armbian Forum Thread von jock
https://forum.armbian.com/topic/24085-csc-armbian-for-rk3318rk3328-tv-box-boards/


## Multitool
https://users.armbian.com/jock/rk3318/multitool.img.xz
https://drive.google.com/file/d/1YUOc95bJbCM8Tq44plZ0q1DeJW8-gDE7/view?usp=share_link

## Wlan Treiber für den 2734C Chip
```
cd ~
wget https://raw.githubusercontent.com/blacknet76/H96MAX-Armbian/main/brcmfmac4334-sdio.rockchip%2Crk3318-box.txt
sudo cp /lib/firmware/brcm/brcmfmac4334-sdio.rockchip,rk3318-box.txt /lib/firmware/brcm/brcmfmac4334-sdio.rockchip,rk3318-box.bak
sudo cp brcmfmac4334-sdio.rockchip,rk3318-box.txt /lib/firmware/brcm/brcmfmac4334-sdio.rockchip,rk3318-box.txt
```

Jetzt verhindern wir noch das die Datei vom Update Manager überschrieben wird
```
sudo chattr -i /lib/firmware/brcm/brcmfmac4334-sdio.rockchip,rk3318-box.txt
```

Anschließend das Wlan Konfigurieren mit
```
nmtui
```

IP Abfragen
```
ip a
```

Reboot und schauen ob alles funktioniert