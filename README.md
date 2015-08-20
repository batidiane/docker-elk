# docker-elk

Dockerized ELK Stack : Elastic Search + Logstash + Kibana

Based on the official images:

* [elasticsearch](https://registry.hub.docker.com/_/elasticsearch/)
* [logstash](https://registry.hub.docker.com/_/logstash/)
* [kibana](https://registry.hub.docker.com/_/kibana/)

# How to use

## Requirements

1. You need a working Docker environment, check [http://docker.io](http://docker.io) for more information.
2. We use Docker-Compose to orchestrate all containers, to install it check [Docker-compose](http://docs.docker.com/compose/install/).

## Installation

Just clone this repository to your docker machine.

## How to start

Start docker-elk using *docker-compose*:

```bash
$ docker-compose up
```

Start docker-elk in detached mode:

```bash
$ docker-compose up -d
```

## How to inject logs

Provided logstash configuration allows you to send content via tcp:

```bash
$ nc localhost 5000 < /path/to/logfile.log
```
