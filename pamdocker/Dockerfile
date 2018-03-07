# Dockerfile
# Docker net amb eines PAM 
FROM fedora:24
MAINTAINER @isx45128227 "PAM Roger Ferran @edt Curs 2017-2018"
RUN dnf -y update vi
RUN dnf -y install vim iputils iproute procps mlocate \
	tree nmap nss-pam-ldapd
	
RUN mkdir /opt/docker

RUN rm -rf /etc/nscd.conf
RUN rm -rf /etc/nslcd.conf
RUN rm -rf /etc/nsswitch.conf 

COPY pam/nscd.conf /etc/
COPY pam/nslcd.conf /etc/
COPY pam/nsswitch.conf /etc/

COPY pam/startup.sh /opt/docker/
RUN chmod +x /opt/docker/startup.sh
WORKDIR /opt/docker/

CMD ["/bin/bash"]
# Haurem d'iniciar el servei pam --> ./opt/docker/startup.sh
