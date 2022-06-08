# Cloud Bootstrap - Ansible Collection

## Overview

Ansible Collection to bootstrap new instances

## Contents

- First-run role for cloud instances (Installing updates, etc.)
- First-run role for VMs (Setting up Timezone, Hostname, Basic SSH hardening and passswordless sudo, etc.)
- Roles for initializing runtime for running containers (Docker, Docker Compose, ECR Credential Helper, ECS Agent, etc.)
- Additional playbooks for adding keys, diagnosing etc.

## Getting Started

### Use it in an Ansible playbook

#### Add cloudbootstrap to your `requirements.yml`

```yaml
---
collections:
  - smartassistco.cloudbootstrap
```

#### Define roles in your playbook (e.g. `initialize.yml`)

```yaml
- hosts: all
  roles:
    - smartassistco.cloudbootstrap.docker
    - smartassistco.cloudbootstrap.docker-compose
    - smartassistco.cloudbootstrap.ecr-credential-helper
  vars:
    docker_service_state: restarted
    docker_compose_version: '2.5.0'
  tasks:
  # Other tasks
```

#### Run your playbook

`ansible-playbook intialize.yml`

### Use without adding to your project

#### Install

`ansible-galaxy collection install smartassistco.cloudbootstrap`

#### Use directly

`ansible-playbook smartassistco.cloudbootstrap.nodeinfo`
