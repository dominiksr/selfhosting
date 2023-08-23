# VS Code server

### Install docker/docker-compose.
```
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```
### Write sudo and user password in .env file.

### Check ID/Group number and fill PUID/GUID
```
id username
```
<pre>
# docker-compose.yml
(...)
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=Etc/UTC
(...)
</pre>
### Create config and worspace folder.
```
mkdir config
mkdir repos
```
### Start docker compose.
```
docker compose up -d
```

Soures: \
https://github.com/coder/code-server \
https://hub.docker.com/r/linuxserver/code-server \
https://docs.docker.com/engine/install/ubuntu
