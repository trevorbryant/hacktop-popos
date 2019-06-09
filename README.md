# ansible-playbooks
Ansible playbooks to setup initial configurations, install various utilities, and security tools to localhost.

## Playbooks
In the beginning the idea was to create a set of roles to perform various tasks. To keep it simple, this has been scaled back to utilize the loop feature in Playbooks, and specific plays and tasks for what actually needs to be tasked with greater detailed arguments. This keeps the simplicity of hierarchy.

This branch is tailored for the disco releases of Ubuntu.

## Testing
This has been tested on disco 19.04.

### Dependencies
Packages to be installed prior to running the playbooks.

```bash
$ apt update
$ apt -y install python-apt ansible
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
$ sudo ansible-playbook play_apt.yml --tags "deb-utils,pip3-sec"
$ sudo ansible-playbook play_apt.yml --skip-tags "deb-sec,pip-sec"
```

Run playbook and all install tools to localhost:

```bash
$ sudo ansible-playbook playbook_apt.yml
```
