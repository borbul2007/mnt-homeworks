- [OpenSearch Project Ansible-Playbook](#opensearch-project-ansible-playbook)
- [OpenSearch Installation with Dashboards](#opensearch-installation-with-dashboards)
  - [Prerequisite](#prerequisite)
  - [Configure](#configure)
  - [Install](#install)

## OpenSearch Project Ansible-Playbook

A community repository for Ansible Playbook of OpenSearch Project.

## OpenSearch Installation with Dashboards

This ansible playbook supports the following,

- Can be deployed on baremetal and VMs(AWS EC2)
- Supports most popular **Linux distributions**(Centos7, RHEL7, Amazon Linux2, Ubuntu 20.04)
- Install and configure the Apache2.0 opensource OpenSearch
- Configure TLS/SSL for OpenSearch transport layer(Nodes to Nodes communication) and REST API layer
- Generate self-signed certificates to configure TLS/SSL for opensearch
- Configure the Internal Users Database with limited users and user-defined passwords
- Configuration of authentication and authorization via OpenID
- Overriding default settings with your own
- Install and configure the Apache2.0 opensource OpenSearch Dashboards

### Prerequisite

- **Ansible 2.9+**
- **Java 8**

### Configure

Refer the file `inventories/opensearch/group_vars/all/all.yml` to change the default values.

For example if we need to increase the java memory heap size for opensearch,

    xms_value: 8
    xmx_value: 8

In `inventories/opensearch/hosts` file, you can configure the node details.
`ansible_host` is used for ansible to connect the nodes to run this playbook.
`ip` is used in OpenSearch and Dashboards configuration.

### Install


    # Deploy with ansible playbook - run the playbook as root
    ansible-playbook -i inventories/opensearch/hosts opensearch.yml --extra-vars "admin_password=myStrongPassword@123! kibanaserver_password=Test@6789 logstash_password=Test@456"

You should set the reserved users(`admin`, `kibanaserver`, and `logstash`) password using `admin_password`, `kibanaserver_password`, and `logstash_password` variables.

**Note**: Starting OpenSearch 2.12, a strong password is required for `admin` user, i.e. `myStrongPassword123!`. The cluster will fail to start with a weak password (i.e. admin) or no password.