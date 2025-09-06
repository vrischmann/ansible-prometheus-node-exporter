Role Name
=========

Install [prometheus-node-exporter](https://github.com/prometheus/node_exporter).

Requirements
------------

Ansible 2.9+.
Debian buster+.

Role Variables
--------------

| Name           | Required | Description                         |
| -------------- | -------- | ----------------------------------- |
| `prometheus_node_exporter_version` | yes | Node exporter package version. Can be found [here](https://github.com/prometheus/node_exporter/releases) |
| `prometheus_node_exporter_checksum` | yes | Checksum of the package. Can be found [here](https://github.com/prometheus/node_exporter/releases) |
| `prometheus_node_exporter_architecture` | no | CPU architecture of the package. Defaults to `amd64` |
| `prometheus_node_exporter_listen_addresses` | yes | List of addresses on which node exporter will listen (at least one is required) |
| `prometheus_node_exporter_enabled_collectors` | no | List of additionally enabled collectors. It adds collectors to [those enabled by default](https://github.com/prometheus/node_exporter#enabled-by-default) |
| `prometheus_node_exporter_disabled_collectors` | no | List of disabled collectors. By default node_exporter disables collectors listed [here](https://github.com/prometheus/node_exporter#disabled-by-default) |
| `prometheus_node_exporter_memory_limit` | no | Memory limit for the systemd service. Defaults to 32M |
| `prometheus_node_exporter_limit_nofile` | no | LimitNOFILE for the systemd service. Defaults to 4096 |
| `prometheus_node_exporter_limit_nproc` | no | LimitNPROC for the systemd service. Defaults to 512 |
| `prometheus_node_exporter_service_extra_after` | no | Appends to the After= property of the service. Useful to make sure your VPN is up if you need to listen on its interface |
| `prometheus_node_exporter_service_extra_wants` | no | Appends to the Wants= property of the service. Useful to make sure your VPN is up if you need to listen on its interface |
| `prometheus_node_exporter_service_extra_requires` | no | Appends to the Requires= property of the service. Useful to make sure your VPN is up if you need to listen on its interface |

Example
-------

```
- hosts: servers
  vars:
    prometheus_node_exporter_version: "1.9.1"
    prometheus_node_exporter_checksum: "sha256:becb950ee80daa8ae7331d77966d94a611af79ad0d3307380907e0ec08f5b4e8"
    prometheus_node_exporter_listen_addresses:
      - "0.0.0.0:9100"
  roles:
     - vrischmann.prometheus-node-exporter
```

License
-------

MIT
