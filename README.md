# desktop
Ansible playbook to setup initial configurations, install various utilities, and security tools to localhost.

## Testing
This has been built and tested for [Pop!_OS 20.04](https://pop.system76.com/). This playbook _can_ work on other Debian-based distributions. Expect failures when repositories aren't present.

### Dependencies
Install the `ansible` package prior to running the playbook.

```bash
$ apt -y install ansible
```

### Running playbook
The `preflight` role will check if the `user` and `hostname` variables are defined. If not, the playbook will fail and ask you to populate the variables. These can be found in `preflight/defaults/main.yml`.

Perform a dry run:
```bash
$ sudo ansible-playbook install.yml --check
```

List tasks or tags:
```bash
$ ansible-playbook install.yml --list-tasks
$ ansible-playbook install.yml --list-tags
```

Install or skip specific tags (or tasks):
```bash
$ ansible-playbook install.yml --tags "web,crack" -K
$ ansible-playbook install.yml --skip-tags "social,wireless" -K
```

Run playbook and all install tools to localhost:

```bash
$ ansible-playbook install.yml -K
```
