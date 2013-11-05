
docker run -d -p 8888 -p 3369/udp -v /home/ja/btsync:/data/btsync j4/btsync

docker run -d -p 8888:8888 -p 3369/udp -v /home/ja:/data/btsync j4/btsync
