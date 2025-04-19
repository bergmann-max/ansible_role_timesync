# Ansible Role: ansible_role_ntp_simple

![Ansible](https://img.shields.io/badge/ansible-ready-blue.svg)
![Platform](https://img.shields.io/badge/platform-Ubuntu-lightgrey)
![License](https://img.shields.io/badge/license-Unlicense-green)

## Description

This Ansible role configures the system's time synchronization service to use a specific NTP server.  
It is designed to provide a lightweight and portable time sync setup using `systemd-timesyncd`, which is available on most modern Ubuntu systems.

### Features:
- Sets a custom NTP server (default: `pool.ntp.org`)
- Ensures `systemd-timesyncd` is active and enabled
- Compatible with minimal and containerized Ubuntu systems

## Role Variables

The following variable can be set (see `defaults/main.yml`):

| Variable     | Default         | Description |
|--------------|-----------------|-------------|
| `time_server` | `pool.ntp.org` | The NTP server address used for time synchronization |

## Usage Example

```yaml
- name: Configure NTP time synchronization
  hosts: all
  become: true
  roles:
    - role: ansible_role_ntp_simple
```

## Sanity Checks

This role ensures:
- `systemd-timesyncd` is properly configured
- The service is enabled and started
- The specified NTP server is used for synchronization

## Directory Structure

Follows standard Ansible role layout:

```
ansible_role_ntp_simple/
├── defaults/
│   └── main.yml
├── tasks/
│   └── main.yml
├── handlers/
│   └── main.yml
├── meta/
│   └── main.yml
└── README.md
```

✔️ Designed for minimal NTP configuration on Ubuntu-based systems.

## License

Unlicense

## Author Information

Role maintained by Max Bergmann.  
Feedback, suggestions, and contributions are always welcome! 🚀
