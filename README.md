# Home Server automated deployment using Ansible and Docker

## Initial Goals:
- [x] Reverse Proxy using SWAG or NPM (Nginx Proxy Manager)
- [ ] Auth using Authella (or similiar)
- [ ] Access to static webpage (i.e. blog, services dashboard)
- [ ] Access to FoundryVTT (with auth)
- [ ] Media services (Radarr, Deluge, Plex etc)
- [ ] Setup of Pihole and PiVPN (or straight wireguard impl?)
- [ ] Ability for seamless interaction between localhost + remote connections
- [ ] Backup scripts implemented in Ansible (photos, Foundry data, configs etc)
- [ ] NextCloud self-hosting (my own gdrive?)

Development of Ansible playbooks + Docker files will be done using Vagrant + VirtualBox.
This allows for rapid prototyping of fresh Ubuntu installs without having to reflash Raspberry Pi.
Ideally, this will be deployed when stable and will *just work*.

## Setup and use for local development
### Dependencies
#### Ansible
Ansible is software that allows simple and readable configuration and management of multiple servers, from a single one to even thousands.
It is used in this project to automatically deploy a "finished" server onto a Virtual Machine (VM). With the end goal of being able to automatically setup a Raspberry Pi 4 with Ubuntu Server and the above services.

To install follow the instructions for your OS: https://www.ansible.com/

Thanks to Jeff Geerling (@geerlingguy) for his videos and book; Ansible for DevOps (https://www.ansiblefordevops.com/) for inspiration for this project.

#### Vagrant & VirtualBox
This project uses Vagrant (https://www.vagrantup.com/) and VirtualBox (https://www.virtualbox.org/) for (VM) provisioning and use. 
Vagrant is useful in this use case as Ansible can be used as it's provisioner, automatically creating the VM with the given playbook(s).

Ensure that both Vagrant and VirtualBox are installed for your OS.

### Usage
- Modify the variables within `vars.yml` file as appropriate.
- Execute `ansible-galaxy install -r requirements.yml` to install the docker plugin.
- Execute `vagrant up` to download, startup and provision a new VM.
- Visit `127.0.0.1:8080` in your browser to explore the available services (this port can be configured in the `Vagrantfile`
- `vagrant ssh` allows for ssh'ing into the VM directly.
