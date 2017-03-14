FROM php:5-fpm
# Install modules
RUN apt-get update && apt-get install -y \
	libpng12-dev \
	libldap2-dev \
        libc-client2007e-dev \
	libkrb5-dev \
#	&& ln -s /usr/lib/x86_64-linux-gnu/libldap.so /usr/lib/libldap.so \
#	&& ln -s /usr/lib/x86_64-linux-gnu /usr/kerberos/lib \
	&& docker-php-ext-install mysqli \
	&& docker-php-ext-install gd \
	&& docker-php-ext-configure ldap --with-libdir=/lib/x86_64-linux-gnu \
	&& docker-php-ext-install ldap \
	&& docker-php-ext-configure  imap --with-kerberos=/usr/lib/x86_64-linux-gnu --with-imap-ssl  \
	&& docker-php-ext-install imap  


CMD ["php-fpm"]
