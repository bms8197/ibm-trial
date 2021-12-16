# Ansible roles & playbooks to deploy a new Ubuntu 20 droplet, via API then install & configure Apache2 webserver to listen on port 8080

# There are 2 roles

- digitalocean role; creates a digitalocean droplet based on some default settings and populate the inventory file in inventory/hosts after the droplet creation
- webserver role; connects to the droplet, upgrades all the packages on the server; if kernel was updated, automatically reboots the server and wait to come back online; then installs Apache2 webserver, enables the service, change the default port from 80 to 8080 and uploads a default index.html file which contains the server's hostname so it can be displayed in a browser

# How to steps:

- run the bash script prepare-ansible like this: ./prepare-ansible
- enter you DO API token; token is saved into roles/digitalocean/defaults/main.yml
- run the actual playbook: ansible-playbook playbooks/create-do-droplet.yml

