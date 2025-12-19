# Ansible Server Automation

[![Ansible](https://img.shields.io/badge/Ansible-2.15+-EE0000?logo=ansible)](https://www.ansible.com/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

Production-ready Ansible playbooks and roles for server provisioning, configuration management, and automation. Built from real-world experience managing 50+ nodes.

## Features

- Server hardening and security baseline
- Docker and Kubernetes installation
- Prometheus node exporter and monitoring setup
- SSH key management and access controls
- Automated package updates and patching
- Idempotent and well-tested roles

## Roles

| Role | Description |
|------|-------------|
| common | Base packages, users, timezone, NTP |
| security | SSH hardening, firewall, fail2ban |
| docker | Docker CE installation and configuration |
| kubernetes | K3s/kubeadm installation |
| monitoring | Node exporter, promtail setup |

## Quick Start

```bash
# Install dependencies
ansible-galaxy install -r requirements.yml

# Test connectivity
ansible all -i inventory/hosts.yml -m ping

# Run full provisioning
ansible-playbook -i inventory/hosts.yml playbooks/site.yml

# Run specific role
ansible-playbook -i inventory/hosts.yml playbooks/site.yml --tags security
```

## Directory Structure

```
├── ansible.cfg              # Ansible configuration
├── inventory/
│   └── hosts.yml            # Inventory file
├── group_vars/
│   └── all.yml              # Global variables
├── playbooks/
│   ├── site.yml             # Main playbook
│   ├── security.yml         # Security hardening
│   └── docker.yml           # Docker setup
└── roles/
    ├── common/              # Base configuration
    ├── security/            # Security hardening
    ├── docker/              # Docker installation
    ├── kubernetes/          # K8s setup
    └── monitoring/          # Monitoring agents
```

## Testing

```bash
# Syntax check
ansible-playbook playbooks/site.yml --syntax-check

# Dry run
ansible-playbook -i inventory/hosts.yml playbooks/site.yml --check

# Run on localhost
ansible-playbook -i "localhost," -c local playbooks/site.yml
```

## Author

Ashwath Abraham Stephen
Senior DevOps Engineer | [LinkedIn](https://linkedin.com/in/ashwathstephen) | [GitHub](https://github.com/ashwathstephen)

## License

MIT License - see [LICENSE](LICENSE) for details.

