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

RUN rm -rf /etc/openldap/slapd.d/* /var/lib/ldap/*
RUN cp /opt/docker/DB_CONFIG /var/lib/ldap
RUN slaptest -f /opt/docker/slapd-edt.org.conf
RUN slaptest -f /opt/docker/slapd-edt.org.conf -u
RUN slaptest -f /opt/docker/slapd-edt.org.conf -F /etc/openldap/slapd.d/
RUN slaptest -f /opt/docker/slapd-edt.org.conf -F /etc/openldap/slapd.d/ -u
RUN slapadd -v -F /etc/openldap/slapd.d/ -l /opt/docker/organitzacio_edt.org-TOTAL.ldif

RUN chown -R ldap.ldap /var/lib/ldap /etc/openldap/slapd.d/
RUN /opt/docker/startup.sh