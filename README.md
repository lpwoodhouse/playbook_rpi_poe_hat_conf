![GitHub repo file count](https://img.shields.io/github/directory-file-count/lpwoodhouse/playbook_rpi_poe_hat_conf)
# Ansible Playbook: rpi_poe_hat_conf
## Part of my Raspberry Pi cluster project

## Purpose

This playbook configures the CPU temperature trip points for the Raspberry Pi PoE Hat fan.

## Requirements

community.general

## Role Variables

Available variables are listed below, along with default values (see ```defaults/main.yml```)
```shell
# variables for raspbian/debian distro
poe_fan_temp0: 75000 # example 55000 = 55'C
poe_fan_temp1: 78000
poe_fan_temp2: 80000
poe_fan_temp3: 81000

# variables for ubuntu distros
trip_point_temp3: 75000
trip_point_hyst3: 5000 # hysterisis value determines the temp when fan rpm changes down a state
trip_point_temp2: 78000
trip_point_hyst2: 2000
trip_point_temp1: 80000
trip_point_hyst1: 2000
trip_point_temp0: 81000
trip_point_hyst0: 5000

# rpi's will require reboot for changes to take effect. False prevents role from rebooting rpi's
reboot_var: true
```
## Dependencies

None

## Example Playbook
```yaml
---
- name: set poe hat fan trip points on rpi cluster hosts
  hosts: all
  become: true
  gather_facts: true
   
  roles:
    - rpi_poe_hat_conf
```

## License

![GitHub](https://img.shields.io/github/license/lpwoodhouse/playbook_rpi_poe_hat_conf)

## Author Information

This role was created in 2022 by [Lee Woodhouse](https://www.leewoodhouse.com/)
