FROM prestashop/base:7.2-apache

ENV PS_VERSION 1.6.1.24

# Get PrestaShop
# ADD https://www.prestashop.com/download/old/prestashop_1.6.1.24.zip /tmp/prestashop.zip
COPY prestashop_1.6.1.24.zip /tmp/prestashop.zip

# Extract
RUN mkdir -p /tmp/data-ps \
	&& unzip -q /tmp/prestashop.zip -d /tmp/data-ps/ \
	&& bash /tmp/ps-extractor.sh /tmp/data-ps \
	&& rm /tmp/prestashop.zip

RUN apt-get install -y libmcrypt-dev && \
    pecl install mcrypt-1.0.1 && \
    docker-php-ext-enable mcrypt

