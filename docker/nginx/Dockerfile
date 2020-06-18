FROM nginx:1.17-alpine

RUN mkdir -p /etc/nginx/sites-enabled
ADD config/nginx.conf /etc/nginx/nginx.conf
ADD config/vhost.conf /etc/nginx/sites-avaliable/vhost.conf
EXPOSE 80
CMD envsubst "$(env | sed -e 's/=.*//' -e 's/^/\$/g')" < \
          /etc/nginx/sites-avaliable/vhost.conf > /etc/nginx/sites-enabled/vhost.conf && \
         nginx -g "daemon off;"