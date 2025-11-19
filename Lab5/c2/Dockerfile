FROM ubuntu:18.10

# Arreglo de repositorios para versión EOL (End Of Life)
RUN sed -i -re 's/([a-z]{2}\.)?archive.ubuntu.com|security.ubuntu.com/old-releases.ubuntu.com/g' /etc/apt/sources.list

# Instalación de herramientas
RUN apt-get update && apt-get install -y \
    openssh-client \
    iproute2 \
    tcpdump \
    iputils-ping \
    && rm -rf /var/lib/apt/lists/*

CMD ["tail", "-f", "/dev/null"]
