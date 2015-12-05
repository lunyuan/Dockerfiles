# Apache2 + PHP5 + phpPgAdmin on Debian Jessie

[![docker hub](https://img.shields.io/badge/docker-image-blue.svg?style=flat-square)](https://registry.hub.docker.com/u/lunyuan/phppgadmin/)

## Docker run
    docker run \
      --name postgres
      -d 
      -e POSTGRES_PASSWORD=12345 
      -p 5432:5432 
      postgres

    docker run \
      --name phppgadmin \
      --link postgres:db \
      -d \
      lunyuan/phppgadmin
