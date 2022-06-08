ECR Credential Helper
=========

Installs the `amazon-ecr-credential-helper` packages and configures `~/.docker/config.json` to use the `ecr-login`
command.

**Known Limitation**: If `~/.docker/config.json` already exists, it will not be changed.

Requirements
------------

None.

Role Variables
--------------

None.

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - role: smartassistco.cloudbootstrap.ecr-credential-helper
      become: yes
```
