FROM php:8.0-apache-bullseye

RUN apt-get update && \
    apt-get install git python3 -y

COPY webclient.conf /etc/apache2/sites-available/webclient.conf

RUN a2ensite webclient.conf
RUN a2enmod rewrite

RUN git clone https://github.com/meganz/webclient.git /var/www/html

RUN chgrp -R www-data /var/www/html

CMD ["apache2-foreground"]
