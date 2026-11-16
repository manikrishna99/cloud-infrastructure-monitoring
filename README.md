# Cloud Infrastructure Monitoring System

A containerized infrastructure monitoring project using Docker Compose, Prometheus, Node Exporter, and Grafana.

## Project Overview

This project collects infrastructure metrics and visualizes system performance through a Grafana dashboard. It also includes CPU and memory alert rules to identify high resource utilization.

## Technology Stack

- Docker and Docker Compose
- Prometheus
- Node Exporter
- Grafana
- PromQL
- Linux / WSL2

## Architecture

1. Node Exporter collects system metrics.
2. Prometheus scrapes metrics every 15 seconds.
3. Grafana connects to Prometheus as its data source.
4. Grafana dashboards visualize infrastructure metrics.
5. Grafana alert rules monitor CPU and memory usage.

## Dashboard Metrics

- CPU Usage (%)
- Memory Usage (%)
- Network Receive Traffic
- Network Transmit Traffic

## Alert Configuration

| Alert | Threshold | Evaluation |
|---|---:|---|
| High CPU Usage | 80% | Every 1 minute |
| High Memory Usage | 85% | Every 1 minute |

Both alerts have a pending period of 1 minute.

## Project Setup

### Prerequisites

- Docker Desktop
- Docker Compose
- WSL2 / Ubuntu

### Start the project

```bash
git clone <your-repository-url>
cd cloud-monitoring
docker compose up -d
```

### Access services

| Service | URL |
|---|---|
| Prometheus | http://localhost:9090 |
| Node Exporter | http://localhost:9100/metrics |
| Grafana | http://localhost:3001 |

## Prometheus Configuration

Prometheus scrapes:
- Prometheus itself
- Node Exporter

Scrape interval: 15 seconds.

## Current Limitations

- Disk usage visualization is not yet working in Grafana.
- Notification contact points are not configured.
- This is a local development and learning project, not a production monitoring deployment.
- Filesystem metrics reflect the filesystems exposed through the WSL environment.

## Future Improvements

- Disk usage monitoring
- Email notifications
- Alertmanager integration
- Persistent Grafana storage
- AWS EC2 monitoring
- Infrastructure monitoring with Terraform

## Author

Cloud Infrastructure Monitoring System — DevOps and Cloud Monitoring Portfolio Project.
