# DigitalOcean Droplet configuration with Ansible

- Buy and Launch Droplets
- Change swap settings
- Create sudo user
- Install packages
- Security tweaks

## Installation


* Install [Ansible 2.0](http://docs.ansible.com/ansible/intro_installation.html)

* Copy vars.yml.example to vars.yml and change the variables to your need.

## Digital Ocean configuration

Create a new API key on the [API access page](https://cloud.digitalocean.com/api_access). 
Add the api_token to `vars.yml`.

![image](https://cloud.githubusercontent.com/assets/2697570/19223963/74bd206e-8e73-11e6-83cb-b0f2192c6d5e.png)
