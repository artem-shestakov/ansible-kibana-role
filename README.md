Ansible kibana role
=========

Ansible role to install [Kibana](https://www.elastic.co/guide/en/kibana/current/get-started.html) on Debian/Red Hat OS family.

Requirements
------------
None

Role Variables
--------------
| Variables                            | Description                                                                |
|--------------------------------------|----------------------------------------------------------------------------|
| version                              | Kibana major version. **Default:** 7                                       |
| server.host                          | IP address or DNS name of the Kibana server. **Default:** 127.0.0.1
| server.port                          | The port to use. **Default:** 5601                                                            |
| elasticsearch.hosts                  | The Elasticsearch instances for all queries. **Default:** http://localhost:9200                         | 
| elasticsearch.sniffInterval          | Time between requests to check Elasticsearch for an updated list of nodes. **Default:** false |
| elasticsearch.sniffOnConnectionFault | Update the list of Elasticsearch nodes if connection fault. **Default:** false            |
| logging.dest                         | Kibana logs. **Default:** stdout                                                               |

   
More information on [Kibana settings](https://www.elastic.co/guide/en/kibana/current/settings.html).

Example Playbook
------------
```
---
- hosts: kibana
  remote_user: user
  roles:
    - artem_shestakov.kibana

  vars:
    server_host: "{{ hostvars[inventory_hostname]['inventory_hostname'] }}"
    server_port: "5601"
    elasticsearch_hosts: [ "http://192.168.1.1:9200","http://192.168.1.2:9200","http://192.168.1.3:9200" ]
    elasticsearch_sniffInterval: 600000
    elasticsearch_sniffOnConnectionFault: true
    logging_dest: "/var/log/kibana/kibana.log"
```


Dependencies
------------
None

License
-------
BSD, MIT


Author Information
------------------
Artem Shestakov (artem.s.shestakov@gmail.com)
