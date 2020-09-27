FROM debian:latest

RUN apt-get update && apt-get -y install git python && git clone https://github.com/sqlmapproject/sqlmap.git 

COPY . /sqlmap
WORKDIR /sqlmap

ENTRYPOINT ["python", "sqlmap.py"]