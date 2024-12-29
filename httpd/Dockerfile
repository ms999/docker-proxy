FROM httpd:2.4

# Copy configuration files
COPY httpd.conf /usr/local/apache2/conf/httpd.conf
COPY mirror.vhost.conf /usr/local/apache2/conf/extra/mirror.vhost.conf


# Create the apache user and group if they don't exist
RUN groupadd -g 1000 apache && useradd -u 1000 -g apache -m apache

# Run the commands as root to create directories and set permissions
RUN mkdir -p /var/cache/apache2/docker && chown -R apache:apache /var/cache/apache2/docker

RUN mkdir -p /usr/local/apache2/logs && chown -R apache:apache /usr/local/apache2/logs


# Set the user for Apache to run as
USER apache


