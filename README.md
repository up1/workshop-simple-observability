# Workshop with Tracing and Metrics
* NodeJS 20
* Database PostgreSQL
* OpenTelemetry
* Tracing
  * Jaeger
* Metrics
  * Prometheus
  * Grafana
* Logging
  * Loki
  * Grafana
* [LGTM stack](https://github.com/grafana/docker-otel-lgtm)

### 1. Start Jaeger and Database
```
$docker compose up -d jaeger
$docker compose up -d db
$docker compose ps
```
Access to jaeger = http://localhost:16686/

### 2. Start `service a` with Docker compose
```
$docker compose build service-a
$docker compose up -d service-a
$docker compose ps
```

Access to service a
* http://localhost:3002
* http://localhost:3002/metrics

More endpoints
* Connect to db
  * http://localhost:3002/call-db
* More steps (custom spans)
  * http://localhost:3002/steps

### 3. Start prometheus to store metric data
```
$docker compose up -d prometheus
$docker compose ps
```

Access to prometheus = http://localhost:9090
* Go to menu Status => Targets

### More with
* Grafana
* Alert manager