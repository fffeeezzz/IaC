# 2 лабораторная работа

## Создали роль "ansible-role-docker" для установки Docker и вынесли в отдельный репозиторий

- https://gitlab.com/ansible-roles7831444/ansible-role-docker

## Параметризовали роль через переменные

### defaults

Подробное описание в ридми роли

- docker_repo_url
- docker_gpg_key_url
- docker_users

### vars

По примеру из лекций создали файл /vars/x86_64.yml, который содержит архитектуру ОС для установки Docker

## Создать файл requirements.yml для установки роли Docker из репозитория

Добавили нашу роль и установили с помощью команды ansible-galaxy install -p ./roles/ -r requirements.yml

## Запустить приложение на нодах группы [app] используя ansible-playbook с ролью “Docker”

В плейбуке для установки Docker заменили использование тасок на использование роли