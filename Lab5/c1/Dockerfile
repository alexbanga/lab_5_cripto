FROM ubuntu:16.10

# 1. Cambiamos los repositorios a old-releases porque la version 16.10 ya no tiene soporte oficial
RUN sed -i -re 's/([a-z]{2}\.)?archive.ubuntu.com|security.ubuntu.com/old-releases.ubuntu.com/g' /etc/apt/sources.list

# 2. Actualizamos e instalamos el cliente SSH y herramientas de red
RUN apt-get update && apt-get install -y \
    openssh-client \
    iproute2 \
    tcpdump \
    iputils-ping \
    && rm -rf /var/lib/apt/lists/*

# 3. Mantenemos el contenedor encendido
CMD ["tail", "-f", "/dev/null"]

