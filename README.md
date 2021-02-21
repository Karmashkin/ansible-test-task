# Ansible container

examples location:
```
cp /usr/share/doc/ansible-base/examples/* /etc/ansible/

```

inside container first steps:
```
ssh-keygen
ssh-copy-id root@<IP> -p 22
```

generate new root and other password:
```
</dev/urandom tr -dc 'A-Za-z0-9' | head -c32; echo ""
```

get hash of new root and other users passwords
```
openssl passwd -1 "password"
```
and edit sshd playbook.


start playbook on a new hosts group
```
ANSIBLE_HOST_KEY_CHECKING=False ansible -m ping testvms
ansible -m shell -a 'python -V' testvms

```

# howto
1. set vars
```
playbooks/php-nginx-mysql-redis/group_vars/all
```
2. then run
```
ansible-playbook playbooks/php-nginx-mysql-redis/install-packages.yml --extra-vars "target=testvms"

```

tested on:
- centos 7
- debian 10

