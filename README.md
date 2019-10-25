# Ansible Role: rabbitmq-exporter

An Ansible role that installs [Prometheus RabbitMQ Exporter](https://github.com/kbudde/rabbitmq_exporter) with systemd.

## Requirements

All needed packages will be installed with this role.

## Role Variables

Available variables are listed below, along with default values:
```yaml
rabbitmq_exporter_version: 0.29.0
rabbitmq_exporter_download_url: "https://github.com/kbudde/rabbitmq_exporter/releases/download/v"

rabbitmq_exporter_config_flags:
  'rabbit_url': 'http://localhost:15672'
  'rabbit_user': 'guest'
  'rabbit_password': 'guest'
  'rabbit_user_file': ''
  'rabbit_password_file': ''
  'publish_port': '9090'
  'output_format': 'TTY'
  'log_level': 'info'
  'cafile': 'ca.pem'
  'skipverify': 'false'
  'include_queues': '.*'
  'skip_queues': '^$'
  'rabbit_capabilities': 'no_sort,bert'
  'rabbit_exporter': 'exchange,node,overview,queue'
```
## Dependencies

## Example Playbook
```yaml
- hosts: node-exporters
  roles:
    - rabbitmq-exporter
```
## License

Apache V2