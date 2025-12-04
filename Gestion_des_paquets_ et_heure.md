# Gestion des paquets sous Linux
## Mise à jour des sources des paquets et des paquets
```
apt update && apt upgrade
```
## Installer un logiciel à partir des dépôts officiels Debian
```
apt install vlc
```
## Installer le logiciel Chrome à partir des dépôts d'un éditeur
```
wget https://dl.google.com/linux/linux_signing_key.pub
mv linux_signing_key.pub google-key.pub
gpg --dearmor google-key.pub > google-key.gpg
echo "deb [signed-by=/usr/share/keyrings/google-key.pub.gpg] http://dl.google.com/linux/chrome/deb/ stable main" > /etc/apt/sources.list.d/google-chrome.list
```
