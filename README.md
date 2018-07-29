# Arch Discourse Ansible Playbook

## Client Requirements

- Python 3.5 or above
- [Pipenv](https://github.com/pypa/pipenv)

## Server Requirements

- Ubuntu 14.04 or above (or [what Docker supports](https://docs.docker.com/install/linux/docker-ce/ubuntu/#os-requirements))
- x86_64

## Run

- Save `vault_password` file with the vault password if you have not.

```shell
$ pipenv run \
    ansible-playbook site.yml \
    -i hosts \
    -u $USER \
    --vault-id vault_password
```
