# Ansible Jenkins Installation

This Ansible playbook installs and configures Jenkins on a CentOS machine. 

## Usage

1. Clone this repository: 
git clone https://github.com/utrains/ansible-playbooks-roles.git



2. Edit the `vars.yml` file with your desired configuration.

3. Run the playbook with the following command:
```
ansible-playbook  main.yml
```


## Playbook Steps

This playbook performs the following tasks:

1. Downloads the Long Term Jenkins release.
2. Imports the Jenkins key from URL.
3. Performs a yum update.
4. Installs Java.
5. Installs Jenkins.
6. Reloads the daemon to pick up config changes.
7. Starts Jenkins.
8. Starts the firewalld service.
9. Allows incoming traffic on port 8080.
10. Displays the contents of the Jenkins initial admin password.

## Configuration

The following variables can be set in the `vars.yml` file:

- `jenkins_host`: The host where Jenkins will be installed.
- `jenkins_remote_user`: The remote user to be used to connect to the host.
- `jenkins_become_user`: The user to become after connecting to the host.
- `jenkins_key_url`: The URL of the Jenkins key to import.


