# SSH config and user deploy Playbook
- this playbook create local users with given ssh key
- set ssh configuration
- deploys locally created users to remote server

## file: users.yml
- configuration file for users
- user can be added without predefined ssh key
- user can be added with predefined ssh key
- user can be added with ssh key file

## file: server
- defined server for playbook

## file: local_init.yml
- create user from *users.yml* locally
- add user to sudoers
- add ssh key

## file: set_ssh_config.yml
- set ssh configuration
    - enable ssh AuthorizedKeysFile
    - enable ssh PubkeyAuthentication
    - disable ssh PasswordAuthentication
    - enable ssh PasswordAuthentication for user deploy
    - disable ssh UsePAM
    - disable ssh PermitEmptyPasswords
    - disable ssh PermitRootLogin

## file: deploy_ssh.yml
- deploy users from *users.yml* remotely
- add deployed users to the sudoers
- deploy ssh keys
- create central authorized_keys file
- set ssh configuration
    - enable ssh AuthorizedKeysFile
    - enable ssh PubkeyAuthentication
    - disable ssh PasswordAuthentication
    - enable ssh PasswordAuthentication for user deploy
    - disable ssh UsePAM
    - disable ssh PermitEmptyPasswords
    - disable ssh PermitRootLogin