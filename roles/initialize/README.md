Initialize Linux
=========

Performs some common tasks on a new Linux system. All tasks are optional, and configurable.

By default, this role will:

- Update all packages
- Set timezone to UTC
- Set hostname if the variable is defined
- Enables passwordless sudo
- Hardens the SSH configuration

Requirements
------------

None.

Role Variables
--------------

Defaults:

```yaml
update_packages: true

set_timezone_utc: true

enable_passwordless_sudo: true

enable_basic_ssh_hardening: true
```

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - role: smartassistco.cloudbootstrap.initialize
      become: yes
      hostname: box1.example.com
```

With variables:

```yaml
- hosts: servers
  roles:
    - role: smartassistco.cloudbootstrap.initialize
      become: yes
      update_packages: false
      enable_basic_ssh_hardening: false
```
