FROM debian:jessie

MAINTAINER Mohamed Omar Kebaili<kebaili.med.omar@gmail.com>

RUN apt-get update && apt-get install -y wget

RUN wget http://repo.mosquitto.org/debian/mosquitto-repo.gpg.key && apt-key add mosquitto-repo.gpg.key

RUN wget http://repo.mosquitto.org/debian/mosquitto-jessie.list -P /etc/apt/sources.list.d/

RUN apt-get update && apt-cache search mosquitto && apt-get install -y mosquitto

ADD mosquitto.conf /etc/mosquitto/mosquitto.conf

ADD docker-entrypoint.sh /docker-entrypoint.sh

RUN chmod +x /docker-entrypoint.sh

ENTRYPOINT ["/docker-entrypoint.sh"]

CMD ["mosquitto", "-c", "/etc/mosquitto/mosquitto.conf"]
