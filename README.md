# 🛠️ Ansible Roles Collection — by Anar Abbasov

This repository contains my personal collection of **Ansible roles** used to automate the systems, tools, and development environments I work with.  
These roles reflect my interests in **Linux**, **automation**, **Python/Django**, and **embedded systems** (PIC, Atmel, ESP32).

The goal of this collection is to provide clean, modular, and reusable automation for both development and deployment workflows.

---

## 📦 Included Roles

This repository may include roles for:

- System setup & configuration  
- Python/Django environment provisioning  
- SQLite and lightweight database setup  
- Embedded development tools (PIC, Atmel Studio, ESP32)  
- Automation utilities  
- Developer workstation setup  
- Web server & service configuration  

Each role is:

- **Idempotent**  
- **Modular**  
- **Easy to customize**  
- **Documented with defaults and examples**  

---

## 📁 Repository Structure

ansible-roles/
├── roles/
│   ├── <role_name>/
│   ├── <role_name>/
│   └── ...
├── inventory/
│   └── hosts
├── playbooks/
│   └── example.yml
└── README.md


---

## 🚀 Getting Started

### Clone the repository

```bash
git clone https://github.com/AnarAbbasov/ansible-roles.git
cd ansible-roles

## 🚀 Use Role in playbook

- hosts: all
  become: yes
  roles:
    - role: <role_name>
⚙️ Requirements
Ansible 2.9+

Linux host (Ubuntu, Debian, CentOS, etc.)

SSH access to managed nodes

Some roles may require:

Python

Git

Systemd

Development tools (PIC/Atmel/ESP32 toolchains)
