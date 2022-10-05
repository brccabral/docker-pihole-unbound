FROM pihole/pihole:${PIHOLE_VERSION:-latest}
RUN apt update && apt install -y unbound nano

COPY external.conf /etc/lighttpd/ 
COPY pi-hole.conf /etc/unbound/unbound.conf.d/
COPY 99-edns.conf /etc/dnsmasq.d/
COPY dnsmasq.conf /etc/
RUN mkdir -p /etc/services.d/unbound
COPY run /etc/services.d/unbound/

ENTRYPOINT ./s6-init
