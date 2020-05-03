# REQUIREMENTS
- [docker](https://docs.docker.com/get-docker/)
- [docker-compose](http://docs.docker.jp/compose/install.html)
- X window System
  - mac: [XQuartz](https://www.xquartz.org/)
  - windows: [Xming](http://www.straightrunning.com/XmingNotes/)
# USAGE
## build image
```sh
sudo docker-compose build --no-cache
```

## startup container
```sh
sudo docker-compose up -d 
```

## start development
```sh
xhost + 127.0.0.1
sudo docker exec -it electron_dev /bin/bash
```

# ENVIRONMENT
| name            | value                                     
|---              |---                                          |
| username        | docker                                      |
| password        | docker                                      |
| working_dir     | /home/docker/app/src                        |
| mounted vlolume | life_game_electron/src:/home/docker/app/src |
