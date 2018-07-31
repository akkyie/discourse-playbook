# Arch Discourse Ansible Playbook

## Client Requirements

- Python 3.7
- [Pipenv](https://github.com/pypa/pipenv)

## Server Requirements

- Ubuntu 14.04 or above (or [what Docker supports](https://docs.docker.com/install/linux/docker-ce/ubuntu/#os-requirements))
- [Managed node requirements of Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#managed-node-requirements): Python and SSH

## Run

- Save `vault_password` file with the vault password if you have not.

```shell
$ pipenv run \
    ansible-playbook playbook.yml \
    -i hosts \
    -u $USER \
    --vault-id vault_password
```
