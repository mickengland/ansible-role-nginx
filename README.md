# Ansible Role: Nginx

This repo is forked from the one authored by [Jeff Geerling](http://jeffgeerling.com/), author of [Ansible for DevOps](http://ansiblefordevops.com/).

I forked this repository as part of a broader project to develop a full-stack playbook for a three tier web application on nginx, tomcat and MySql.

I am testing this stack in Vagrant with multiple tomcat instances behind Nginx. While Jeff's code had configuration place holders for LB configuration, this was not dynamic. I need to be able to look up the IPs of the app servers and use those in the backend configuration. I did this by moving the LB configuration to a template and using fact lookups from the group directive in the inventory file.

Jeff's original also had a place holder in defaults/main.yml to code a virtual host. I chose to modify this to just use a template file for the virtual host as well.

I also modified the handlers to work with Fedora 22 which now uses dnf in place of yum. At the same time I chose to use the official Fedora repositories rather than those provided by nginx.

Jeff's original README can be found [here](https://github.com/mickengland/ansible-role-nginx/blob/AddLB/README-ORIGINAL.md). It contains lots of useful configuration information and should be referenced if you are using this module. 

This version has been tested on Ubuntu 10.14.04 and Fedora 22 systems.
 
