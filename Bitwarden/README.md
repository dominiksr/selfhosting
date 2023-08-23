# Bitwarden docker/docker-compose

### Install docker/docker-compose.
```
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```
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
### Download the Bitwarden installation script and install. Complete the prompts.
```
curl -Lso bitwarden.sh "https://func.bitwarden.com/api/dl/?app=self-host&platform=linux" && chmod 700 bitwarden.sh
./bitwarden.sh install
```
### Change "localhost" in config file.
<pre>
# bwdata/config.yml
(...)
url: https://192.168.xxx.xxx
(...)
</pre>
### Change adminSettings__admins to access to the admin portal.
<pre>
# bwdata/env/global.override.env
(...)
adminSettings__admins=admin@example.com
(...)
</pre>
```
./bitwarden.sh rebuild
./bitwarden.sh restart
```

Sources: \
https://bitwarden.com/help/install-on-premise-linux \
https://bitwarden.com/help/certificates \
https://docs.docker.com/engine/install/ubuntu
