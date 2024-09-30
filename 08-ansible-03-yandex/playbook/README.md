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
- Deploy Lighthouse web staic site for Nginx web server.

### Prerequisite
- **Ansible 2.9+**

### Configure
Refer the file `templates/config/vector.toml.j2` to change the default values for Vector.
Refer the file `templates/config/lighthouse.conf.j2` site with Lighthouse static for Nginx web server on 8080 port.

### Tags
- clickhouse
- vector
- lighthouse

### Install
    # Deploy with ansible playbook - run the playbook as root
    ansible-playbook site.yml -i inventory/prod.yml 
    # Deploy ClickHouse with ansible playbook - run the playbook as root
    ansible-playbook site.yml -i inventory/prod.yml  --tags clickhouse
    # Deploy Vector with ansible playbook - run the playbook as root
    ansible-playbook site.yml -i inventory/prod.yml --tags vector
    # Deploy Lighthouse with ansible playbook - run the playbook as root
    ansible-playbook site.yml -i inventory/prod.yml --tags lighthouse
