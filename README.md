# azkaban
default port: 8081

## requirement
- docker-compose: 17.09.0+

## How to run with docker-compose

- start azkaban 

```
    git clone https://github.com/haxqer/azkaban.git \
        && cd azkaban \
        && docker-compose up
```

- start azkaban & mysql daemon

```
    docker-compose up -d
```

## How to run with docker

- start azkaban

```
    docker run -p 8080:8080 -v azkaban_home_data:/var/azkaban --network azkaban-network --name azkaban-srv -e TZ='Asia/Shanghai' haxqer/azkaban
```
