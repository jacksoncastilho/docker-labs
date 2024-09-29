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
RUN apt update && apt install libapache2-mod-security2 -y

RUN cp /usr/lib/apache2/modules/mod_security2.so /usr/local/apache2/modules/
