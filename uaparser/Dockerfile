ARG BASE_CONTAINER=rockstat/band-base-py:3.7
FROM $BASE_CONTAINER

LABEL maintainer="Dmitry Rodin <madiedinro@gmail.com>"
LABEL band.service.version="0.4.0"
LABEL band.service.title="UserAgent parser"
LABEL band.service.def_position="4x2"

WORKDIR /usr/src/services

ENV HOST=0.0.0.0
ENV PORT=8080

#cachebust
ARG RELEASE=master
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

EXPOSE ${PORT}
COPY . .

CMD [ "python", "-m", "uaparser"]
