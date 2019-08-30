# ansible playbooks to manage jail hosts and jails

### configure jail hosts

```
ansible-playbook -i inventories/staging jail_hosts.yml --limit="{jails_host_hostname}"
```

### create and start jail j003

```
ansible-playbook -i inventories/staging -K jail_create_insecure.yml --extra-vars="JAIL_NAME=j003" --limit="{jails_host_hostname}"
```

### bootstrap python and secure ssh connection for jail {jail_name}

```
ansible-playbook -i inventories/staging jail_bootstrap_insecure.yml --limit="{jails_host_hostname}-{jail_name}"
```

### stop and remove jail {jail_name}

```
ansible-playbook -i inventories/staging -K jail_remove.yml --extra-vars="JAIL_NAME=j003" --limit="{jails_host_hostname}-{jail_name}"
```

### install basic packages like mc, oh-my-zsh and vim in jail {jail_name}

```
ansible-playbook -i inventories/staging jails.yml --limit="{jails_host_hostname}-{jail_name}"
```

### install and configure webserver with apache24, php73 {jail_name}

```
ansible-playbook -i inventories/staging web_apache24_php73.yml --limit="{jails_host_hostname}-{jail_name}"
```

### install and configure webserver with nginx, php73 {jail_name}

```
ansible-playbook -i inventories/staging web_nginx_php73.yml --limit="{jails_host_hostname}-{jail_name}"
```
