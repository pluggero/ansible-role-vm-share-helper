# Ansible Role: VM Share Helper

[![CI](https://github.com/pluggero/ansible-role-vm-share-helper/actions/workflows/ci.yml/badge.svg)](https://github.com/pluggero/ansible-role-vm-share-helper/actions/workflows/ci.yml) [![Ansible Galaxy downloads](https://img.shields.io/ansible/role/d/pluggero/vm-share-helper?label=Galaxy%20downloads&logo=ansible&color=%23096598)](https://galaxy.ansible.com/ui/standalone/roles/pluggero/vm-share-helper)

An Ansible Role that installs a basic configuration of the VM Share Helper.
It can be used to sync data between the shared folder of a VM and the host.
Designed for Pentest VMs.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
vm_share_helper_sync_folders:
  - vbox_share_name: "shared_folder_name" # This must be the name of the VirtualBox shared folder
    unison_name: "profile_name" # This must be the name of the Unison profile
    host: "/mnt/folder"
    vm: "{{ ansible_env.HOME }}/documents/shared"
    sync_interval: "10min" # Automatically sync every 10 minutes
```

Set host-specific shared folders that are synced with the host system using shared folders with the `vm_share_helper_sync_folders` variable.

## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  roles:
    - pluggero.vm_share_helper
```

## License

MIT / BSD

## Author Information

This role was created in 2025 by Robin Plugge.
