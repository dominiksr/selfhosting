# Pi-hole

### Install docker/docker-compose.
```
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```
### Start docker compose
```
sudo docker compose up -d
```
### Diable stub resolver on fedora/ubuntu.
```
sudo sed -r -i.orig 's/#?DNSStubListener=yes/DNSStubListener=no/g' /etc/systemd/resolved.conf
sudo systemctl restart systemd-resolved
```
### Change password
```
sudo docker exec -it pi-hole-pihole-1 /bin/bash
pihole -a -p # and enter password
exit
```

Sources: \
https://github.com/pi-hole/docker-pi-hole \
https://github.com/pi-hole/docker-pi-hole/blob/master/examples/docker-compose-nginx-proxy.yml \
https://docs.docker.com/engine/install/ubuntu
