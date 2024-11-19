Ansible Role Nginx
=========

Роль "ansible-role-nginx" для установки Nginx.

Role Variables
--------------

1. порт nginx
    - nginx_port: 80 (по умолчанию)

2. порт сервера, на который будут проксироваться запросы
    - nginx_proxy_port: 8000 (по умолчанию)

3. айпи сервера, на который будут проксироваться запросы
    - nginx_proxy_ip: localhost (по умолчанию)

4. директория со статическими файлами
    - nginx_static_path: /var/html/static/ (по умолчанию)

5. кол-во соединений
    - nginx_worker_connections: 1024 (по умолчанию)

Example Playbook
----------------

Добавление в файл requirements.yml

```yaml
- name: nginx
  src: git+https://gitlab.com/ansible-roles7831444/ansible-role-nginx.git
```

Использование в плейбуке

```yaml
- name: Установка Nginx
  hosts: web
  become: true
  roles:
    - nginx
```

License
-------

BSD