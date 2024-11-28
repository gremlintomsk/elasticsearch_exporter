# elasticsearch_exporter Ansible role

- [elasticsearch_exporter Ansible role](#elasticsearchexporter-ansible-role)
  - [Variables](#variables)
  - [Examples](#examples)

This roles installs Prometheus ElasticSearch Exporter.

Prometheus ElasticSearch Exporter makes available system metrics for collection by Prometheus server.

For more information about Prometheus ElasticSearch Exporter please visit
[https://github.com/justwatchcom/elasticsearch_exporter](https://github.com/justwatchcom/elasticsearch_exporter).

For more information about Prometheus Server please visit
[https://prometheus.io](https://prometheus.io).

```YAML
- name: stuart.elasticsearch_exporter
  version: 2.0.0
```

and run `ansible-galaxy install -p ./roles -r requirements.yml`

## Variables

Please have a look at [defaults/main.yml](defaults/main.yml) and [vars/main.yml](vars/main.yml) to know which parameter you can customize.

A special note about `elasticsearch_exporter_opts`. This dictionary contains the options that will be used to run the elasticsearch_exporter
and you can find [all the configuration parameters](https://github.com/justwatchcom/elasticsearch_exporter#configuration) in the exporter documentation.
Keep in mind that since it's a dictionary you will need to rewrite it completely if you want to customize one parameter,
or you should enabled variables merging in `ansible.cfg`


## Examples

Simply include role in your playbook

Default elasticsearch: localhost:9200
Default exporter port: 9108

```YAML
- name: Install and configure prometheus_elasticsearch_exporter
  hosts: "somehost"

  roles:
    - role: stuart.elasticsearch_exporter
```

```YAML
- name: Install and configure prometheus_elasticsearch_exporter and enable start on boot.
  hosts: "somehost"

  roles:
    - role: stuart.elasticsearch_exporter
      elasticsearch_exporter_start_on_boot: yes
```
