# ansible-playbooks-security
Ansible playbooks to install various security tools to localhost.

## Playbooks
In the beginning the idea was to create a set of roles to perform various tasks. To keep it simple, this has been scaled back to utilize the loop feature in Playbooks, and tasks for what actually needs to be tasked with greater detailed arguments. This keeps the simplicity of hierarchy. The breakdown of the Playbooks are as followed:

  - `playbook_apt_bionic.yml`: Tasks the packages that are already available in Ubuntu's repostiory from a clean installation.
  - `playbook_pip`: Tasks the packages that are sourced externally and can be installed using python.
  - `playbook_*`: Tasks the packages that are not satisfied in the above Playbooks.

## Testing
This has been tested on the following distributions:
  - Ubuntu 18.04.2 LTS
  - Pop!_OS 18.04 LTS

### Dependencies
The package `python-apt` will need to be present prior to running the playbooks. Ansible requires this package as a dependency to the`--check` module.

```bash
$ apt update
$ apt -y install python-apt
```

### Examples
Perform a dry run:

```bash
$ sudo ansible-playbook playbook_apt-utils.yml --check
```
Run playbook and install tools to localhost:

```bash
$ sudo ansible-playbook playbook_apt-utils.yml
```
