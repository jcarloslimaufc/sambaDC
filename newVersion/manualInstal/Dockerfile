FROM ubuntu:focal
RUN apt-get update && apt-get upgrade -y
# Install samba dependencies https://wiki.samba.org/index.php/Package_Dependencies_Required_to_Build_Samba
ADD bootStrap.sh /bootStrap.sh
RUN chmod 777 bootStrap.sh && ./bootStrap.sh
#RUN wget https://download.samba.org/pub/samba/stable/samba-4.14.5.tar.gz

#ADD já realiza o unzip do arquivo https://wiki.samba.org/index.php/Build_Samba_from_Source
ADD samba-4.14.5.tar.gz /

RUN cd /samba-4.14.5 && ./configure 
RUN cd /samba-4.14.5 && make -j 2
RUN cd /samba-4.14.5 && make install
RUN export PATH=/usr/local/samba/bin/:/usr/local/samba/sbin/:$PATH

ENTRYPOINT ["/bin/sh"]