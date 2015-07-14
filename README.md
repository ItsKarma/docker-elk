# ItsKarma/docker-elk

### Usage
This stack is designed and instructions are provided for AWS EC2 and requires some EBS volumes to be mounted to persist data. These instructions can be translated for use on another system, but will not be supported at this time.

Attach EBS volumes via aws console or cli
```
attach EBS volume to: /dev/sde - 40G
attach EBS volume to: /dev/sdl - 1G
attach EBS volume to: /dev/sdk - 1G
```

Create 1 partition consuming the entire disk for each volume mounted
```
fdisk /dev/sde
mkfs -t ext4 /dev/xvde1
fdisk /dev/sdl
mkfs -t ext4 /dev/xvdl1
fdisk /dev/sdk
mkfs -t ext4 /dev/xvdk1
```

Create the directories to mount
```
mkdir /data{elasticsearch,logstash,kibana}
mount /dev/xvde1 /data/elasticsearch
mount /dev/xvdl1 /data/logstash
mount /dev/xvdk1 /data/kibana
```

Create the data directory for elasticsearch
```
mkdir /data/elasticsearch/data
```

Install docker-compose via pip
```
pip install --upgrade pip
pip install -U docker-compose
```

Clone the repo and run
```
git clone https://github.com/ItsKarma/docker-elk.git ~/elk
cd ~/elk
docker-compose up
```
