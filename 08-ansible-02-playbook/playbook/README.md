- [Netology DevOps Course Project Ansible-Playbook](#netology-devops-course-project-ansible-playbook)
- [Installation](#installation)
  - [Prerequisite](#prerequisite)
  - [Configure](#configure)
  - [Install](#install)
  - [Tags](#tags)

## Netology DevOps Course Project Ansible-Playbook

A community repository for Netology DevOps Course Project.

## Installation
This ansible playbook supports the following,
- Install ClickHouse and create logs database.
- Install and Configure Vector.

### Prerequisite
- **Ansible 2.9+**

### Configure
Refer the file `templates/config/vector.toml.j2` to change the default values for Vector.

### Tags
- clickhouse
- vector

### Install
    # Deploy with ansible playbook - run the playbook as root
    ansible-playbook site.yml -i inventory/prod.yml --ask-pass
    # Deploy ClickHouse with ansible playbook - run the playbook as root
    ansible-playbook site.yml -i inventory/prod.yml --ask-pass --tags clickhouse
    # Deploy Vector with ansible playbook - run the playbook as root
    ansible-playbook site.yml -i inventory/prod.yml --ask-pass --tags vector
