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
cd /etc/apt/keyrings/
wget https://dl.google.com/linux/linux_signing_key.pub
mv linux_signing_key.pub google-key.pub
gpg --dearmor google-key.pub > google-key.gpg
echo "deb [signed-by=/etc/apt/keyrings/google-key.pub.gpg] http://dl.google.com/linux/chrome/deb/ stable main" > /etc/apt/sources.list.d/google-chrome.list
apt update
apt install google-chrome-stable
```
## Installer le logiciel Discord manuellement à partir d'un fichier .deb
```
wget discord.deb "https://discord.com/api/download?platform=linux&format=deb"
mv *=deb discord.deb
dpkg -i discord.deb
```
## Configuration de l'horloge
- Synchronisation sur un serveur spécifique NTP : fichier /etc/systemd/timesyncd.conf
```conf
[Time]
NTP=ntp.univ-rennes2.fr
FallbackNTP=0.debian.pool.ntp.org 1.debian.pool.ntp.org 2.debian.pool.ntp.org 3.debian.
pool.ntp.org
```
- Activer NTP
```
timedatectl set-ntp true
```
- Redémarrer le service
```
systemctl restart systemd-timesyncd
```
- Vérifier la synchronisation
```
timedatectl timesync-status
```
