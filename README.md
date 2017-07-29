# ansible-bootstrap
Personal bootstrap tool for new systems to get them just right :)

## Usage

```
cp inventory/example.inventory inventory/local.inventory
vim inventory/local.inventory
ansible-playbook -v -i inventory/local.inventory site.yml
```

## Extend

[TODO]: eventually will be able to add includes and galaxy roles
