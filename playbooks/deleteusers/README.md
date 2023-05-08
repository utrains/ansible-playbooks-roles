# Playbook: Delete users from CentOS servers

This Ansible playbook deletes users from one or more CentOS servers. The playbook reads a list of users to delete from a variable file, then uses the `user` module to delete each user from the server.

## Usage

1. Update the `hosts` variable in `vars.yml` with the group of servers to delete users from.

2. Update the `users` variable in `users.yml` with the list of users to delete. Each user is specified as a dictionary with a `username` key.

3. Run the playbook with the command:

```
ansible-playbook main.yml -i hosts 
```




## Note

- If a user specified in the `users` list is not present on the server, the `user` module will skip the deletion task and report a success message.

- This playbook requires sudo or root privileges to run. Use the `--ask-become
