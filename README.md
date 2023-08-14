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

## Apache2 conf (sur le server)

```
sudo cp 000-default.conf /etc/apache2/sites-available/000-default.conf
sudo a2enmod proxy proxy_http proxy_balancer lbmethod_byrequests rewrite
sudo systemctl restart apache2
```