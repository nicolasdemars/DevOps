FROM httpd:2.4-alpine

RUN apk add --no-cache gettext

ENV FRONT_HOST=front
ENV BACKEND_BLUE_HOST=backend-blue
ENV BACKEND_GREEN_HOST=backend-green

COPY httpd.conf /usr/local/apache2/conf/httpd.conf.template

CMD ["sh", "-c", "envsubst '$FRONT_HOST $BACKEND_BLUE_HOST $BACKEND_GREEN_HOST' < /usr/local/apache2/conf/httpd.conf.template > /usr/local/apache2/conf/httpd.conf && httpd-foreground"]
