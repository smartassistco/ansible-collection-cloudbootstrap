Docker Compose
=========

Installs ECS agent on Amazon Linux 2

Requirements
------------

None.

Role Variables
--------------

Required:

```yaml
ecs_cluster_name: 'my-cluster'
```

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - role: smartassistco.cloudbootstrap.ecs_agent
      become: yes
      ecs_cluster_name: 'my-cluster'
```
