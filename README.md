# ansible-playbooks-security
Ansible playbooks to install various security tools to localhost.

This has been tested on the following distributions:
  - Ubuntu 18.04.2 LTS
  - Pop!_OS 18.04 LTS

# Dependencies
The package `python-apt` will need to be present prior to running the playbooks. Ansible requires this package as a dependency to the`--check` module.

```bash
$ apt update
$ apt -y install python-apt
```

## Examples
Perform a dry run:

```bash
$ sudo ansible-playbook playbooks/playbook_apt_bionic.yml --check
```
Run playbook and install tools to localhost:

```bash
$ sudo ansible-playbook playbooks/playbook_apt_bionic.yml
```
