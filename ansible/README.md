# Ansible alpine dockerized

```sh
UID_GID="$(id -u):$(id -g)" docker-compose run --rm ansible sh
UID_GID="$(id -u):$(id -g)" docker-compose up -d
```

## Generate ssh key

Generate a SSH key for the managed node. It's recommended to use a key which is protected with a password.

```sh
ssh-keygen -t ed25519
```

## Transfer the SSH key
There are two ways to do it. From a default Alpine installation you can use ssh and cat to do it.

```sh
ssh root@[IP of the management system] 'cat ~/.ssh/id_ed25519.pub' | cat - >> ~/.ssh/authorized_keys
```

If you are planning to use additional features of SSH. ssh-copy-id, which is provided by the openssh-client package, can help you with the key setup.

```sh
ssh-copy-id -i ~/.ssh/id_ed25519.pub root@[IP of the management system]
```

```
# /etc/ansible/hosts

192.168.1.50
10.0.0.12
webserver.example.org
mail.example.org
```

## First test

```shell
ansible all -m ping -u you

# Another test is check all variables
ansible [IP of your Alpine Linux box] -m setup
```

## Playbooks
When writing playbooks for Alpine Linux there are modules to keep in mind:

1. There is support for OpenRC, the Init System, in the service module

```yaml
- service:
   name: lighttpd
   enabled: yes
   state: started
```

2. There is support for APK as of Ansible 2.0.

```yaml
- apk:
   name: lighttpd
   state: present
   update_cache: yes
```

3. There is support for the Awall firewall as of Ansible 2.4

```yaml
- awall:
   name: policyfile
   state: enabled
   activate: yes
```

4. If you are going to re-use playbooks from other Linux distribution, please keep in mind that Alpine Linux uses different paths for the binaries. `/bin/rm`
The [alpine-ansible git repository](http://git.alpinelinux.org/user/fab/alpine-ansible/) contain some example playbooks.
