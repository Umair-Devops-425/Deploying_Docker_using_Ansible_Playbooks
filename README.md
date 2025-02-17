# Docker Installation on Multiple Servers using Ansible

This project demonstrates how to install Docker on multiple servers using An Ansible playbook. The playbook is executed from an EC2 instance, targeting multiple remote servers.

## Prerequisites

1. **Ansible Installed**: The EC2 instance from which you are running the playbook should have Ansible installed.
2. **SSH Access**: Ensure you have SSH access to the target servers from the EC2 instance.
3. **Inventory File**: An inventory file containing the IP addresses or hostnames of the target servers.
4. **Python**: Ensure Python is installed on the target servers, as Ansible requires it to execute tasks.
5. **Inventory**: Contains the list of target servers.
6. **Playbook.yml**: The main playbook that includes the roles and tasks.

## Inventory 

The `inventory` file should list the IP addresses or hostnames of the target servers.

```
nano hosts
```

![A2](/Images/images2.png)

List all servers

```
ansible-inventory --list -y -i /home/ubuntu/ansible/hosts
```

Testing all servers

```
ansible all ping -i /home/ubuntu/ansible/hosts/ --private-key=~/.ssh/ansible_key
```

## Playbook

The `docker_create.yml` file is the main playbook that includes the roles and tasks.

![A1](/Images/image.png)

## Running the Playbook

To run the playbook, use the following command:

```
ansible-playbook docker_create.yml -i /home/ubuntu/ansible/hosts --private-key=~/.ssh/ansible_key
```

![A2](/Images/images3.png)