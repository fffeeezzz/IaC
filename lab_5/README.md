# 5 лабораторная работа

## Создали роль "ansible-role-postgres" для установки PostgreSQL и вынесли в отдельный репозиторий

- https://github.com/fffeeezzz/ansible-role-postgres

## Параметризовали роль через переменные

Подробное описание в ридми роли

## Создать файл requirements.yml для установки роли PostgreSQL из репозитория

Добавили нашу роль и установили с помощью команды ansible-galaxy install -p ./roles/ -r requirements.yml

## Установили PostgreSQL, используя плейбук с ролью postres

```yaml
---
- name: Устанавливаем мастер PostgreSQL
  hosts: master
  become: true
  tasks:
    - name: Подключаем таски PostgreSQL для мастера
      include_role:
        name: postgres

- name: Устанавливаем реплику
  hosts: replica
  become: true
  tasks:
    - name: Подключаем таски PostgreSQL для реплики
      include_role:
        name: postgres
```

## Продумали механизм по опеределинию мастер и реплика нод

С помощью переменной `postgres_role` можно указать `master` или `replica` нода.
Можно явно передавать в плейбуке, либо же вынести в group_vars, что и сделали в данном случае.
