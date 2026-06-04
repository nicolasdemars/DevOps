FROM httpd:2.4-alpine

RUN apk add --no-cache gettext

ENV FRONT_HOST=front
ENV SIMPLEAPI_HOST=app

COPY httpd.conf /usr/local/apache2/conf/httpd.conf.template

CMD ["sh", "-c", "envsubst '$SIMPLEAPI_HOST $FRONT_HOST' < /usr/local/apache2/conf/httpd.conf.template > /usr/local/apache2/conf/httpd.conf && httpd-foreground"]
