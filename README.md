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
![Uploading {1E7B3C3A-58F8-4CDB-9E4E-4FE3DD1B9AB9}.png…]()
