# Ansible Role: timesync

![Ansible](https://img.shields.io/badge/ansible-ready-blue.svg)
![Platform](https://img.shields.io/badge/platform-Ubuntu-lightgrey)
![License](https://img.shields.io/badge/license-Unlicense-green)

## Description

Configures system time synchronization via `systemd-timesyncd` with NTP server.

## Variables

| Variable | Default | Description |
|---|---|---|
| `timesync_time_server` | `pool.ntp.org` | NTP server address used for time synchronization |

## Installation

Include via a `requirements.yml` and install with `ansible-galaxy`:

```yaml
# requirements.yml
roles:
  - name: timesync
    src: git+ssh://git@github.com/bergmann-max/ansible_role_timesync.git
    version: main
    scm: git
```

```bash
ansible-galaxy install -r requirements.yml
```

## Example Playbook

```yaml
- name: Configure NTP time synchronization
  hosts: all
  become: true

  roles:
    - role: timesync
      vars:
        timesync_time_server: "pool.ntp.org"
```

## Handlers

| Handler | Triggered by | Description |
|---|---|---|
| `Restart timesyncd` | `lineinfile` config change | Restarts `systemd-timesyncd` via `systemd` module |

## License

Unlicense

## Author

Max Bergmann
