FROM prestashop/prestashop:1.6

# Use development php.ini
RUN cp "$PHP_INI_DIR/php.ini-development" "$PHP_INI_DIR/php.ini"

# XDebug extension
RUN pecl install xdebug-2.5.5 \
    && docker-php-ext-enable xdebug

# Enable XDebug
RUN echo '[XDebug] \n\
xdebug.remote_enable=1 \n\
xdebug.remote_connect_back=1' >> /usr/local/etc/php/php.ini
