# Web server
FROM nginx:1.21.1
MAINTAINER Alexander <alex3030@yandex.ru>
RUN mv /etc/nginx/conf.d/default.conf /etc/nginx/conf.d/default.conf_
RUN touch /etc/nginx/conf.d/web.conf
RUN echo "server {" >> /etc/nginx/conf.d/web.conf
RUN echo "listen 8000;" >> /etc/nginx/conf.d/web.conf
RUN echo "server_name  localhost;" >> /etc/nginx/conf.d/web.conf
RUN echo "location / {" >> /etc/nginx/conf.d/web.conf
RUN echo "root   /app;" >> /etc/nginx/conf.d/web.conf
RUN echo "index  index.html index.htm;" >> /etc/nginx/conf.d/web.conf
RUN echo "}" >> /etc/nginx/conf.d/web.conf
RUN echo "}" >> /etc/nginx/conf.d/web.conf
RUN mkdir -p /app
RUN usermod -u 1001 nginx &&\
RUN chown nginx /app
