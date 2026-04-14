Role Name
=========

The jobsearch_remove role cleanly undeploys the JobSearch application that was previously deployed using Podman Compose.
It performs a full teardown of the service, including:

Closing firewall ports

Disabling optional HTTP service access

Stopping the Podman Compose stack (if present)

Removing the compose file

Cleaning up deployment artifacts

This role is idempotent — running it multiple times is safe.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------



Variable	Description	                                             Default
home_dir	Base directory where the JobSearch service was deployed	/home/ansible
disable_http	Whether to disable the http firewalld service	      false



Example Playbook
----------------

- hosts: all
  become: yes
  roles:
    - role: jobsearch_remove
      vars:
        home_dir: /home/ansible
        disable_http: true




License
-------

MIT

Author Information
------------------

Anar Abbasov
