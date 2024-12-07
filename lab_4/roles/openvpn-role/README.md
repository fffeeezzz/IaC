
---

### README для **Openvpn Role**

# Openvpn Role

An Ansible role for installing and configuring OpenVPN on a Linux server, generating client configuration files, and setting up a secure VPN connection.

## Requirements

- Ansible 2.9+ is required.
- Target system must be Ubuntu.

## Role Variables

The following variables can be customized in the role:
openvpn_port: 1194
openvpn_protocol: udp
openvpn_network: 10.8.0.0
openvpn_netmask: 255.255.255.0
openvpn_user: nobody
openvpn_group: nogroup
openvpn_cipher: AES-256-CBC
openvpn_keepalive: "10 120"
easy_rsa_path: /home/vagrant/easy-rsa

easy_rsa_pki_path: /home/vagrant/easy-rsa/pki
openvpn_config_path: /etc/openvpn/
openvpn_server_config_name: server.conf.j2
openvpn_client_config_name: client.ovpn.j2

| Variable                     | Default Value                |
|------------------------------|------------------------------|
| `openvpn_port`               | `1194`                       |
| `openvpn_protocol`           | `udp`                        |
| `openvpn_network`            | `10.8.0.0`                   |
| `openvpn_netmask`            | `255.255.255.0`              |
| `openvpn_user`               | `nobody`                     |
| `openvpn_group`              | `nogroup`                    |
| `openvpn_cipher`             | `AES-256-CBC`                |
| `openvpn_keepalive`          | `10 120`                     |
| `easy_rsa_path`              | `/home/vagrant/easy-rsa`     |
| `easy_rsa_pki_path`          | `/home/vagrant/easy-rsa/pki` |
| `openvpn_config_path`        | `/etc/openvpn/`              |
| `openvpn_server_config_name` | `server.conf.j2`             |
| `openvpn_client_config_name` | `client.ovpn.j2`             |

## Templates

This role includes template:

**server.conf.j2** - Main configuration file for server.
**client.conf.j2** - Main configuration file for client.


## Dependencies

This role has no dependencies on other roles.