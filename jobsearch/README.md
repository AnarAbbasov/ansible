Role Name
=========

jobsearch — Deploy and manage a Podman‑based Job Search Logging Web Application.

A brief description of the role goes here.

This role automates the deployment of a lightweight CGI‑based job‑search logging application. It prepares the SQLite database, installs required packages, fetches the latest Podman Compose configuration from GitHub, configures Podman registries, and launches the application using podman-compose. It also ensures the required directory structure exists and opens the necessary firewall ports.

Requirements
------------

This role assumes:

The target system is a RHEL/Fedora/CentOS‑based distribution using dnf.

Podman is installed and functional.

Python 3 and pip3 are available (the role installs python3-pip if missing).

The host uses firewalld (the role enables port 8081/tcp).

Internet access is available to download:

Podman Compose via pip

The podman-compose.yml file from GitHub

The user running the role has privileges to:

Install packages

Modify /etc/containers/registries.conf

Start containers

Modify firewall rules

Role Variables
--------------

The following variables should be defined by the user:

home_dir
Base directory where the application will be deployed.

Example:

yaml
home_dir: /home/ansible
version_to_deploy
The Docker/Podman image tag to deploy.

Example:

yaml
version_to_deploy: "0.3.1"
Variables created or used internally:
{{home_dir}}/jobsearch/www/data — directory for SQLite DB and CGI data.

{{home_dir}}/jobsearch/podman-compose.yml — downloaded compose file.

No other variables are required.

Dependencies
------------

This role has no external Ansible Galaxy role dependencies.

However, it relies on:

Podman being installed (not installed by this role)

firewalld being present and running

Network access to GitHub and Docker Hub

Example Playbook
----------------

- hosts: jobsearch_servers
  become: yes
  vars:
    home_dir: /home/ansible
    version_to_deploy: "0.3.1"
  roles:
    - role: jobsearch

License
-------

MIT

Author Information
------------------

Created by Anar Abbasov.
For questions or improvements, feel free to reach out via GitHub.
