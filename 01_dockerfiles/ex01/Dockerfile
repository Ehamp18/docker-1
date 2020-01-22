FROM debian

ENV TS3SERVER_LICENSE=accept

WORKDIR /home/teamspeak

RUN apt-get update && apt-get upgrade -y && apt-get install -y wget bzip2 && \
wget https://files.teamspeak-services.com/releases/server/3.7.1/teamspeak3-server_linux_amd64-3.7.1.tar.bz2 && \
tar -xvf teamspeak3-server_linux_amd64-3.7.1.tar.bz2

EXPOSE 9987/udp 10011 30033

WORKDIR teamspeak3-server_linux_amd64

ENTRYPOINT sh ts3server_minimal_runscript.sh