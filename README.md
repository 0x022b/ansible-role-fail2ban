# Ansible Role: fail2ban

![Ansible Galaxy](https://github.com/0x022b/ansible-role-fail2ban/workflows/Ansible%20Galaxy/badge.svg)

Ansible role that configures fail2ban package and service.

## Requirements

None.

## Role Variables

Available variables are listed below with default values.

```yaml
fail2ban_package_state: present
```

Variable to control the state of fail2ban package.

```yaml
fail2ban_service_state: started
fail2ban_service_enabled: yes
```

Variables to control the state of fail2ban service.

```yaml
fail2ban_jail_default_bantime: 5m
fail2ban_jail_default_findtime: 1h
fail2ban_jail_default_ignoreip:
  - 127.0.0.0/8
  - 10.0.0.0/8
  - 172.16.0.0/12
  - 192.168.0.0/16
fail2ban_jail_default_maxretry: 3
```

Variables to control default jail settings.

```yaml
fail2ban_jail_sshd_enabled: yes
fail2ban_jail_sshd_filter: null
```

Variables to control sshd jail settings.

```yaml
fail2ban_jail_selinux_ssh_enabled: yes
```

Variable to control state of selinux-ssh jail.

```yaml
fail2ban_jail_recidive_enabled: yes
fail2ban_jail_recidive_bantime: 30d
fail2ban_jail_recidive_findtime: 3d
fail2ban_jail_recidive_maxretry: 5
```

Variables to control recidive jail settings.

## Dependencies

- 0x022b.epel
- 0x022b.firewalld

## Example Playbook

```yaml
- hosts: servers
  roles:
    - role: 0x022b.fail2ban
```

## License

MIT
