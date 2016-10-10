# DigitalOcean Droplet configuration with Ansible

- Buy and Launch Droplets
- Change swap settings
- Create sudo user
- Install packages
- Security tweaks

## Quick Start


* Install [Ansible 2.0](http://docs.ansible.com/ansible/intro_installation.html)

* Copy vars.yml.example to vars.yml and change the variables to your need.

* Create a new API key on the [API access page](https://cloud.digitalocean.com/api_access). Add the api_token to `vars.yml`.

* Run ``ansible-playbook -i hosts launch.yml``

## Variables

```yml
# DO API v2 settings
do_api_token: ~

# DO SSH key settings
do_ssh_name: ~
do_ssh_pub_key: "{{ lookup('file', '~/.ssh/id_rsa.pub') }}"
do_ssh_private_key: "~/.ssh/id_rsa"

# DO droplet settings
do_region: ams2
do_size: 512mb
do_image: "ubuntu-16-04-x64"

# SSH
ssh_port: 22

# UFW - Firewall settings
ufw_allow_ports:
  - 22
  - 80
  - 443

# Swap settings - https://goo.gl/vrqDqI
swapfile_location: /swapfile
swapfile_size: 4G
swapfile_swappiness: 10
swapfile_vfs_cache_pressure: 50

# System user to create
# your future ssh user for access to a new droplet
ssh_user: ~ 
ssh_groups: "sudo"
#path on host machine to public key for adding it to authorized keys
ssh_pub_key: "{{ lookup('file', '~/.ssh/id_rsa.pub') }}" 

# Run apt-get update only if the last one is more than 3600 seconds ago http://docs.ansible.com/ansible/apt_module.html
cache_valid_time: 3600
```

