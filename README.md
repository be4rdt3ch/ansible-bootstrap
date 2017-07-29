# ansible-bootstrap
Personal bootstrap tool for new systems to get them just right :)

## Usage

```
cp inventory/example.inventory inventory/local.inventory
vim inventory/local.inventory
ansible-playbook -v -i inventory/local.inventory site.yml
```

## Extend

You can extend this role by creating a `local.yml` which includes whatever
roles and other changes you want to execute after the bootstrapping. Example
`local.yml looks like:

```
---
- hosts: nodes
  roles:
    - { role: leifmadsen.gluster-centos-ansible }
    - { role: dougbtv.kube-centos-ansible }
```

Additionally you can install more  roles into the `roles/` directory. If you
need to create a `local-requirements.yml` go ahead. Only the `site.yml` and
`requirements.yml` along with the `roles_external/` directories are managed by
the Git repo.

Go ahead and make your local changes to build up a local play without tainting
the cloned repo. In this way you can pull in your own roles, build your own
local environment, and then keep additional Git repos inside the `roles/`
directory.

Doing it this way you can gather up a large collection of
independent roles, and do local development from the comfort of your bootstrap
playbook. I find this useful for quick lab deployment successions.
