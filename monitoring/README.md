# Monitoring Stack for Jenkins

This setup includes:

- Prometheus scraping Jenkins metrics from `http://65.2.4.206:8080/prometheus`
- Grafana running on port `3000`
- Pre-configured `prometheus.yml`

## How to Run

```bash
cd monitoring
docker-compose up -d
