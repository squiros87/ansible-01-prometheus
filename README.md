# ansible-01-prometheus
This repository contains Ansible playbooks for configuring the Node Exporter and Prometheus server
## README

### Overview
This repository contains an Ansible playbook for configuring the Node Exporter and Prometheus server to automate server and network management efficiently.

### What is Prometheus?
Prometheus is an open-source tool for event monitoring and alerting, written in Go. It stores metrics in a time series database using an HTTP pull model, allowing for real-time alerting with flexible queries. The Node Exporter is a Prometheus component that exposes OS and hardware metrics.

### Why Ansible?
Ansible is an agentless automation and configuration tool that simplifies the deployment of Prometheus, enabling you to configure multiple servers in just a few minutes.

### Contents
- **Node Exporter Playbook:** Configures Node Exporter on servers for scraping.
- **Prometheus Server Playbook:** Installs Prometheus on a designated server.

### Node Exporter Playbook
#### Inventory Groups
- **scrape:** Servers for Node Exporter configuration.
- **server:** Server for Prometheus installation.

#### Variables
- `node_exporter_user`: User running the Node Exporter service.
- `node_exporter_version`: Version of the Node Exporter.
- `scraping_port`: Port exposing the metrics.
- `metric_path`: Path for metrics exposure.
- `textfile_collector_directory`: Directory for manually defined metrics.

#### Running the Playbook

ansible-playbook node_exporter.yaml -K


### Prometheus Server Playbook
#### Inventory Groups
- **server:** Server for Prometheus installation.

#### Variables
- `prometheus_user`: User running Prometheus.
- `prometheus_version`: Version of Prometheus.
- `scraping_port`: Port for scraping metrics.
- `metrics_path`: Path for scraping metrics.
- `config_prometheus`: Configuration directory.
- `prometheus_folder`: Installation directory.
- `prometheus_listen_address`: Address for Prometheus UI.

#### Running the Playbook

ansible-playbook prometheus_server.yaml -K


Once completed, Prometheus will be installed and configured to scrape metrics from hosts in the `scrape` group.

### Feedback
Try these playbooks and let me know what you think. Do you have any suggestions for improvement?

Socrates

