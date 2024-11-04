Ansible Role: Logrotate-docker
==============================

Install Dockerized Logrotate project.

- https://github.com/blacklabelops/logrotate

Requirements
------------

Requires the following to be installed:
- docker
- docker compose

Role Variables
--------------

Common Docker projects variables:

```yaml
# Base directory for Docker projects
docker_projects_path: # /var/apps
```

Available role variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
# Docker project variables

logrotate_project_name: logrotate

# Logrotate project variables

logrotate_logs: []
# Ex:
#  - src:  /host/app1/path/logs # path on host
#    dest: /var/log/app1        # path in logrotate container
#  - src:  /host/app2/path/logs # ...
#    dest: /var/log/app2        # ...

logrotate_interval: daily
logrotate_copies:   31
logrotate_size:     64M
logrotate_mode:     copytruncate
```

Dependencies
------------

This role depends on :
- [djuuu.docker_project](https://github.com/Djuuu/ansible-role-docker-project)

Example Playbook
----------------

```yaml
- hosts: all
  gather_facts: false
  roles:
    - djuuu.logrotate_docker
```

License
-------

Beerware License
