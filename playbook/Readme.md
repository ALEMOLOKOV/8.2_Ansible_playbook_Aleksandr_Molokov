## Ansible deployment Clickhouse, Vector, Lighthouse and install Nginx  

# Description

Playbook deploys:

ClickHouse on the specified host

Vector on the specified host

Lighthouse on the specified host

Install and configur Nginx on the specified host


# Requirements

Ansible >= 2.10

OS on deploy host must be from RPM line

Connection to host is made via ssh

# Variables

All variables which can be overridden are stored in group_vars

CLickhouse - /clickhouse/vars.yml file as well as in below.

/-------------------------/-------------------------/-----------------/
    Name	               Default Value	       Description
/-------------------------/-------------------------/-----------------/

clickhouse_version             22.3.3.44	       Latest version


Vector - /vector/vars.yml file as well as in below

/-------------------------/-------------------------/-----------------/
    Name                       Default Value            Description
/-------------------------/-------------------------/-----------------/

vector_version                 vector-0.27.0-1          Latest version

Directory /template include:
lighthouse.conf.j2 - config for Lighthouse
nginx.conf.j2 - config for Nginx

# Local Testing
 
- you must indicate IP address and username host machines into /inventory/prod.yml 

Testing performed on 3 Yandex Cloud VMs:
1 - Clickhouse, ОS - Centoc 7, CPU - 2, RAM - 4 Gb, Disk - 10Gb
2 - Vector, ОS - Centoc 7, CPU - 2, RAM - 4 Gb, Disk - 10Gb
3 - Lighthouse, ОS - Centoc 7, CPU - 2, RAM - 2 Gb, Disk - 10Gb
  
username indicate - ansible_ssh_user:
  
Connection to VM organised via ssh

# Examples

---
clickhouse:
  hosts:
    clickhouse:
      ansible_host: 51.250.72.71
      ansible_ssh_user: amolokov
vector:
  hosts:
    vector:
      ansible_host: 51.250.84.243
      ansible_ssh_user: amolokov
lighthouse:
  hosts:
    lighthouse:
      ansible_host: 51.250.81.185
      ansible_ssh_user: amolokov

