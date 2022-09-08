# vagrant-ansible

Simple box to learn Ansible. This box adds your sshkeys to the *vagrant* user in the box so you don't have to do it yourself.

This box will have IP address **192.168.168.168**.

# Get started

```
vagrant up
```

# Run a playbook

```
ansible-playbook playbook.yml
```

# Using a specific **inventory** file

The default inventory file is **.vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory**. You can create your own inventory file and pass it to Ansible with the -i switch.

Suppose you want to run a playbook on a group **foogroup**, you need to add the **vagrant** host to that group in the inventory file.

Edit **inventory** file and add a group like below

```
[foogroup]
vagrant
```

Then run the playbook.yml with the specified **inventory** file.

```
ansible-playbook -i inventory playbook.yml --limit vagrant
```
