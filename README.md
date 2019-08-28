# ansible playbooks to manage jail hosts and jails

### create and start jail j003

```
ansible-playbook -i inventories/staging -K create-insecure-jail.yml --extra-vars="JAIL_NAME=j003"
```

### bootstrap python and secure ssh connection for jail j003

```
ansible-playbook -i inventories/staging -K bootstrap-insecure-jails.yml --limit="{jails_host_hostname}-j003"
```

### stop and remove jail j003

```
ansible-playbook -i inventories/staging -K remove-jail.yml --extra-vars="JAIL_NAME=j003" --limit="{jails_host_hostname}"
```
