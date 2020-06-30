FROM prestashop/prestashop

# Use development php.ini
RUN cp "$PHP_INI_DIR/php.ini-development" "$PHP_INI_DIR/php.ini"

# XDebug extension
RUN pecl install xdebug \
    && docker-php-ext-enable xdebug

# Enable XDebug
RUN echo '[XDebug] \n\
xdebug.remote_enable=1 \n\
xdebug.remote_connect_back=1' >> /usr/local/etc/php/php.ini
