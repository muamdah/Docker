FROM debian:stretch

RUN apt-get update && \
	 apt-get install -y wget tar && \
	 apt-get install -y bzip2 && \
	 wget http://dl.4players.de/ts/releases/3.0.12.4/teamspeak3-server_linux_amd64-3.0.12.4.tar.bz2 && \
	 bzip2 -d teamspeak3-server_linux_amd64-3.0.12.4.tar.bz2 && \
	 tar -xvf teamspeak3-server_linux_amd64-3.0.12.4.tar

EXPOSE 9987/udp
EXPOSE 10011
EXPOSE 30033

CMD ./teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh start

#Creation de l'image:
#docker build -t debian_ts .

#Demarrage de debian_ts avec les configuration correspondant :
#docker run -ti --name=serverTS -p 9987:9987/udp -p 10011:10011 -p 30033:30033 -d debian_ts
