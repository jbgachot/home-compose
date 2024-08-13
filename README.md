<div align="center">
  <a href="#">
    <img src=".img/ha-logo.png" alt="Logo" width="200" height="200">
  </a>

  <h3 align="center">Home Assistant with Compose</h3>

  <p align="center">
    Personal setup for home assistant
  </p>
</div>

## Prerequisites

    - docker

## Start

- Copy `.env.example` into `.env`

- Edit `.env` and create new secrets, make sure `ZIGBEE_USB_PATH` match your usb key:

```bash
ls /dev/serial/by-id/
```

- Remove the file `postgres/data/.gitkeep`

_Postgres won't start if his data folder is not empty_

- Edit `caddy/Caddyfile` and make it match your dns setup

```bash
# If you don't have dns pointing to your server, add this entries in your laptop /etc/hosts
# 127.0.0.1 if you are running locally or 192.168.xx.xx if it's a remote server
127.0.0.1 server.home
127.0.0.1 influxdb.home
127.0.0.1 zigbee2mqtt.home
```

- Start the stack

`docker compose up -d`

- Watch the logs

`docker compose logs -f`

- Access your url : [http://server.home](http://server.home)
