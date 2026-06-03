FROM httpd:2.4-alpine

RUN apk add --no-cache gettext

COPY index.html /usr/local/apache2/htdocs/index.html
COPY httpd.conf /usr/local/apache2/conf/httpd.conf.template

CMD sh -c "envsubst '\$SIMPLEAPI_HOST' < /usr/local/apache2/conf/httpd.conf.template > /usr/local/apache2/conf/httpd.conf && httpd-foreground"