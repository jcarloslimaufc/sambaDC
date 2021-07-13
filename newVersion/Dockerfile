FROM ubuntu:focal
#MAINTAINER Fmstrat <fmstrat@NOSPAM.NO>

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get upgrade -y

# Install all apps
# The third line is for multi-site config (ping is for testing later)
RUN apt-get install -y pkg-config
RUN apt install python3
#RUN apt-get install -y attr acl samba smbclient ldap-utils winbind libnss-winbind libpam-winbind krb5-user krb5-kdc supervisor
#RUN apt-get install -y openvpn inetutils-ping
RUN sudo apt-get install -y attr acl attr autoconf bind9utils bison build-essential \
  debhelper dnsutils docbook-xml docbook-xsl flex gdb libjansson-dev krb5-user \
  libacl1-dev libaio-dev libarchive-dev libattr1-dev libblkid-dev libbsd-dev \
  libcap-dev libcups2-dev libgnutls28-dev libgpgme-dev libjson-perl \
  libldap2-dev libncurses5-dev libpam0g-dev libparse-yapp-perl \
  libpopt-dev libreadline-dev nettle-dev perl perl-modules pkg-config \
  python-all-dev python-crypto python-dbg python-dev python-dnspython \
  python3-dnspython python-gpgme python3-gpgme python-markdown python3-markdown \
  python3-dev xsltproc zlib1g-dev liblmdb-dev lmdb-utils


# Set up script and run
ADD init.sh /init.sh
ADD bootstrap.sh /bootstrap.sh
RUN chmod 777 /bootstrap.sh
CMD /init.sh setup
