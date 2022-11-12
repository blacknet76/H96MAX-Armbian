# H96MAX-Armbian

Das ist ein Armbian Debian Bullseye Image für die H96 MAX TV Box.

Installations Video
https://youtu.be/uuOujI-yfYU

## Mein selbst erstelltes Image
Download:
https://drive.google.com/file/d/1nU2_yQY3Oh7GQYWXxNAR4u5qr25xtTLU/view?usp=share_link

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

## Kommandos aus dem Video
rk3318-config
```
rk3318-config
```
Pakete aktualisieren
```
apt update
```
armbian-config installieren
```
apt install armbian-config
```
armbian-config
```
armbian-config
```
Pakete aktualisieren
```
apt upgrade
```

IP Adresse anzeigen lasen
```
ip a
```

Rechner neu starten
```
reboot
```

Wlan Konfigurieren
```
nmtui
```

## alternativ die Wlan Treiber für den 2734C Chip
```
cd ~
```
```
wget https://raw.githubusercontent.com/blacknet76/H96MAX-Armbian/main/brcmfmac4334-sdio.rockchip%2Crk3318-box.txt
```
```
sudo cp /lib/firmware/brcm/brcmfmac4334-sdio.rockchip,rk3318-box.txt /lib/firmware/brcm/brcmfmac4334-sdio.rockchip,rk3318-box.bak
```
```
sudo cp brcmfmac4334-sdio.rockchip,rk3318-box.txt /lib/firmware/brcm/brcmfmac4334-sdio.rockchip,rk3318-box.txt
```

Jetzt verhindern wir noch das die Datei vom Update Manager überschrieben wird
```
sudo chattr -i /lib/firmware/brcm/brcmfmac4334-sdio.rockchip,rk3318-box.txt
```

Rechner neu starten
```
sudo reboot
```

Anschließend das Wlan Konfigurieren mit
```
nmtui
```

IP Abfragen
```
ip a
```

Kennwort ändern
```
passwd
```

Box neu starten
```
sudo reboot
```

Wlan Konfigurieren
```
nmtui
```

IP Abfragen
unter wlan0 sollte nun eine IP Adresse stehen
```
ip a
```

Reboot und schauen ob alles funktioniert