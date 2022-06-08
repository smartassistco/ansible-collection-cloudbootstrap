Docker Compose
=========

Installs Docker Compose on Linux, macOS

Requirements
------------

None.

Role Variables
--------------

Defaults:

```yaml
docker_compose_version: 'latest'
```

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - role: smartassistco.cloudbootstrap.docker_compose
      become: yes
```

With variables:

```yaml
- hosts: servers
  roles:
    - role: smartassistco.cloudbootstrap.docker_compose
      become: yes
      docker_compose_version: '2.5.1'
```
