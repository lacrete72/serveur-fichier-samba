# serveur-fichier-samba

### installation des paquets plus démarrage des services
```
sudo apt install samba
sudo systemctl enable smb
sudo systemctl start smb
```

### création du dossier partagé
```
sudo mkdir -p /srv/samba/partage   // création du dossier partage
sudo chmod 755 /srv/samba/partage  // gestion des droits sur le dossier
sudo chown debian:debian /srv/samba/partage  // changement du propriétaire du dossier
```

### modification du ficher de conf
```
sudo nano /etc/samba/smb.conf
```
### ajouter ces ligne dans le fichier
```
[partage]
  path = /srv/samba/partage
  browseable = yes
  writable = yes
  guest ok = no
  valid users = @sambausers
```

### gestion des utilisateurs
```
sudo smbpasswd -a debian 
sudo groupadd sambausers
sudo adduser debian sambausers
```

### ajout du dossier partage dans windows
ouvrir un cmd et taper la commande
```
NET USE P: \\192.168.72.1\partage
```

