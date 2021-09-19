# nginx-proxy
A walkthrough on setting up an nginx proxy with tor

1. install nginx and tor docker docker-compose
2. create a self-signed certificate if needed
```bash
mkdir /etc/nginx/certs
cd /etc/nginx/certs
openssl req -x509 -newkey rsa:4096 -keyout selfsigned.key -out selfsigned.crt -days 365 -nodes
```
3. create a tor hidden service if needed in /etc/tor/torrc
```torrc
# simply add two lines simular to these
# one with the name of the service
HiddenServiceDir /var/lib/tor/nextcloud/
# the second with the port mapping:  exernal_port internal_ip:internal_port
HiddenServicePort 80 127.0.0.1:80
```
4. restart tor and get the hostname
```bash
systemctl restart tor
cat /var/lib/tor/nextcloud/hostname
```
6. edit /etc/nginx/nginx.conf (look at the example for help)
7. restart nginx
```
systemctl restart nginx
```
