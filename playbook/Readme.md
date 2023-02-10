## Ansible deployment Clickhouse and Vector  

# Description

Playbook deploys ClickHouse

Installs Vector on the specified host


# Requirements

Ansible >= 2.7

OS on deploy host must be from RPM line

Connection to host is made via ssh

# Variables

All variables which can be overridden are stored in group_vars/clickhouse/vars.yml file as well as in below.

Name	             -       Default Value	    -   Description

vector_version       -	     vector-0.27.0-1    -  	Latest version

clickhouse_version   -       22.3.3.44	        -    Latest version


# Local Testing
 
- you must indicate IP address and username host machine into /inventory/prod.yml 

  Testing performed on Yandex Cloud VM, ОS - Centoc 7
  
  Connection to VM organised via ssh

# Examples

---
clickhouse:

  hosts:

    clickhouse-01:

      ansible_host: 51.250.25.8

      ansible_ssh_user: amolokov
vector:

  hosts:

    vector:

      ansible_host: 51.250.25.8

      ansible_ssh_user: amolokov

