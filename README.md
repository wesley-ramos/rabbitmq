
### Directory Organization

```shell
./
├── grafana
│   └── dashboard.json
│
├── haproxy
│   ├── Dockerfile 
│   └── haproxy.cfg
│
├── prometheus
│   └──prometheus.yml 
│
├── rabbitmq
│   ├── Dockerfile 
│   └── rabbit.conf
│
└── docker-compose.yml
```

### How to start the cluster ?

```shell
docker-compose build
docker-compose up -d
```

### how to start replication between master and slave?

```shell
docker exec -it rabbitmq_master rabbitmqctl set_policy ha-all ".*" '{"ha-mode":"all"}
```
