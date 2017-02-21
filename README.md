# Docker ELK Stack
- Credit to [deviantony/docker-elk](https://github.com/deviantony/docker-elk) for a great starting point.

## Setup

1. Install [Docker](http://docker.io).
2. Install [Docker-compose](http://docs.docker.com/compose/install/) **version >= 1.6**.
3. Clone this repository
4. `sudo sysctl -w vm.max_map_count=262144`

## Usage

Start the ELK stack using *docker-compose*:

```bash
$ docker-compose up -d
```

Now that the stack is running, you'll want to inject logs in it. Try running `rabbitmq/send_message.py` which publishes the message to RabbitMQ. Logstash then receives the message and drops it into Elasticsearch, where it can be viewed with Kibana.

You can access Kibana UI by hitting [http://localhost:5601](http://localhost:5601) with a web browser.

By default, the stack exposes the following ports:
- 5000: Logstash TCP input.
- 9200: Elasticsearch HTTP
- 9300: Elasticsearch TCP transport
- 5601: Kibana
- 5672: RabbitMQ