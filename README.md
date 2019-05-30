Ansible Role: Prometheus Exporter Installer
==================

[![Build Status](https://travis-ci.org/Lusitaniae/ansible-role-prometheus-exporter-installer.svg?branch=master)](https://travis-ci.org/Lusitaniae/ansible-role-prometheus-exporter-installer)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/Lusitaniae/ansible-role-prometheus-exporter-installer/master/LICENSE)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-prometheus--exporter--installer-blue.svg)](https://galaxy.ansible.com/Lusitaniae/prometheus-exporter-installer)


Role for installing prometheus exporters in your server.

Should work for _all_ exporters with a similar release procedure as the official ones. Where *promu* is used to build and package the exporters for a number of architectures and deploy the final packages to the respective release in GitHub.

Usecase
------------

Installing one or more exporters in a system. 

Useful when you're running traditional VMs which you may be sharing for multiple services.


Requirements
------------

None.


Example Playbook
-----------------


```yaml
- hosts: localhost

  vars:
    prometheus_exporter_install_plugins:
     - name: Apache Exporter
       github_user: Lusitaniae
       github_name: apache_exporter
       github_version: 0.4.0
       install_path: /usr/local/bin/apache_exporter
       exporter_args: -scrape_uri http://localhost/server-status/?auto

     - name: Memcached Exporter
       github_user: prometheus
       github_name: memcached_exporter
       github_version: 0.3.0
       install_path: /usr/local/bin/memcached_exporter
       exporter_args:


  roles:
    - Lusitaniae.prometheus-exporter-installer

```


License
-------

MIT
