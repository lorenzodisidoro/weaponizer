FROM python:alpine3.11

RUN apk add --update build-base libffi-dev libxml2-dev libxslt-dev git && git clone https://github.com/laramies/theHarvester.git

COPY . /theHarvester
WORKDIR /theHarvester

RUN pip3 install -r requirements.txt
RUN chmod +x *.py

ENTRYPOINT ["/theHarvester/theHarvester.py"]