# ansible-playbooks-security
Ansible playbooks to install various security tools to localhost.

## Playbooks
In the beginning the idea was to create a set of roles to perform various tasks. To keep it simple, this has been scaled back to utilize the loop feature in Playbooks, and specific plays and tasks for what actually needs to be tasked with greater detailed arguments. This keeps the simplicity of hierarchy.

This branch is tailored for the disco releases of Ubuntu.

## Testing
This has been tested on disco 19.04.

### Dependencies
The package `python-apt` will need to be present prior to running the playbooks. Ansible requires this package as a dependency to the`--check` module.

```bash
$ apt update
$ apt -y install python-apt
```
Optionally, many of these tools can be installed by the `forensics-all` package described in [Debian Forensics Environment - essential components](https://packages.debian.org/sid/forensics-all).

### Examples
Perform a dry run:

```bash
$ sudo ansible-playbook playbook_apt.yml --check
```

List tasks or tags:
```bash
$ sudo ansible-playbook playbook_apt.yml --list-tasks
```

Install or skip specific tasks:
```bash
$ sudo ansible-playbook playbook_apt.yml --tags "deb-utils,pip3-sec"
$ sudo ansible-playbook playbook_apt.yml --skip-tags "deb-sec,pip-sec"
```

Run playbook and all install tools to localhost:

```bash
$ sudo ansible-playbook playbook_apt.yml
```
