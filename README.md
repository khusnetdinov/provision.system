# Provision.user

This receipt update system on Ubuntu server.

## What it does?

 Under root user it:

 * Apt update

 * Installs required packages

 * Set timezone

 * Setup UWF

## Files structure

```
  ├── /defaults/                  # Default variables for playbook
  │   └── main.yml                # Variables for playbook
  ├── /meta/                      # Meta
  │   └── main.yml                # Ansible Galaxy meta information
  ├── /tasks/                     # Play tasks
  │   └── main.yml                # User provision task
  │── README.md                   # Project description
  │── hosts                       # Inventory file
  └── playbook.yml                # Playbook file
```

## Usage

#### Set Variables

```yaml
  # defaults/main.yml

  # Set variables below
  provision_user_name: root
  provision_system_packages: ['curl', 'git', 'ufw']
  provision_system_locale: en_US.UTF-8
  provision_system_timezone: Europe/Moscow
```

#### Set provision hosts

```ini
  # hosts

  [provision]
  # Set you hosts
  0.0.0.0
```

#### Run provision

```bash
  $ ansible-playbook playbook.yml -i hosts -vvv
```
