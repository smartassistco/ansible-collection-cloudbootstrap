# Ansible Collection - smartassist.cloud_bootstrap

## Overview

Ansible Collection to bootstrap new instances

## Contents

- First-run role for cloud instances (Installing updates, etc.)
- First-run role for VMs (Setting up Timezone, Hostname, Basic SSH hardening and passswordless sudo, etc.)
- Roles for initializing runtime for running containers (Docker, Docker Compose, ECR Credential Helper, ECS Agent, etc.)
- Additional playbooks for adding keys, diagnosing etc.

## Getting Started

### Use it in an Ansible playbook

#### Add cloud_bootstrap to your `requirements.yml`

```yaml
---
collections:
  - smartassist.cloud_bootstrap
```

#### Define roles in your playbook (e.g. `initialize.yml`)

```yaml
- hosts: all
  roles:
    - smartassist.cloud_bootstrap.initialize
    - smartassist.cloud_bootstrap.docker
    - smartassist.cloud_bootstrap.docker_compose
    - smartassist.cloud_bootstrap.ecr_credential_helper
  vars:
    docker_service_state: restarted
    docker_compose_version: 2.5.0
  tasks:
  # Other tasks
```

#### Run your playbook

`ansible-playbook intialize.yml`

### Use without adding to your project

#### Install

`ansible-galaxy collection install smartassist.cloud_bootstrap`

#### Use directly

`ansible-playbook smartassist.cloud_bootstrap.nodeinfo`
