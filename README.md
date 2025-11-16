# Ansible Role: unattended_upgrades

## Description

unattended-upgrade - automatic installation of security (and other) upgrades.

## Requirements

None

## Dependencies

None

## OS Platforms

- Ubuntu-20.04+

## Example Playbook

```yaml
- hosts: all
  roles:
    - unattended_upgrades
```

## Role Variables

### unattended_upgrades_package_ensure: (string)

```yaml
unattended_upgrades_package_ensure: 'present'
```

### unattended_upgrades_service_ensure: (string)

```yaml
unattended_upgrades_service_ensure: 'started'
```

### unattended_upgrades_service_enable: (bool)

```yaml
unattended_upgrades_service_enable: true
```

### unattended_upgrades_update_package_list: (string)

```yaml
unattended_upgrades_update_package_list: '1'
```

### unattended_upgrades_download_upgradable_packages: (string)

```yaml
unattended_upgrades_download_upgradable_packages: ''
```

### unattended_upgrades_autoclean_interval: (string)

```yaml
unattended_upgrades_autoclean_interval: ''
```

### unattended_upgrades_upgrade: (string)

```yaml
unattended_upgrades_upgrade: '1'
```

### unattended_upgrades_allowed_origins: (list)

```yaml
unattended_upgrades_allowed_origins:
  - '${distro_id}:${distro_codename}'
  - '${distro_id}:${distro_codename}-security'
  - '${distro_id}ESMApps:${distro_codename}-apps-security'
  - '${distro_id}ESM:${distro_codename}-infra-security'
```

### unattended_upgrades_package_blacklist: (list)

```yaml
unattended_upgrades_package_blacklist: []
```

### unattended_upgrades_devrelease: 'auto'

```yaml
unattended_upgrades_devrelease: 'auto'
```

### unattended_upgrades_autofix_interrupt_dpkg: (bool)

```yaml
unattended_upgrades_autofix_interrupt_dpkg: true
```

### unattended_upgrades_minimal_steps: (bool)

```yaml
unattended_upgrades_minimal_steps: true
```

### unattended_upgrades_install_on_shutdown: (bool)

```yaml
unattended_upgrades_install_on_shutdown: false
```

### unattended_upgrades_mailto: (string)

```yaml
unattended_upgrades_mailto: ''
```

### unattended_upgrades_mailreport: (string)

```yaml
unattended_upgrades_mailreport: ''
```

### unattended_upgrades_remove_unused_kernel: (bool)

```yaml
unattended_upgrades_remove_unused_kernel: true
```

### unattended_upgrades_remove_new_unused_dependencies: (bool)

```yaml
unattended_upgrades_remove_new_unused_dependencies: true
```

### unattended_upgrades_remove_unused_dependencies: (bool)

```yaml
unattended_upgrades_remove_unused_dependencies: false
```

### unattended_upgrades_automatic_reboot: (bool)

```yaml
unattended_upgrades_automatic_reboot: false
```

### unattended_upgrades_automatic_reboot_withuser: (bool)

```yaml
unattended_upgrades_automatic_reboot_withuser: true
```

### unattended_upgrades_automatic_reboot_time: (string)

```yaml
unattended_upgrades_automatic_reboot_time: "now"
```

### unattended_upgrades_download_limit: (bool)

```yaml
unattended_upgrades_download_limit: false
```

### unattended_upgrades_download_limit_value: (string)

```yaml
unattended_upgrades_download_limit_value: '70'
```

### unattended_upgrades_syslog_enable: (bool)

```yaml
unattended_upgrades_syslog_enable: false
```

### unattended_upgrades_syslog_facility: (string)

```yaml
unattended_upgrades_syslog_facility: 'daemon'
```

### unattended_upgrades_only_acpower: (bool)

```yaml
unattended_upgrades_only_acpower: true
```

### unattended_upgrades_skip_nonmeterd_connection: (bool)

```yaml
unattended_upgrades_skip_nonmeterd_connection: true
```

### unattended_upgrades_verbose: (bool)

```yaml
unattended_upgrades_verbose: false
```

### unattended_upgrades_debug: (bool)

```yaml
unattended_upgrades_debug: false
```

### unattended_upgrades_allow_downgrade: (bool)

```yaml
unattended_upgrades_allow_downgrade: false
```

### unattended_upgrades_append_config: (list)

```yaml
unattended_upgrades_append_config: []
```

## Example vars

```yaml
unattended_upgrades_periodic_enable: '0'
unattended_upgrades_upgrade: '0'
unattended_upgrades_update_package_list: '0'
unattended_upgrades_download_upgradable_packages: '0'
unattended_upgrades_autoclean_interval: '0'
unattended_upgrades_package_blacklist:
  - 'linux-headers*'
  - 'linux-image*'
  - 'linux-generic*'
  - 'linux-modules*'
  - 'docker.io'
unattended_upgrades_append_config:
  - name: 20auto-upgrades
    config: |
      APT::Periodic::Verbose "2";
  - name: 50unattended-upgrades
    config: |
      Unattended-Upgrade::Mail-Only-On-Error "true";
```
