# 🚀 Ansible + GitHub Actions CI/CD Automation on AWS

![Ansible](https://img.shields.io/badge/Ansible-Automation-red?logo=ansible)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-CI%2FCD-blue?logo=githubactions)
![AWS](https://img.shields.io/badge/AWS-EC2-orange?logo=amazonaws)
![Ubuntu](https://img.shields.io/badge/Ubuntu-24.04-E95420?logo=ubuntu)
![License](https://img.shields.io/badge/License-MIT-green)
![EC2 Instances](screenshots/ec2-instances.png)

## 📌 Project Overview

This project demonstrates how to automate the configuration and deployment of multiple AWS EC2 instances using **Ansible** and **GitHub Actions**.

An Ansible Control Node manages two Ubuntu web servers through SSH key authentication. The infrastructure is organized using reusable Ansible roles, while GitHub Actions provides continuous integration by validating the playbooks with **ansible-lint** and triggering deployments.

This project showcases Infrastructure Automation, Configuration Management, and CI/CD practices commonly used in modern DevOps environments.

---

# 🏗️ Architecture

```
                    GitHub Repository
                           │
                     Git Push (main)
                           │
                           ▼
                  GitHub Actions Runner
                           │
                    SSH Deployment
                           │
                           ▼
                 Ansible Control Node
                           │
         ┌─────────────────┴─────────────────┐
         │                                   │
         ▼                                   ▼
    Web Server 1                        Web Server 2
      Ubuntu EC2                          Ubuntu EC2
         │                                   │
         ├── Install Nginx                   ├── Install Nginx
         ├── Configure UFW                   ├── Configure UFW
         ├── Deploy Website                  ├── Deploy Website
         └── Restart Services                └── Restart Services
```

Architecture Diagram

```
screenshots/architecture.png
```

---

# 🎯 Project Objectives

- Automate server configuration with Ansible
- Manage multiple EC2 instances from a Control Node
- Configure passwordless SSH authentication
- Organize automation using reusable Ansible Roles
- Deploy a custom web page
- Configure UFW Firewall
- Install and manage Nginx
- Validate Ansible playbooks using GitHub Actions
- Demonstrate Infrastructure as Code (IaC) best practices

---

# 🛠 Technologies Used

- AWS EC2
- Ubuntu 24.04 LTS
- Ansible
- GitHub Actions
- Git
- OpenSSH
- Nginx
- UFW Firewall
- YAML

---

# 📁 Project Structure

```
ansible-github-actions-cicd/

├── .github/
│   └── workflows/
│       └── deploy.yml
│
├── inventory/
│   └── hosts.ini
│
├── playbooks/
│   └── site.yml
│
├── roles/
│   ├── common/
│   ├── nginx/
│   ├── firewall/
│   └── webpage/
│
├── screenshots/
│
├── ansible.cfg
├── README.md
└── LICENSE
```

---

# ⚙️ Infrastructure

## Control Node

- Ubuntu 24.04
- Ansible Installed
- Git Installed
- SSH Key Authentication
- GitHub Repository

## Managed Nodes

- Ubuntu 24.04
- Nginx
- UFW Firewall
- Custom Web Page

---

# 🔐 SSH Authentication

Passwordless authentication is configured between:

```
Control Node
        │
        ├────────► Web Server 1
        │
        └────────► Web Server 2
```

This allows Ansible to manage both servers without interactive authentication.

---

# 📦 Ansible Roles

## Common

- Update package cache
- Upgrade installed packages

---

## Nginx

- Install Nginx
- Enable service
- Start service

---

## Webpage

Deploys a custom HTML page displaying:

- Hostname
- Deployment Date
- Automation Method

---

## Firewall

Configures UFW by allowing:

- SSH (22)
- HTTP (80)
- HTTPS (443)

---

# 🚀 Deployment

Clone the repository

```bash
git clone git@github.com:murphyola/ansible-github-actions-cicd.git

cd ansible-github-actions-cicd
```

Verify connectivity

```bash
ansible webservers -m ping
```

Run the playbook

```bash
ansible-playbook playbooks/site.yml
```

---

# 🔄 GitHub Actions Workflow

Whenever code is pushed to the **main** branch:

1. Checkout Repository
2. Install Ansible
3. Install ansible-lint
4. Validate Playbooks
5. SSH into the Control Node
6. Pull latest changes
7. Execute Ansible Playbook

Workflow File

```
.github/workflows/deploy.yml
```

---

# 📸 Screenshots

## AWS Infrastructure

```
screenshots/ec2-instances.png
```

---

## Ansible Ping

```
screenshots/ansible-ping.png
```

---

## Successful Playbook Execution

```
screenshots/ansible-playbook.png
```

---

## GitHub Actions

```
screenshots/github-actions-success.png
```

---

## Nginx Web Page

```
screenshots/nginx-homepage.png
```

---

## Architecture

```
screenshots/architecture.png
```

---

# 📈 Skills Demonstrated

- Infrastructure as Code
- Configuration Management
- Linux Administration
- AWS EC2
- SSH Authentication
- Git Version Control
- GitHub Actions CI/CD
- Ansible Roles
- YAML
- Web Server Automation
- Firewall Configuration
- Automation Best Practices

---

# 📚 Future Improvements

- Dynamic Inventory using AWS EC2 Plugin
- Ansible Vault for Secrets Management
- Multi-Environment Deployments
- Docker Container Deployment
- Kubernetes Integration
- Prometheus Monitoring
- Grafana Dashboards
- Slack Notifications
- Automated Rollbacks

---

# 👨‍💻 Author

**Maruf Salaudeen**

Cloud & DevOps Engineer

### Connect with Me

- LinkedIn: https://www.linkedin.com/in/maruf-salaudeen-177a3b75
- GitHub: https://github.com/murphyola

---

# ⭐ If you found this project useful

Please consider giving the repository a ⭐ on GitHub.

It helps others discover the project and supports my work as I continue building cloud and DevOps solutions.
