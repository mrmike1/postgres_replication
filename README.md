
This playbook uses apt to install postgresql and setup master and slave replication

Ran with
ansible-playbook postgres_playbook.yaml --ask-pass --ask-become-pass

Tested with Debian debian-8.3.0

setup your /etc/ansible/hosts file with postgres slaves in the group pslaves and master in group pmasters

[pmasters]
192.168.1.192 ansible_user=postgres ansible_connection=ssh

[pslaves]
192.168.1.191 ansible_user=postgres ansible_connection=ssh
192.168.1.151 ansible_user=postgres ansible_connection=ssh

edit includes/vars.yaml with database user, password , version etc
