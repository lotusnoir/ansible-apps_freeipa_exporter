# Ansible Role: ansible-apps_freeipa_exporter

## Description

[![Build Status](https://travis-ci.com/lotusnoir/ansible-apps_freeipa_exporter.svg?branch=master?style=flat)](https://travis-ci.com/lotusnoir/ansible-apps_freeipa_exporter)
[![License](https://img.shields.io/badge/license-Apache--2.0-brightgreen?style=flat)](https://opensource.org/licenses/Apache-2.0)
[![Ansible Role](https://img.shields.io/badge/galaxy-apps_freeipa_exporter-purple?style=flat)](https://galaxy.ansible.com/lotusnoir/apps_freeipa_exporter)
![GitHub repo size](https://img.shields.io/github/repo-size/lotusnoir/ansible-apps_freeipa_exporter?color=orange&style=flat)
![Ansible Quality Score](https://img.shields.io/ansible/quality/52300)
[![downloads](https://img.shields.io/ansible/role/d/52300)](https://galaxy.ansible.com/lotusnoir/apps_freeipa_exporter)
[![Version](https://img.shields.io/github/release/lotusnoir/ansible-apps_freeipa_exporter.svg)](https://github.com/lotusnoir/ansible-apps_freeipa_exporter/releases/)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_freeipa_exporter&metric=alert_status)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_freeipa_exporter)
[![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_freeipa_exporter&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_freeipa_exporter)
[![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_freeipa_exporter&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_freeipa_exporter)
[![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_freeipa_exporter&metric=security_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_freeipa_exporter)

Deploy [freeipa_exporter](https://github.com/boynux/freeipa-exporter) to expose freeipa metrics to prometheus.

## Role variables

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `freeipa_exporter_version` | 0.2.1 | freeipa_exporter version |
| `freeipa_exporter_install_dir` | /usr/local/bin | directory to install binary |
| `freeipa_exporter_force_install` | false | force install variable |
| `freeipa_exporter_loglevel` | info | loglevel of exporter |
| `freeipa_exporter_freeipa_admin` | admin | admin username of freeipa |
| `freeipa_exporter_freeipa_passwd` | admin | admin password of freeipa |
| `freeipa_exporter_freeipa_url` | http://localhost:9000 | port of the freeipa service on the freeipa server |
| `freeipa_exporter_listen_port` | 9122 | port to expose prometheus metrics |

## Examples

	---
	- hosts: apps_freeipa_exporter
	  become: yes
	  become_method: sudo
	  gather_facts: yes
	  roles:
	    - role: ansible-apps_freeipa_exporter
	  environment: 
	    http_proxy: "{{ http_proxy }}"
	    https_proxy: "{{ https_proxy }}"
	    no_proxy: "{{ no_proxy }}

## License

This project is licensed under Apache License. See [LICENSE](/LICENSE) for more details.
