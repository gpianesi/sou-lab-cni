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

> [!NOTE]
> To access Grafana and Prometheus through HAProxy via a web browser, you need to configure the `/etc/hosts` file on your host. This will map the DNS names `grafana.local` and `prometheus.local` to the IP address of the `soufe1` host (192.168.55.20).

Add the following at the bottom of `/etc/hosts` to configure DNS names:

```
192.168.55.20 grafana.local 
192.168.55.20 prometheus.local
```

You can then reach Grafana at https://grafana.local:8443 and Prometheus at https://prometheus.local:8443.
