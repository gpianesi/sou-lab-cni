# sou-lab-cni
---

This repository aims to create using Vagrant two vm's, 'soufe1' and 'soube2'. Once they are up the Ansible Playbook 'deploy.yml' will run, and will:

- Install `podman`  on both vm's
- Create a container running `HAProxy` on soufe1
- Create a container running `Grafana` on soube2
- Create a container running `Prometheus` on soube2

HAProxy in this case acts as a reverse proxy balancing requests to Grafana and Prometheus containers.

--- 
### **Usage**

- Clone repository
- Run `vagrant up`
