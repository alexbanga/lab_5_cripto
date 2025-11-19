FROM ubuntu:22.10

# Arreglo de repositorios (22.10 ya no tiene soporte oficial)
RUN sed -i -re 's/([a-z]{2}\.)?archive.ubuntu.com|security.ubuntu.com/old-releases.ubuntu.com/g' /etc/apt/sources.list

# Instalamos Cliente Y Servidor
RUN apt-get update && apt-get install -y \
    openssh-client \
    openssh-server \
    iproute2 \
    tcpdump \
    iputils-ping \
    nano \
    && rm -rf /var/lib/apt/lists/*

# Configuración necesaria para que corra el servidor SSH
RUN mkdir -p /var/run/sshd

# Creación del usuario 'prueba' con password 'prueba' (Requisito Rúbrica)
RUN useradd -m -s /bin/bash prueba && echo "prueba:prueba" | chpasswd

# Permitir autenticación por contraseña
RUN sed -i 's/#PasswordAuthentication yes/PasswordAuthentication yes/' /etc/ssh/sshd_config

EXPOSE 22

# Iniciamos el servicio SSH
CMD ["/usr/sbin/sshd", "-D"]
