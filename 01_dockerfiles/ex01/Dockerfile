FROM debian
 
LABEL maintainer="avolgin"
 
RUN apt-get update -y && apt-get upgrade -y

COPY teamspeak3server.service /etc/systemd/system

RUN apt-get install wget bzip2 -y --allow-unauthenticated && apt-get clean
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
RUN apt-get autoremove -y
RUN adduser --disabled-password --gecos "" teamspeak
RUN mkdir /opt/teamspeak
RUN chown teamspeak:teamspeak /opt/teamspeak
RUN chmod 0770 /opt/teamspeak
RUN	apt-get update -y \
	&& apt-get install systemd -y \
	&& systemctl enable teamspeak3server.service \
	&& apt-get install sudo -y
RUN	sudo -iu teamspeak
RUN wget http://dl.4players.de/ts/releases/3.0.13.8/teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2
RUN tar xfv teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2
RUN mv teamspeak3-server_linux_amd64/* /opt/teamspeak
RUN rm -rf teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2 teamspeak3-server_linux_amd64
RUN /opt/teamspeak/ts3server_startscript.sh start
	
ENV DEBIAN_FRONTEND=noninteractive

# it is default! change if needed
ENV TS3SERVER_LICENSEPATH /var/ts3server 

ENV TS_VERSION=LATEST \
	TS3SERVER_LICENSE=accept \
	TS_USER=teamspeak \
	TS_HOME=/teamspeak

#set locale
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en

#open ports
EXPOSE 9987/udp 10011 30033 41144


# to build image in current directory
# docker build -t <image_name> .
# to start teamspeak /opt/teamspeak/ts3server_startscript.sh start or
# /opt/teamspeak/ts3server_startscript.sh restart
