## 👋 Welcome to proftp 🚀  

proftp README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update proftp
```
  
## Install and run container
  
```shell
dockerHome="/var/lib/srv/$USER/docker/casjaysdevdocker/proftp/proftp/latest/rootfs"
mkdir -p "/var/lib/srv/$USER/docker/proftp/rootfs"
git clone "https://github.com/dockermgr/proftp" "$HOME/.local/share/CasjaysDev/dockermgr/proftp"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/proftp/rootfs/." "$dockerHome/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-proftp-latest \
--hostname proftp \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$dockerHome/data:/data:z" \
-v "$dockerHome/config:/config:z" \
-p 80:80 \
casjaysdevdocker/proftp:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/proftp
    container_name: casjaysdevdocker-proftp
    environment:
      - TZ=America/New_York
      - HOSTNAME=proftp
    volumes:
      - "/var/lib/srv/$USER/docker/casjaysdevdocker/proftp/proftp/latest/rootfs/data:/data:z"
      - "/var/lib/srv/$USER/docker/casjaysdevdocker/proftp/proftp/latest/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/proftp
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/proftp" "$HOME/Projects/github/casjaysdevdocker/proftp"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/proftp"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
