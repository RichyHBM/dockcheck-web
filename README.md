# DockCheck
## All cred goes to Mag37 making this amazing script!
### This image use dockcheck provided by Mag37.
[Dockcheck @github/Mag37](https://github.com/mag37/dockcheck)
-------

### A script checking updates for docker images without the need of pulling - then having the option to auto-update.

This image provide an webpage running as a container.

<img alt="logo" src="https://i.imgur.com/1unSupa.png">



### Bugs and fixes

1. <s>Cronjob not working properly</s> <b>(Fixed 2023-01-27)</b>


-------
Checking for new images at startup and once a day at midnight.


```yml
version: '3.2'
services:
  dockcheck-web:
    container_name: dockcheck-web
    image: 'palleri/dockcheck-web:latest'
    restart: unless-stopped
    ports:
      - '80:80'
    volumes:
      - ./data:/var/www/html
      - /var/run/docker.sock:/var/run/docker.sock
```

