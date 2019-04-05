
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

### How to start replication between master and slave ?

```shell
docker exec -it rabbitmq_master rabbitmqctl set_policy ha-all ".*" '{"ha-mode":"all"}
```

### How to access the RabbitMQ panel ?

```shell
URL: http://localhost:15672
Username: admin
Password: admin
```

### How to access and configure infrastructure monitoring ?

1. Access grafana

```shell
URL: http://localhost:3000
Username: admin
Password: admin
```

2. Create a datasource of type prometheus

```shell
Configuration->Data Sources->Add data source
```

3. Import the dashboard

```shell
Create->Import->Upload .json File
```
select the ./grafana/dashboard.json
