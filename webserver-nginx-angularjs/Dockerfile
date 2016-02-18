FROM ubuntu:trusty

MAINTAINER Guilherme G. Amaral <ggamaral@gmail.com>

# Install dependencies
RUN apt-get update && apt-get install -y wget \
    dialog \
    net-tools \
    nginx && \
    rm -rf /var/lib/apr/lists/* && \
    echo "daemon off;" >> /etc/nginx/nginx.conf

# Define mountable directories.
VOLUME ["/etc/nginx/sites-enabled", "/etc/nginx/certs", "/etc/nginx/conf.d", "/var/log/nginx", "/var/www/html"]

# Define working directory.
WORKDIR /etc/nginx

# Expose HTTP and HTTPS
EXPOSE 80 443

# Execute process
CMD ["/etc/init.d/nginx", "start"]
