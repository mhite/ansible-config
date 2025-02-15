# Laptop Configuration with Ansible

This repository contains Ansible playbooks for managing work and home laptops.

## Prerequisites

### For macOS

1. Install Homebrew:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

2. Ensure Homebrew is in your PATH:
```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zshrc
source ~/.zshrc
```

3. Install Ansible via Homebrew:
```bash
brew install ansible
```

4. Get rid of sudo_lecture
```bash
sudo ls
```

## Usage

For work laptop:
```bash
ansible-playbook playbooks/work_laptop.yml --limit work-laptop-1 -v -K
```

For home laptop:
```bash
ansible-playbook playbooks/home_laptop.yml --limit mattirl -v -K
```

## Structure

- `group_vars/`: Variables for different types of systems
  - `all.yml`: Common settings for all systems
  - `work_laptops.yml`: Work-specific settings
  - `home_laptops.yml`: Home-specific settings
- `roles/`: Ansible roles
  - `base/`: Common to all systems
  - `laptop_common/`: Shared laptop configurations
  - `work_laptop/`: Work-specific configurations
  - `home_laptop/`: Home-specific configurations
- `playbooks/`: Ansible playbooks
  - `work_laptop.yml`: Setup for work laptops
  - `home_laptop.yml`: Setup for home laptops
