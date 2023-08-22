# Bitwarden docker/docker-compose

### Create a bitwarden user.
```
sudo adduser bitwarden
```
### Add the bitwarden user to the docker group.
```
sudo usermod -aG docker bitwarden
```
### Create a bitwarden directory and set permisions.
```
sudo mkdir /opt/bitwarden
sudo chmod -R 700 /opt/bitwarden
sudo chown -R bitwarden:bitwarden /opt/bitwarden
```
### Download the Bitwarden installation script and install.
```
curl -Lso bitwarden.sh "https://func.bitwarden.com/api/dl/?app=self-host&platform=linux" && chmod 700 bitwarden.sh
./bitwarden.sh install
```
### Change "localhost" in config file.
```
# bwdata/config.yml
(...)
url: https://192.168.xxx.xxx
(...)
```
### Change adminSettings__admins to access to the admin portal.
```
# bwdata/env/global.override.env
(...)
adminSettings__admins=admin@example.com
(...)
```
```
./bitwarden.sh rebuild
./bitwarden.sh restart
```

Sources: \
https://bitwarden.com/help/install-on-premise-linux \
https://bitwarden.com/help/certificates
