# docker-proxy

This scipts create `docker-proxy` container from image [jwilder/nginx-proxy](https://hub.docker.com/r/jwilder/nginx-proxy/) that automate Nginx reverse proxy for docker containers and create docker network `bridge` or `overlay` mode.

## Usage

```bash
$ nginx-proxy-bridge.sh
```

This scipts create `docker-proxy` container and docker network `bridge` mode.


```bash
$ nginx-proxy-bridge-overlay.sh
```

This scipt will create `docker-proxy` container and docker networks `bridge` and `overlay` mode.

Now you can connect your stack in compose file to docker-proxy-overlay network:

```docker-compose
networks:
  docker-proxy-overlay:
    external:
      name: docker-proxy-overlay
```

For services:

```docker-compose
networks:
      - docker-proxy-overlay
```
	

## For check

```bash
$ sudo docker network ls
```

You will see networks `bridge` and `docker-proxy-overlay` in networks list.

```bash
$ sudo docker ps
```

You will see `docker-proxy` container.

