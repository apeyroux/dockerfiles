from         j4pe/saucy
maintainer   j4pe

RUN dpkg-divert --local --rename --add /sbin/initctl
RUN ln -s /bin/true /sbin/initctl

RUN echo "deb http://archive.ubuntu.com/ubuntu saucy main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get upgrade -y 
RUN apt-get install software-properties-common python-software-properties -y 
RUN add-apt-repository ppa:tuxpoldo/btsync -y
RUN apt-get update
RUN export DEBIAN_FRONTEND=noninteractive; apt-get install btsync -y  --force-yes
RUN rm -f /etc/btsync/debconf-default.conf
RUN mkdir -p /data/btsync
RUN mkdir -p /data/.btsync
ADD btsync.conf /etc/btsync/btsync.conf
RUN restart btsync

EXPOSE 3369/udp
EXPOSE 8888

CMD ["/usr/lib/btsync/btsync-daemon", "--nodaemon", "--config", "/etc/btsync/btsync.conf"]
