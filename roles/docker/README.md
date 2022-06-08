Docker
=========

Installs Docker on Amazon Linux, CentOS and Debian.

Requirements
------------

None.

Role Variables
--------------

Defaults:

```yaml
add_currentuser_docker_group: true

docker_service_state: started
docker_service_enabled: true
```

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - role: smartassistco.cloudbootstrap.docker
      become: yes
```

With variables:

```yaml
- hosts: servers
  roles:
    - role: smartassistco.cloudbootstrap.docker
      become: yes
      docker_service_state: stopped
```
