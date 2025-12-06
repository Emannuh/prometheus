# Prometheus Monitoring Stack

A complete monitoring solution using Prometheus, Grafana, and various exporters for comprehensive system and application monitoring.

## Overview

This project sets up a monitoring stack with:
- **Prometheus**: Time-series database and monitoring system
- **Grafana**: Visualization and analytics platform
- **Node Exporter**: Hardware and OS metrics
- **cAdvisor**: Container metrics
- **Alertmanager**: Alert handling and notifications

## Features

- Real-time system metrics collection
- Container and Docker monitoring
- Custom alerting rules
- Beautiful dashboards with Grafana
- Easy deployment with Docker Compose

## Prerequisites

- Docker
- Docker Compose
- Basic understanding of monitoring concepts

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Emannuh/prometheus.git
cd prometheus
```

### 2. Start the monitoring stack

```bash
docker-compose up -d
```

### 3. Access the services

- **Prometheus**: http://localhost:9090
- **Grafana**: http://localhost:3000 (default login: admin/admin)
- **Alertmanager**: http://localhost:9093
- **Node Exporter**: http://localhost:9100
- **cAdvisor**: http://localhost:8080

## Configuration

### Prometheus Configuration

Edit `prometheus.yml` to add or modify scrape targets:

```yaml
scrape_configs:
  - job_name: 'prometheus'
    static_configs:
      - targets: ['localhost:9090']
```

### Alert Rules

Alert rules are defined in `alert_rules.yml`. Customize them based on your monitoring needs.

### Grafana Dashboards

1. Log into Grafana
2. Add Prometheus as a data source
3. Import pre-built dashboards or create custom ones

## Project Structure

```
prometheus-monitoring/
├── docker-compose.yml
├── prometheus.yml
├── alert_rules.yml
├── alertmanager.yml
└── README.md
```

## Common Commands

### View logs
```bash
docker-compose logs -f prometheus
```

### Stop the stack
```bash
docker-compose down
```

### Restart services
```bash
docker-compose restart
```

### Update and rebuild
```bash
docker-compose down
docker-compose up -d --build
```

## Monitoring Metrics

This stack collects various metrics including:
- CPU usage
- Memory utilization
- Disk I/O
- Network statistics
- Container performance
- Application-specific metrics

## Troubleshooting

### Services not starting
```bash
docker-compose ps
docker-compose logs [service-name]
```

### Check Prometheus targets
Navigate to http://localhost:9090/targets to verify all targets are up.

### Reset Grafana password
```bash
docker-compose exec grafana grafana-cli admin reset-admin-password newpassword
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open source and available under the [MIT License](LICENSE).

## Resources

- [Prometheus Documentation](https://prometheus.io/docs/)
- [Grafana Documentation](https://grafana.com/docs/)
- [Docker Documentation](https://docs.docker.com/)

## Author

**Emannuh**

## Acknowledgments

- Prometheus community
- Grafana Labs
- Docker community
