Prometheus Grafana Microservicios
---------------------------------

Se debe mejorar los gráficos del grafana. 


http://jira.bch.bancodechile.cl:8080/browse/DSOC-126


## Descripción
----

Dashboards de grafana para profiling de microservicios

Dashboard de miroservicio basado en la info de prometheus y micrometer
Dashboard general con los micros, estado del cluster y micros top errors or latency
 

Entornos Dev y QA

Ejemplo de la información que puedes sacar de prometheus basado en un microservicio con micrometer habilitado (tienes que estar conectado a la VPN):

 

http://ms-demomonitor-sandbox.mipago-dev.oci.labsbch.cl/prometheus

 

 

Grafana QA:

http://grafana.mipago-qa.oci.labsbch.cl/

 

Grafana Dev:

http://grafana.mipago-dev.oci.labsbch.cl/

 

Usuario/pass grafana: revaldesb.vates@bancochile.cl / revaldesb.vates@bancochile.cl

 

## Graficos de ejemplo

 

* [Gráficos Java Micrometer QA](http://grafana.mipago-qa.oci.labsbch.cl/d/v_Nz5spMk/micros-j2c-java-micrometer?orgId=1)

 

* [Gráficos Java Micrometer Dev](http://grafana.mipago-dev.oci.labsbch.cl/d/v_Nz5spMk/micros-j2c-java-micrometer?orgId=1)

 

* [Grafico Nginx Ingress](http://grafana.mipago-dev.oci.labsbch.cl/d/nginx/nginx-ingress-controller?orgId=1&refresh=5s)


# Obtener las métricas sin #

```
curl http://ms-demomonitor-sandbox.mipago-dev.oci.labsbch.cl/prometheus |grep "^[^#;]"

```

* [Prometheus Query Language](https://grafana.com/blog/2020/02/04/introduction-to-promql-the-prometheus-query-language/)


* [](https://prometheus.io/docs/introduction/overview/)
* [METRIC AND LABEL NAMING](https://prometheus.io/docs/practices/naming/)


sum(avg_over_time(nginx_ingress_controller_nginx_process_connections{controller_pod=~"$controller",controller_class=~"$controller_class",controller_namespace=~"$namespace"}[2m]))



# Panel Editor


https://grafana.com/docs/grafana/latest/panels/panel-editor/




* [Google SRE Book](https://sre.google/sre-book/monitoring-distributed-systems/)