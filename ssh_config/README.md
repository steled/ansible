# SSH config and user deploy Playbook
## file: users.yml
- configuration file for users inclusive ssh key to be added

## file: server
- defined server for playbook

## file: local_init.yml
- create users from *users.yml* locally
- add users to sudoers
- add ssh keys
- set ssh configuration
    - enable ssh AuthorizedKeysFile
    - enable ssh PubkeyAuthentication
    - disable ssh PasswordAuthentication
    - enable ssh PasswordAuthentication for user deploy
    - disable ssh UsePAM
    - disable ssh PermitEmptyPasswords
    - disable ssh PermitRootLogin

## file: deploy_ssh.vml
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