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

```
4. edit /etc/nginx/nginx.conf
```conf


```
