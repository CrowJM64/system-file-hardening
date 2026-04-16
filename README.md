# Ansible Role for System File Hardening
**Author/Maintainer:** Josh Murphy

## Overview

This Ansible role automates hardening of the following system files and directories:
```yaml
- /boot (700)
- /etc/cron.monthly (700)
- /etc/cron.weekly (700)
- /etc/cron.daily (700)
- /etc/cron.hourly (700)
- /etc/crontab (600)
- /etc/ssh/sshd_config (600)
- /etc/passwd (644)
- /etc/group (644)
- /etc/shadow (640)
- /etc/gshadow (640)
- /home (755)
- /home/* (700)
- /tmp (1777 - Sticky Bit) 
- /var/tmp (1777 - Sticky Bit)
- /run/shm (tmpfs defaults,noexec,nosuid)
- /dev/shm (tmpfs defaults,noexec,nosuid,nodev)
```

## Supported Platforms and Derivatives
The files changed should exist on every Redhat and Debian Distro. Below are the explicitly tested Distros.
```yaml
# RedHat
Rocky 10/9
CentOS 10/9
Fedora 43/42
Oracle 10

# Debian
Ubuntu 24.04/22.04
Debian 13
Alma 10
Mint 22
```

## Example Playbook

```yaml
- hosts: all
  become: yes

  roles:
    - role: system_file_hardening
```

### From Ansible Galaxy

```bash
ansible-galaxy install crowjm64.system_file_hardening
```

This role was created and is maintained by **[CrowJM64](https://github.com/CrowJM64)**.