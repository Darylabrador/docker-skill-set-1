# SKILL SET 1

## More details

```
# All services are containerized except Apache.
# We have the Apache2 service on the front end linux server, which hands over to nginx which is in the Docker.
```

## Activities 

Here is a skill set 1 dedicated to practice docker :

- Install and configure a Linux server in LAMP mode.
- Install and configure a Firewall under Debian.
- Install and configure an SSH server.
- Install and configure an OPENVPN server.
- Install and configure a Proxy server.
- Install and configure a LAMP with an Nginx service in reverse proxy.
- Install and configure the Let's Encrypt service.

## Installation

```
git clone https://github.com/Darylabrador/docker-skill-set-1
cd docker-skill-set-1

# Pour OPENVPN : suivre la documentation avant de faire la commande suivante
https://github.com/kylemanna/docker-openvpn/blob/master/docs/docker-compose.md

docker compose up -d
```