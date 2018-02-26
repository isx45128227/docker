# Dockerfile
# Docker net amb eines LDAP funcionant
FROM fedora:24
MAINTAINER @isx45128227 "LDAP Roger Ferran @edt Curs 2017-2018"
RUN dnf -y update vi
RUN dnf -y install vim iputils iproute procps mlocate \
	xinetd openldap openldap-servers openldap-clients tree nmap
	
RUN echo "Benvingut a host base"
RUN mkdir /opt/docker && echo "opt creat"
RUN cp /usr/share/openldap-servers/DB_CONFIG.example /opt/docker/DB_CONFIG

COPY slapd/slapd-edt.org.conf /opt/docker
COPY slapd/organitzacio_edt.org-TOTAL.ldif /opt/docker
COPY slapd/startup.sh /opt/docker
RUN chmod +x /opt/docker/startup.sh
RUN /opt/docker/startup.sh
