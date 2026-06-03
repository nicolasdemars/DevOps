# DevOps
## 3-1 Inventory and base commands

I created a project-specific Ansible inventory in `ansible/inventories/setup.yml`.

The inventory defines:
- the remote user: `admin`
- the SSH private key: `~/.ssh/id_rsa`
- the production host: `nicolas.demars.takima.school`

Inventory content:

```yaml
all:
  vars:
    ansible_user: admin
    ansible_ssh_private_key_file: ~/.ssh/id_rsa
  children:
    prod:
      hosts:
        nicolas.demars.takima.school:

## 3-2 Playbook documentation

I refactored the Docker installation playbook by using an Ansible role.

I created the role with:

```bash
ansible-galaxy init roles/docker