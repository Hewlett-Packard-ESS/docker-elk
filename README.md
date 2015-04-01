![Elk](/elk.jpg?raw=true "Elk")
The purpose of this project is to show how easily you can build a clustered ELK stack using a bunch of other docker containers that we've put together.

The benefit here is because all of these containers are based from the same set of base images, the actual download size is significantly less than the virtual size.

## Configuration
By default, the docker-compose file creates 4 `elasticsearch` nodes, 2 `logstash` nodes, and 2 `kibana` nodes.  These are load balanced using `haproxy`.

We also have a `logstash forwarder`, which is configured to read everything in /var/log, and send this via TCP to `loadstash`, just as an example of how to get data in.

## To run it
Simply type `docker-compose up -d`, it takes around 10 seconds on my laptop for everything to come up, cluster, and start talking to eachother, key urls once it's done are:

  - http://127.0.0.1:8080       # HA Proxy
  - http://127.0.0.1:9200		# Elasticsearch
  - http://127.0.0.1:5601		# Kibana

## Composing Containers
The configuration is made up of the following docker images:
  - [hpess/haproxy](https://github.com/Hewlett-Packard-ESS/docker-haproxy)
  - [hpess/elasticsearch](https://github.com/Hewlett-Packard-ESS/docker-elasticsearch)
  - [hpess/kibana](https://github.com/Hewlett-Packard-ESS/docker-kibana)
  - [hpess/logstash](https://github.com/Hewlett-Packard-ESS/docker-logstash)
  - [hpess/logstash-forwarder](https://github.com/Hewlett-Packard-ESS/docker-logstash-forwarder)

## License
Each of the containers are licensed under the [MIT](/LICENSE-MIT) license.

Each of the components in those containers have their own licences in place, visit the links above to see them.
