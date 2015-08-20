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

## Resume

Kibana UI is accessible at [http://localhost:5601](http://localhost:5601).

By default,  the following ports:

* 5000: Logstash TCP input.
* 9200: Elasticsearch HTTP (with Marvel plugin accessible via [http://localhost:9200/_plugin/marvel](http://localhost:9200/_plugin/marvel))
* 5601: Kibana 4 web interface

## Further configuration

* Kibana default configuration is stored in `kibana/config/kibana.yml`.
* logstash configuration is stored in `logstash/config/logstash.conf`.
* Elasticsearch container is using the shipped configuration and it is not exposed by default.
