# server

## basic nginx setup

```
domain=example.com

sudo -i

mkdir -p /var/log/nginx/$domain

mkdir -p /var/www/$domain

echo $domain > /var/www/$domain/index.html

touch /etc/nginx/sites-available/$domain.conf

wget https://raw.githubusercontent.com/gue-ni/raspberrypi-server/main/example.com.conf -O /etc/nginx/sites-available/$domain.conf

sed -i "s/example.com/$domain/g" /etc/nginx/sites-available/$domain.conf

ln -s /etc/nginx/sites-available/$domain.conf /etc/nginx/sites-enabled/

nginx -t && nginx -s reload

certbot --nginx -d $domain -d www.$domain
```
