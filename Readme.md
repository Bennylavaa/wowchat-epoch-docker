WoWChat-Epoch Docker
==============

WoWChat-Epoch is a Discord integration chat bot for Project Epoch.

This repo builds a docker image to run [WoWChat-Epoch](https://github.com/Bennylavaa/wowchat-epoch).

The architectures supported by this image are:

| Architecture |
| :----: |
| amd64 |
| armv8 |
| armv7 |
| armv6 |

---
### docker-compose 
```
---
version: "3"

services:
  wowchat:
    image: doctorbeefy/wowchat-epoch:latest
    container_name: wowchat
    volumes:
      - path/to/config/wowchat.conf:/wowchat.conf
    restart: unless-stopped
```

### docker CLI

```
$ docker run -d \
  --name=wowchat \
  -v path/to/config/wowchat.conf:/wowchat.conf \
  --restart unless-stopped \
  doctorbeefy/wowchat-epoch:latest
```

---
Edit the https://github.com/Bennylavaa/wowchat-epoch/blob/master/src/main/resources/wowchat.conf to your needs and copy it into your /path/to/config directory. Now restart or deploy the container to apply the config changes.
