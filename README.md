# nextcloud-docker-basic
Projeto Nextcloud com Docker e config NGINX proxy

## Installing certbot (Let's Encrypt certificate)

```sh
## Install
sudo apt install certbot

## Generating a new certificate (must have a valid host and config to certbot check):
## sudo certbot certonly --webroot -w /var/www/html -d your-host.com

## IF YOU WANT to copy the certificates to another dir:
## sudo cp /etc/letsencrypt/archive/your-host.com/{cert1.pem,chain1.pem,fullchain1.pem,privkey1.pem} ./new/path/to/certs/

## To renew the certificates
# /usr/bin/certbot renew

## To renew the certificates automatically via crontab
## Run
crontab -e
## And add above line
0 6 * * * /usr/bin/certbot renew

```


## Enabling nginx proxy 

```sh
sudo ln -s /path/to/project/nginx-proxy/nginx-proxy.conf /etc/nginx/sites-enabled/

sudo nginx -t && sudo nginx -s reload
```
