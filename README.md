# Ansible Collection - Cloud Bootstrap

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
  - smartassistco.cloud_bootstrap
```

#### Define roles in your playbook (e.g. `initialize.yml`)

```yaml
- hosts: all
  roles:
    - smartassistco.cloud_bootstrap.initialize
    - smartassistco.cloud_bootstrap.docker
    - smartassistco.cloud_bootstrap.docker_compose
    - smartassistco.cloud_bootstrap.ecr_credential_helper
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

`ansible-galaxy collection install smartassistco.cloud_bootstrap`

#### Use directly

`ansible-playbook smartassistco.cloud_bootstrap.nodeinfo`
