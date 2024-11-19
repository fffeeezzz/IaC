Ansible Role Docker
=========

Роль "ansible-role-docker" для установки Docker

Role Variables
--------------

1. docker_repo_url - урл репозитория докера

- По умолчанию https://download.docker.com/linux/{{ дистрибутив ОС }}

2. docker_gpg_key_url - урл GPG ключа для докера

- По умолчанию использует урл репозитория докера {{docker_repo_url}} + /gpg

3. docker_users - пользователь, которые необходимо добавить в группу "docker"

- По умолчанию пустой список

Example Playbook
----------------

Добавление в файл requirements.yml

```yaml
- name: docker
  src: git+https://gitlab.com/ansible-roles7831444/ansible-role-docker.git
```

Использование в плейбуке

```yaml
- name: Установка Docker
  hosts: app
  become: true
  roles:
    - docker
```

License
-------

BSD

