# Reporting Showcase for DDQ + ELK

## Description

This is a demonstration of how [Drunken Data Quality (DDQ)](https://github.com/FRosner/drunken-data-quality) can work together with Elasticsearch, Logstash and Kibana (ELK) to monitor data quality.

It provides a composition of all required services: ELK, DDQ, a Spark streaming job, and a data generator.

## Prerequisites

This demo was developed using docker and docker-compose. You should have a docker host running and configured. It will probably also work with different versions, but in case something is wrong you might try these ones:

### Docker

```
Client:
 Version:      1.10.2
 API version:  1.22
 Go version:   go1.5.3
 Git commit:   c3959b1
 Built:        Mon Feb 22 22:37:33 2016
 OS/Arch:      darwin/amd64

Server:
 Version:      1.11.0
 API version:  1.23
 Go version:   go1.5.4
 Git commit:   4dc5990
 Built:        Wed Apr 13 19:36:04 2016
 OS/Arch:      linux/amd64
```

### Docker Compose

```
docker-compose version 1.6.2, build 4d72027
docker-py version: 1.7.2
CPython version: 2.7.11
OpenSSL version: OpenSSL 1.0.2f  28 Jan 2016
```

## Usage

1. Check out the repository (or download the zip)
   ```
   git clone git@github.com:FRosner/ddq-demo-elk.git && \
   cd ddq-demo-elk
   ```
2. Launch docker-compose (-d for daemon mode)
   ```
   docker-compose up -d
   ```
3. Find the Kibana UI at `http://<DOCKER_HOST_IP>:5601`
4. Find the Spark UI at `http://<DOCKER_HOST_IP>:4040`

You can find your docker host IP address by looking at `echo $DOCKER_HOST | cut -f2 -d: | cut -f3 -d/`.

## Disclaimer

All the services run on a single host and contain static port mappings. They are only intended for demonstration. Do not expect high performance or scalability out of this setup. You should use a proper cluster manager + service discovery if you want to run this in production.

## License

Copyright 2016 Frank Rosner

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this work except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
