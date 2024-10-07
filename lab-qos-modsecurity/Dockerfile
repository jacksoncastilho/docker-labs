# Use the official Apache HTTP server image as the base
FROM httpd:latest

# Keep the image updated with the latest package versions
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Install additional required packages
RUN apt-get update && \
    apt-get install -y \
    vim \
    curl \
    wget \
    net-tools \
    tcpdump \
    htop \
    netcat-traditional \
    iputils-ping \
    hping3 \
    telnet \
    tmux && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Install ModSecurity2 module for Apache
RUN apt-get update && \
    apt-get install -y apache2 libapache2-mod-security2 && \
    cp /usr/lib/apache2/modules/mod_security2.so /usr/local/apache2/modules/ && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Create necessary directories for ModSecurity
RUN mkdir -p /opt/modsecurity/bin /opt/modsecurity/var/audit \
    /opt/modsecurity/var/data /opt/modsecurity/var/log \
    /opt/modsecurity/var/tmp /opt/modsecurity/var/upload

# Set ownership for directories based on least privilege principle
RUN chown root:www-data /opt/modsecurity /opt/modsecurity/bin /opt/modsecurity/var && \
    chown www-data:root /opt/modsecurity/var/audit /opt/modsecurity/var/data /opt/modsecurity/var/upload && \
    chown root:root /opt/modsecurity/var/log && \
    chown www-data:www-data /opt/modsecurity/var/tmp

# Apply restrictive permissions to directories
RUN chmod 750 /opt/modsecurity /opt/modsecurity/bin /opt/modsecurity/var && \
    chmod 700 /opt/modsecurity/var/audit /opt/modsecurity/var/data /opt/modsecurity/var/log /opt/modsecurity/var/upload && \
    chmod 750 /opt/modsecurity/var/tmp
