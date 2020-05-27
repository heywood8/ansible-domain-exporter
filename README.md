<p><img src="http://jacobsmedia.com/wp-content/uploads/2015/08/black-box-edit.png" alt="domain logo" title="domain" align="right" height="60" /></p>

# Ansible Role: Domain Exporter

# Description

Deploy and manage [domain exporter](https://github.com/caarlos0/domain_exporter) which to get expiratio dates of your websites.

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

## Local Testing

The preferred way of locally testing the role is to use Docker and [molecule](https://github.com/metacloud/molecule) (v2.x). You will have to install Docker on your system. See "Get started" for a Docker package suitable to for your system.
We are using tox to simplify process of testing on multiple ansible versions. To install tox execute:
```sh
pip3 install tox
```
To run tests on all ansible versions (WARNING: this can take some time)
```sh
tox
```
To run a custom molecule command on custom environment with only default test scenario:
```sh
tox -e py35-ansible28 -- molecule test -s default
```
For more information about molecule go to their [docs](http://molecule.readthedocs.io/en/latest/).

If you would like to run tests on remote docker host just specify `DOCKER_HOST` variable before running tox tests.

## Travis CI

Combining molecule and travis CI allows us to test how new PRs will behave when used with multiple ansible versions and multiple operating systems. This also allows use to create test scenarios for different role configurations. As a result we have a quite large test matrix which will take more time than local testing, so please be patient.

## Contributing

See [contributor guideline](CONTRIBUTING.md).

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
