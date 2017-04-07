# docker-plex

These compose files imply a linux host, but could be updated to run on other hosts.

Have fun plexing.

## Update the following variables

* HOST_IP
* HOST_PORT
* PIA_PASSWORD
* PIA_USERNAME
* Update shared-config.env

## Letsencrypt Optional

git clone https://github.com/letsencrypt/letsencrypt ~/nginx/letsencrypt

## Nginx Optional

If you would like domain names for each service you can configure nginx. aka plexrequests.DOMAIN.com

make sure to update:

* nginx/conf/default.conf
* nginx/conf/example.conf

### Auto rewnew

To auto renew can you cron the following command

docker exec nginx /letsencrypt/letsencrypt-auto \
    renew -n \
    -m EMAIL@EMAIL.COM \
    -a webroot --webroot-path=/usr/share/nginx/html \
    --agree-tos