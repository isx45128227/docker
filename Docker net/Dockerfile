# Dockerfile
# Docker net amb eines bàsiques

FROM fedora:24
MAINTAINER @isx45128227 "Roger Ferran @edt Curs 2017-2018"
RUN dnf -y update vi
RUN dnf -y install vim iputils iproute procps mlocate \
	man-db nmap tree sendmail tftp tftp-server vsftpd \
	httpd telnet telnet-server openssh openssh-server \
	openssh-clients 
RUN echo "Benvingut a host base"
