# ansible-playbooks-security
Ansible playbooks to install various security tools to localhost.

## Examples
Perform a dry run:

```bash
$ sudo ansible-playbook playbooks/playbook_apt_bionic.yml --check
```
Run playbook and install tools to localhost:

```bash
$ sudo ansible-playbook playbooks/playbook_apt_bionic.yml
```
