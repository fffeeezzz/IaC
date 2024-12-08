# 4 лабораторная работа

## Создали роль "ansible-role-openvpn" для установки OpenVPN и вынесли в отдельный репозиторий

- https://github.com/fffeeezzz/ansible-role-openvpn

## Параметризовали роль через переменные

Подробное описание в ридми роли

## Создать файл requirements.yml для установки роли OpenVPN из репозитория

Добавили нашу роль и установили с помощью команды ansible-galaxy install -p ./roles/ -r requirements.yml

## Установили OpenVPN, используя плейбук с ролью OpenVPN

```yaml
- name: Install OpenVPN to server
  hosts: web
  become: true
  roles:
    - openvpn
```

## Конфигурационный файл для сервера

```text
port 1194
proto udp
dev tun

server 10.8.0.0 255.255.255.0
ifconfig-pool-persist ipp.txt

push "route 10.8.0.0 255.255.255.0"

keepalive 10 120

ca /etc/openvpn/ca.crt
cert /etc/openvpn/server.crt
key /etc/openvpn/server.key
dh /etc/openvpn/dh.pem
tls-auth /etc/openvpn/ta.key 0
cipher AES-256-CBC
user nobody
group nogroup
persist-key
persist-tun
```

## Конфигурационный файл для клиента

```text
client
dev tun
proto udp
remote 10.8.0.0 1194
resolv-retry infinite
nobind
persist-key
persist-tun

ca ca.crt
cert client.crt
key client.key
tls-auth ta.key 1
cipher AES-256-CBC
```