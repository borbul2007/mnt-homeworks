- [Netology DevOps Course Project Ansible-Playbook](#netology-devops-course-project-ansible-playbook)
- [Installation)
  - [Prerequisite](#prerequisite)
  - [Configure](#configure)
  - [Install](#install)

## Netology DevOps Course Project Ansible-Playbook

A community repository for Netology DevOps Course Projectt.

## Installation
This ansible playbook supports the following,
- Install ClickHouse and Vector
- Configure Vector

### Prerequisite
- **Ansible 2.9+**

### Configure
Refer the file `templates/config/vector.toml.j2` to change the default values for Vector.

### Install

    # Deploy with ansible playbook - run the playbook as root
    ansible-playbook -i inventories/opensearch/hosts opensearch.yml --extra-vars "admin_password=myStrongPassword@123! kibanaserver_password=Test@6789 logstash_password=Test@456"

You should set the reserved users(`admin`, `kibanaserver`, and `logstash`) password using `admin_password`, `kibanaserver_password`, and `logstash_password` variables.

**Note**: Starting OpenSearch 2.12, a strong password is required for `admin` user, i.e. `myStrongPassword123!`. The cluster will fail to start with a weak password (i.e. admin) or no password.
