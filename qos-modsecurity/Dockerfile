# Use a imagem base oficial do Apache httpd
FROM httpd:latest

# Mantenha a imagem atualizada
RUN apt-get update && apt-get upgrade -y

# Instale pacotes adicionais
RUN apt-get install -y vim \
curl \
wget \
net-tools \
tcpdump \
htop \
netcat-traditional \
iputils-ping \
hping3 \
telnet \
tmux

# Intala o modulo mod-security2
RUN apt update && apt install apache2 libapache2-mod-security2 -y

RUN cp /usr/lib/apache2/modules/mod_security2.so /usr/local/apache2/modules/

RUN mkdir -p /opt/modsecurity/bin
RUN mkdir -p /opt/modsecurity/var/audit
RUN mkdir /opt/modsecurity/var/data
RUN mkdir /opt/modsecurity/var/log
RUN mkdir /opt/modsecurity/var/tmp
RUN mkdir /opt/modsecurity/var/upload

RUN chown root:www-data /opt/modsecurity
RUN chown root:www-data /opt/modsecurity/bin
RUN chown root:www-data /opt/modsecurity/var
RUN chown www-data:root /opt/modsecurity/var/audit
RUN chown www-data:root /opt/modsecurity/var/data
RUN chown root:root /opt/modsecurity/var/log
RUN chown www-data:www-data /opt/modsecurity/var/tmp
RUN chown www-data:root /opt/modsecurity/var/upload

RUN chmod 750 /opt/modsecurity
RUN chmod 750 /opt/modsecurity/bin
RUN chmod 750 /opt/modsecurity/var
RUN chmod 700 /opt/modsecurity/var/audit
RUN chmod 700 /opt/modsecurity/var/data
RUN chmod 700 /opt/modsecurity/var/log
RUN chmod 750 /opt/modsecurity/var/tmp
RUN chmod 700 /opt/modsecurity/var/upload
