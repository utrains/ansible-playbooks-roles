# Creating New Users with Passwords on CentOS Servers

This Ansible playbook is used to create new users with passwords on CentOS servers, and force the users to change their passwords on first login.

## Prerequisites

Before you can use this playbook, you must have the following:

- Ansible installed on your local machine or control node
- Access to one or more CentOS servers that you want to create new users on

## Usage

To use this playbook, follow these steps:

1. Clone or download the playbook to your local machine or control node.
2. Edit the `users.yml` file to specify the usernames and passwords for the new users that you want to create. Each user should be defined as a dictionary with `username` and `password` keys.
3. Edit the `vars.yml` file to specify the  host group of the CentOS servers that you want to create the new users on.
4. Run the playbook using the following command:

ansible-playbook -i hosts.yml main.yml



The playbook will run and create the new users with the specified passwords on the CentOS servers. The users will also be forced to change their passwords on first login.

## Playbook Details

The playbook consists of two tasks:

1. Create user accounts: This task uses the `user` module to create new user accounts on the CentOS servers. The `name` and `password` parameters are set based on the values defined in the `users.yml` file. The `createhome` parameter is set to `yes` to create a home directory for each user, and the `shell` parameter is set to `/bin/bash`.
2. Force users to change password on first login: This task uses the `command` module to run the `chage` command, which sets the last password change date to the epoch (0) for each user, forcing them to change their password on first login.

## Authors

This playbook was created by Utrains. If you have any questions or suggestions, please contact me at contact@utrians.org.



