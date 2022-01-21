# docker-monitor
Monitor docker server using node_exporter, cadvisor, prometheus and display on grafana.

1. Compose up.
```
docker compose up -d
```
2. Connect to grafana. Default user and password is [admin](https://grafana.com/docs/grafana/latest/administration/configuration/#admin_user)
```
http://docker-host:3000
```
3. Add prometheus as datasource.
![Datasource](document/datasource.png)
4. Add dashboard to grafana.
[Docker Host & Container Overview](https://grafana.com/grafana/dashboards/395)
