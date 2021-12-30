# Home Server automated deployment using Ansible and Docker

Initial Goals:
- Reverse Proxy using SWAG or NPM (Nginx Proxy Manager)
- Auth using Authella (or similiar)
- Access to static webpage (i.e. blog, services dashboard)
- Access to FoundryVTT (with auth)
- Media services (Radarr, Deluge, Plex etc)
- Setup of Pihole and PiVPN (or straight wireguard impl?)
- Ability for seamless interaction between localhost + remote connections
- Backup scripts implemented in Ansible (photos, Foundry data, configs etc)

Development of Ansible playbooks + Docker files will be done using Vagrant + VirtualBox.
This allows for rapid prototyping of fresh Ubuntu installs without having to reflash Raspberry Pi.
Ideally, this will be deployed when stable and will *just work*.
