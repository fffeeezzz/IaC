Role Name
=========

Роль "ansible-role-openvpn" для установки OpenVPN.

Default Role Variables
--------------

```yaml
openvpn_port: 1194
openvpn_protocol: udp
openvpn_network: 10.8.0.0
openvpn_netmask: 255.255.255.0
openvpn_user: nobody
openvpn_group: nogroup
openvpn_cipher: AES-256-CBC
openvpn_keepalive: "10 120"
openvpn_easy_rsa_path: /home/dportnov/easy-rsa
openvpn_easyrsa_tool_path: /usr/share/easy-rsa
openvpn_easy_rsa_pki_path: /home/dportnov/easy-rsa/pki
openvpn_config_path: /etc/openvpn
openvpn_server_config_name: server.ovpn.j2
openvpn_client_config_name: client.ovpn.j2
```

Example Playbook
----------------

Добавление в файл requirements.yml

```yaml
- name: openvpn
  src: git+https://github.com/fffeeezzz/ansible-role-openvpn.git
```

Использование в плейбуке

```yaml
- name: Установка OpenVPN
  hosts: web
  become: true
  roles:
    - openvpn
```

License
-------

MIT
