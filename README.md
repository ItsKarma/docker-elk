# ItsKarma/docker-elk

### Usage
This stack is currently designed for AWS and requires some volumes to be mounted to persist data.
> [https://docs.docker.com/userguide/dockervolumes/](https://docs.docker.com/userguide/dockervolumes/)

```
mount EFS volume to: /data/elasticsearch
mount 1GiB volume to: /data/logstash
mount 1GiB volume to: /data/kibana
git clone https://github.com/ItsKarma/docker-elk.git ~/elk
cd ~/elk
docker-compose up
```
