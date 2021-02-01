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

Dependencies
------------
None

License
-------
BSD

Author Information
------------------
Artem Shestakov (artem.s.shestakov@gmail.com)
