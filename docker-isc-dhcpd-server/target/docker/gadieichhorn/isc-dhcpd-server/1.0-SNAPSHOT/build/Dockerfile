FROM debian
LABEL version=1.0-SNAPSHOT
EXPOSE 67/udp
COPY maven /
RUN apt update && apt install -y isc-dhcp-server
VOLUME ["/data"]
ENTRYPOINT ["dhcpd","-cf","/opt/data/dhcpd.conf","-if","/opt/data/dhcpd.leases","--no-pid","-4","-f","eth0"]
