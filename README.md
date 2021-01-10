Role Name
=========

Deploy [node exporter](https://github.com/prometheus/node_exporter).

Requirements
------------

Ansible 2.9+.

Role Variables
--------------

| Name           | Required | Description                         |
| -------------- | -------- | ----------------------------------- |
| `prometheus_node_exporter_version` | yes | Node exporter package version. Can be found [here](https://github.com/prometheus/node_exporter/releases) |
| `prometheus_node_exporter_checksum` | yes | Checksum of the package. Can be found [here](https://github.com/prometheus/node_exporter/releases) |
| `prometheus_node_exporter_listen_addr` | yes | Address on which node exporter will listen |
| `prometheus_node_exporter_enabled_collectors` | no | List of additionally enabled collectors. It adds collectors to [those enabled by default](https://github.com/prometheus/node_exporter#enabled-by-default) |
| `prometheus_node_exporter_disabled_collectors` | no |List of disabled collectors. By default node_exporter disables collectors listed [here](https://github.com/prometheus/node_exporter#disabled-by-default). |


Example
-------

```
    - hosts: servers
      roles:
         - vrischmann.prometheus-node-exporter
```

License
-------

MIT
