# docker-monitor
Monitor docker server using node_exporter, cadvisor, prometheus and display on grafana.

1. Create .env from .env.example.
```
NODE_EXPORTER_PORT=9100
CADVISOR_PORT=8080
```
2. For server: create directory and edit prometheus.yml.
```
./data/prometheus
```
```
./data/grafana
```
3. Generate password using script.
```
script/generate-password.sh
```
4. Edit prometheus.yml config.
```
static_configs:
  - targets: ['node_exporter:9100']
basic_auth:
  password: 'your_password'
```
5. Compose up.
```
agent.sh
```
or

```
server.sh
```
6. Connect to grafana. Default user and password is [admin](https://grafana.com/docs/grafana/latest/administration/configuration/#admin_user)
```
http://docker-host:3000
```
7. Add prometheus as datasource.
```
http://prometheus:9090
```
![Datasource](document/datasource.png)
8. Add dashboard to grafana.
  - Host monitor
    - [Node Exporter Full](https://grafana.com/grafana/dashboards/1860)
    - [1 Node Exporter for Prometheus Dashboard EN 20201010](https://grafana.com/grafana/dashboards/11074)
  - Containrt monitor
    - [Docker Container](https://grafana.com/grafana/dashboards/11600)
    - [Docker monitoring with node selection](https://grafana.com/grafana/dashboards/8321)
  - Log monitor
    - [docker log](report/docker-log.json)
