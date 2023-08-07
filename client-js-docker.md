###### Dockerfile
````
FROM registry.kube.io/nginx/nginx:1.23.0
COPY ./nginx.conf /etc/nginx/conf.d/default.conf
COPY dist /usr/share/nginx/html
EXPOSE 80
````
###### nginx.conf
```
# Expires map
map $sent_http_content_type $expires {
    default                    off;
    text/html                  epoch;
    text/css                   max;
    application/json           max;
    application/javascript     max;
    ~image/                    max;
}

server {
  listen 80;
  location / {
      root /usr/share/nginx/html;
      index index.html index.htm;
      try_files $uri $uri/ /index.html =404;
    }
  expires $expires;
  gzip  on;
}
```
