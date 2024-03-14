FROM debian

RUN apt-get update && apt-get install -y apache2
ENV APACHE_LOCK_DIR="/var/lock"
ENV APACHE_PID_FILE="/var/run/apache2.pid"
ENV APACHE_RUN_USER="wwww-data"
ENV APACHE_RUN_GROUP="wwww-data"
ENV APACHE_LOG_DIR="/var/log/apache2"

#COPY index.html /var/www/html/
ADD index.html /var/www/html/

WORKDIR /var/www/html

LABEL description="Webserver"

USER root

VOLUME /var/www/html
EXPOSE 80

ENTRYPOINT ["/usr/sbin/apachectl"]
CMD ["-D", "FOREGROUND"]