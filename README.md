This example is piggybacking off of the Elastic stack in 5 minutes docker example 
in order to provide a sample python application with apm hooks into the Elastic stack

Please noteP: sometimes docker compose needs to be ran twice without deleting container and images
if experiencing memory issues on laptop

Just download, cd into directory, and then run "docker-compose up"

When done, go to http://localhost:5000 in browser to see sample web page via flask with Redis backend

Go to http://localhost:5601 and log into kibana to see apm data (and other sample data)

If APM dashboards are not present, consider logging into the APM container and manually running the APM dashboard command:

(to tunnel into APM container):
 docker exec -it pythonstackdocker_web_1 /bin/bash

(within bash):
./apm-server setup -E setup.kibana.host=kibana:5601





-------------------------------------
all info below is straight from official stack-docker
storing this simply for convenience - there is nothing official here - use at own peril


# stack-docker
This example Docker Compose configuration demonstrates many components of the
Elastic Stack, all running on a single machine under Docker.

## Prerequisites
- Docker and Compose. Windows and Mac users get Compose installed automatically
with Docker. Linux users can:
```
pip install docker-compose
```

- At least 4GiB of RAM for the containers. Windows and Mac users _must_
configure their Docker virtual machine to have more than the default 2 GiB of
RAM:

![Docker VM memory settings](screenshots/docker-vm-memory-settings.png)

## Starting the stack
Try `docker-compose up` to create a demonstration Elastic Stack with
Elasticsearch, Kibana, Logstash, Auditbeat, Metricbeat, Filebeat, Packetbeat,
and Heartbeat.

Point a browser at [`http://localhost:5601`](http://localhost:5601) to see the results.

Log in with `elastic` / `changeme`.
