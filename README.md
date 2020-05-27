# Ansible Role: Domain Exporter

# Description

Deploy and manage [domain exporter](https://github.com/caarlos0/domain_exporter) which to get expiration dates of your websites.

## Requirements

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `domain_exporter_version` | 1.7.2 | Domain exporter package version |
| `domain_exporter_web_listen_address` | 0.0.0.0:9222 | Address on which domain exporter will be listening |

## Example

### Playbook

```yaml
- hosts: all
  become: true
  roles:
    - heywood8.domain-exporter
```

## Contributing

See [contributor guideline](CONTRIBUTING.md).

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
