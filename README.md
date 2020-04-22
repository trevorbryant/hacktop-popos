# ansible-playbooks
Ansible playbooks to setup initial configurations, install various utilities, and security tools to localhost.

## Playbooks
I needed something to install tools quickly after a new fresh OS install.

This branch is tailored for the focal releases of Ubuntu 20.04. Originally, I was updating for non-LTS releases. Going forward this will be tailored for _only_ the LTS releases.

## Testing
This has been tested on focal 20.04 and is expected to work on other distributions using `apt`.

### Dependencies
Packages to be installed prior to running the playbooks.

```bash
$ apt update && apt -y install python-apt ansible
```

Optionally, many of these tools can be installed by the `forensics-all` package described in [Debian Forensics Environment - essential components](https://packages.debian.org/sid/forensics-all).

### Examples
Perform a dry run:

```bash
$ sudo ansible-playbook desktop.yml --check
```

List tasks or tags:
```bash
$ sudo ansible-playbook desktop.yml --list-tasks
```

Install or skip specific tasks:
```bash
$ sudo ansible-playbook desktop.yml --tags "web,crack"
$ sudo ansible-playbook desktop.yml --skip-tags "chats,kubectl"
```

Run playbook and all install tools to localhost:

```bash
$ sudo ansible-playbook desktop.yml
```
