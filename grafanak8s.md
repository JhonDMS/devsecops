## Grafana Prometheus en K8s

kubectl get namespaces

kubectl create ns monitoring



## Instalación grafana local con docker compose
---------------------------------------------

## Archivo original prometheus.yml

* [Archivo prometheus.yml Inicial](https://github.com/prometheus/prometheus/blob/release-2.7/documentation/examples/prometheus.yml)

```
# my global config
global:
  scrape_interval:     15s # Set the scrape interval to every 15 seconds. Default is every 1 minute.
  evaluation_interval: 15s # Evaluate rules every 15 seconds. The default is every 1 minute.
  # scrape_timeout is set to the global default (10s).

# Alertmanager configuration
alerting:
  alertmanagers:
  - static_configs:
    - targets:
      # - alertmanager:9093

# Load rules once and periodically evaluate them according to the global 'evaluation_interval'.
rule_files:
  # - "first_rules.yml"
  # - "second_rules.yml"

# A scrape configuration containing exactly one endpoint to scrape:
# Here it's Prometheus itself.
scrape_configs:
  # The job name is added as a label `job=<job_name>` to any timeseries scraped from this config.
  - job_name: 'prometheus'

    # metrics_path defaults to '/metrics'
    # scheme defaults to 'http'.

    static_configs:
    - targets: ['localhost:9090']
```



# Scrape Config de Bitbucket
--------------------------
```

scrape_configs:
  - job_name: 'bitbucket'
    scheme: http #change to http if don't you have https
    metrics_path: '/plugins/servlet/prometheus/metrics'
    static_configs:
      - targets: ['10.252.226.123:7990']
```

# Docker compose
----

```
version: '3'
services:
  promcontainer:
    image: "prom/prometheus"
    volumes:
     - ./prometheus.yml:/etc/prometheus/prometheus.yml
    command: "--config.file=/etc/prometheus/prometheus.yml"
    ports:
     - "9090:9090"
  grafanacontainer:
    image: "grafana/grafana"
    ports:
     - "3000:3000"
```

docker-compose up




# Referencias

* [Setup Prometheus Monitoring on Kubernetes using Helm and Prometheus Operator ](https://youtu.be/QoDqxm7ybLc)

* [Monitor Your Kubernetes Cluster With Prometheus and Grafana](https://medium.com/better-programming/monitor-your-kubernetes-cluster-with-prometheus-and-grafana-1f7d0195e59)