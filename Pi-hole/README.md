# Pi-hole

### Install docker/docker-compose.
```
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```
### Diable stub resolver on fedora/ubuntu.
```
sudo sed -r -i.orig 's/#?DNSStubListener=yes/DNSStubListener=no/g' /etc/systemd/resolved.conf
sudo systemctl restart systemd-resolved
```

Sources: \
https://github.com/pi-hole/docker-pi-hole \
https://github.com/pi-hole/docker-pi-hole/blob/master/examples/docker-compose-nginx-proxy.yml \
https://docs.docker.com/engine/install/ubuntu
