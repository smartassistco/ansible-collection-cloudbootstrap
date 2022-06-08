Update Packages
=========

Updates all packages on yum/dnf/apt based distros

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
    - role: smartassistco.cloudbootstrap.update_packages
      become: yes
```
