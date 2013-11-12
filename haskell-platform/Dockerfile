from         j4pe/saucy
maintainer   j4pe

RUN dpkg-divert --local --rename --add /sbin/initctl
RUN ln -s /bin/true /sbin/initctl

RUN echo "deb http://archive.ubuntu.com/ubuntu saucy main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get upgrade -y 
RUN export DEBIAN_FRONTEND=noninteractive; apt-get install haskell-platform vim -y
RUN useradd ja -d /home/ja -s /bin/bash
