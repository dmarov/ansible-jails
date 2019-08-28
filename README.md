# ansible playbooks to manage jail hosts and jails

create and start jail j003

```
ansible-playbook -i inventories/staging -K create-insecure-jail.yml --extra-vars="JAIL_NAME=j003"
```

remove jail j003

```
ansible-playbook -i inventories/staging -K remove-jail.yml --extra-vars="JAIL_NAME=j003"
```
