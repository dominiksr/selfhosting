# Nextcloud snap

### Change ports if you use something else on this server
```
sudo snap set nextcloud ports.http=80
sudo snap set nextcloud ports.https=443
```

### Add nextcloud IP, DNS name, IP nextcloud have over VPN in `/var/snap/nextcloud/current/nextcloud/config/config.php`
```
(...)
array (
    0 => 'localhost',
    1 => 'nextcloud.lan',
    2 => '192.168.xxx.xxx',
    3 => 'xxx.xxx.xxx.xxx',   
(...)
```

Sources: \
https://github.com/nextcloud-snap/nextcloud-snap \
https://github.com/nextcloud-snap/nextcloud-snap/wiki/Port-configuration \
https://github.com/nextcloud-snap/nextcloud-snap/wiki/Managing-encryption
