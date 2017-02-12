FROM nginx:stable-alpine

COPY config/nginx.conf /etc/nginx/nginx.conf
COPY config/default.conf /etc/nginx/conf.d/default.conf
COPY website /usr/share/nginx/html/
