from j4pe/saucy
maintainer j4pe


RUN echo "deb http://archive.ubuntu.com/ubuntu saucy main universe" > /etc/apt/sources.list

run apt-get update
run apt-get install -y -q nginx
run rm /etc/nginx/sites-enabled/default
run echo "daemon off;" >> /etc/nginx/nginx.conf
add j4.pe /etc/nginx/sites-enabled/j4.pe
expose 80
cmd ["nginx"]
