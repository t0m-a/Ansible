# Ansible Playbooks files

----
## Web Servers Cluster Environment for Development

## Warning
These Ansible & Vagrant repositories are meant for **Development** (& Staging) only. Right now, I don't have any plan on building these for Production. Though I've built provisioning and configurations as secured and robust as I can, I would have included different parameters and security measures for Production environments, including real security tests.

## Description
See my [Vagrantfiles/WebServersCluster (GitHub)](https://github.com/t0m-a/Vagrantfiles/tree/master/WebServerCluster)

This Vagrantfile repository will provision virtual machines to create a web infrastructure containing:

- One load balancer using Nginx.
- Two front-end web servers using Nginx.
- Two back end MySQL database servers, Master & Slave.

----
## Content
### Roles
The "WebServerCluster\_Dev" directory contains roles divided into different directories named after the roles they contain.

It also contains the Master Playbook called *site.yml*.

This file references the Tiers Playbooks for each roles:

 - common.yml
 - loadbalancer.yml
 - webservers.yml
 - dbservers.yml

----
### Modules
Each roles contains the modules they will need to be included and configured:

- files/ - If files need to be included in server's FS
- handlers/ - How we'll handle service's actions
- hosts - The hosts file containing the IP addresses of the members of the cluster by group, as defined while provisioning
- tasks/ - Installation, enable at boot, import the configuration file(s)
- templates/ - Configurations files, virtual hosts, etc..
- vars/ - pid, user running the service, service's variables

----
## changelog
* 2019-11-29 README.md added, Work in progress