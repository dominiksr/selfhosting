# Nextcloud snap

### Install.
```
sudo snap install nextcloud
```
### Enter a username and strong password to create the first administrator account, and click Install.

### Edit the main NextCloud configuration file.
### Add nextcloud IP, DNS name, IP nextcloud have over VPN in `/var/snap/nextcloud/current/nextcloud/config/config.php`.
```
sudo vim /var/snap/nextcloud/current/nextcloud/config/config.php
```
```
(...)
'trusted_domains' =>
array (
    0 => 'localhost',
    1 => 'nextcloud.lan',
    2 => '192.168.xxx.xxx',
    3 => 'xxx.xxx.xxx.xxx',   
(...)
```

### Enable self signed certificate.
```
sudo /snap/bin/nextcloud.enable-https self-signed
```

### (optional) Change ports if you use something else on this server.

```
sudo snap set nextcloud ports.http=81 ports.https=444
```

### (optional) Enable removable media (external storage).
```
sudo snap connect nextcloud:removable-media
```
### (optional) Enable system monitoring.
```
sudo snap connect nextcloud:network-observe
```


Sources: \
https://github.com/nextcloud-snap/nextcloud-snap \
https://github.com/nextcloud-snap/nextcloud-snap/wiki/Managing-encryption \
https://github.com/nextcloud-snap/nextcloud-snap/wiki/Port-configuration \
https://www.vultr.com/docs/how-to-install-nextcloud-on-ubuntu-22-04-with-snap
