FROM ubuntu:22.04

RUN apt-get update && \
    apt-get install git python3 apache2 -y

COPY webclient.conf /etc/apache2/sites-available/webclient.conf

RUN a2ensite webclient.conf
RUN a2enmod rewrite

RUN git clone https://github.com/meganz/webclient.git /var/www/html

RUN chgrp -R www-data /var/www/html
RUN chown -R www-data /var/www/html

CMD ["apache2-foreground"]
