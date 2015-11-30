1.打开image的命令行

docker run -i -t ubuntu /bin/bash


2. Dockerfile范本格式

FROM docker/whalesay:latest
RUN apt-get -y update && apt-get install -y fortunes
CMD /usr/games/fortune -a | cowsay