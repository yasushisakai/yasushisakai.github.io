---
title: https server
layout: post
---

# how to set a https server (mit media lab)


## 1. create place to save the certificates

``` sudo mkdir -p /etc/httpd/conf/ssl.key ```

## 2. generate a key

``` openssl genrsa -out /etc/httpd/conf/ssl.key/cityio.media.mit.edu.key 2048 ```

## 3. generate request

``` sudo openssl req -new -key /etc/httpd/conf/ssl.key/cityio.media.mit.edu.key -out /etc/httpd/conf/cityio.media-2017.req ```

## 4. send the request file to mitcert@mit.edu

signed certificates will be sent back to you in a few hours!

## 5. download signed certificate and concatenate 

the default file did not work.
download X509 cert only and intermediates/root

``` $ cat cert.cer intern.cer > cerfile.cer ```

open and **add a new line** between cert and intern

``` $ vim /etc/nginx/sites-available/default ```

## 6. configure nginx config file

crucial part of the file should resemble like the following

```
# HTTP

server {
        listen 80;
        listen [::]:80 default_server ipv6only=on;
        # redirect everything to https
        return 301 https://$host$request_uri;
}

# HTTPS

server {
        listen 443;
        server_name cityio.media.mit.edu;

        ssl on;
        # ssl_certificate /etc/httpd/conf/ssl.crt/cityio_media_mit_edu_reversed.cer;
        ssl_certificate /etc/httpd/conf/ssl.crt/cityio_media_mit_edu_renewed.cer;
        ssl_certificate_key /etc/httpd/conf/ssl.key/cityio.media.mit.edu.key;

        # pass requests for / to localhost:8080
        location / {
                # proxy_set_header X-Real-IP $remote-addr;
                # proxy_set_header X-Forwareded-For $proxy_add_x_forwareded_for;
                # proxy_set_header X-NginX-Proxy true;
                # proxy_ssl_session_reuse off;
                proxy_http_version 1.1;
                proxy_pass http://0.0.0.0:8080/;
                proxy_set_header Upgrade $http_upgrade;
                proxy_set_header Connection 'upgrade';
                proxy_set_header Host $host;
                proxy_cache_bypass $http_upgrade;
                proxy_redirect off;
        }

}

```

## 7. test nginx 

``` $ sudo nginx -t ```

if everything looks good

``` $ sudo systemctl nginx start ```

## 8. observe the url

and your done.
