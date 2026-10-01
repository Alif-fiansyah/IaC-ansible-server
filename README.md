# Iac-ansible-server

An automated **Infrastructure as Code (IaC)** project built using **Ansible** to provision, configure, and secure Linux servers (optimized for **Arch Linux** & **Debian/Ubuntu**) effortlessly from a single control node.

## Key Features
- **Idempotent Automation**: Safely run playbooks repeatedly without breaking existing system configurations.
- **Automated Security Tools**: Instantly installs and configures **UFW Firewall** and **Fail2Ban** to protect against unauthorized access and brute-force attacks.
- **SSH Hardening**: Automatically secures remote access by disabling direct root logins (`PermitRootLogin no`).
- **Service Management**: Ensures essential security daemons are enabled and running via `systemd`.
- **Multi-Distro Support**: Tailored tasks that adapt automatically depending on the target system package manager (`pacman` or `apt`).

---

## 📂 Project Structure
```text
ansible-server-bootstrap/
├── inventory/
│   └── hosts.ini       # Defines target servers / hosts
├── playbook.yml        # Main automation tasks & handlers
└── README.md           # Project documentation
```

### Getting Started & Usage
### 1. Prerequisites
### Arch Linux:
   ```bash
   sudo pacman -S ansible
```
### Debian / Ubuntu:
```bash
sudo apt update && sudo apt install ansible -y
```

### 2. Configure the Inventory
Edit the `inventory/hosts.ini` file to add your target server IP addresses or hostnames. For local testing, use:
```bash
[servers]
localhost ansible_connection=local
```
### 3.Run the Playbook
Execute the Ansible playbook with elevated privileges:
```bash
sudo ansible-playbook -i inventory/hosts.ini playbook.yml
```
---

## Tech Stack

- **Language:** YAML, Jinja2 (Ansible Playbooks)
- **Os Target:** Arch Linux, Debian, Ubuntu
- **Engine:** Ansible Core
- **Security Tools:** UFW, Fail2Ban, OpenSSH

## Why Ansible?

Instead of manually logging into multiple servers via SSH to run shell commands one by one, Ansible allows administrators to manage and secure tens or hundreds of servers simultaneously using clean, version-controlled configuration templates.



