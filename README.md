Role Name
=========

Deploy [node exporter](https://github.com/prometheus/node_exporter).

Requirements
------------

Ansible 2.9+.

Role Variables
--------------

All variables are required.

| Name           | Description                         |
| -------------- | ----------------------------------- |
| `prometheus_node_exporter_version` | Node exporter package version. Can be found [here](https://github.com/prometheus/node_exporter/releases) |
| `prometheus_node_exporter_checksum` | Checksum of the package. Can be found [here](https://github.com/prometheus/node_exporter/releases) |
| `prometheus_node_exporter_listen_addr` | Address on which node exporter will listen |
| `prometheus_node_exporter_enabled_collectors` | List of additionally enabled collectors. It adds collectors to [those enabled by default](https://github.com/prometheus/node_exporter#enabled-by-default) |
| `prometheus_node_exporter_disabled_collectors` | List of disabled collectors. By default node_exporter disables collectors listed [here](https://github.com/prometheus/node_exporter#disabled-by-default). |


Example
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - vrischmann.prometheus-node-exporter

License
-------

MIT
