## Ansible playbook to setup a Prometheus server

### How to use it

- Clone the repository
- Create a variable file (Example: `group_vars/all.yml`)

**Available variables**
```
email: email@service.com
prometheus_domain: prometheus.yourdomain.com
prometheus_group: prometheus
prometheus_user: prometheus
prometheus_version: 2.35.0
prometheus_checksum: <checksum>
prometheus_binary_dir: /srv/prometheus
prometheus_config_dir: /etc/prometheus
prometheus_db_dir: /var/lib/prometheus
node_exporter_version: 1.3.1
node_exporter_checksum: <checksum>

prometheus_config:
  global:
    scrape_interval: 15s
    evaluation_interval: 15s

  scrape_configs:
  - job_name: prometheus
    static_configs:
      - targets: ['localhost:9090', 'localhost:9100']
```