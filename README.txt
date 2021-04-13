1) Build image twemproxy
    cd twemproxy && docker build -t baonnt/twemproxy

2) Build image twemproxy_exporter
    cd twemproxy_exporter && docker build -t baonnt/twemproxy_exporter

3) Run docker compose
    docker-compose up


-- GRAFANA:             localhost:3000
-- twemproxy:           localhost:22121
-- prometheus:          localhost:9090
-- twemproxy_exporter:  localhost:9151