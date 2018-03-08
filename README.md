# Ansible Role: Ansible Base Setup

Executes tasks that have to be executed on any system used.
Installs [ZSH](https://wiki.ubuntuusers.de/Zsh/) with [OhMyZSH](http://ohmyz.sh/) and sets the timezone (defaults to `Europe/Berlin`)

## Installed Software
- If set, additional APT packages will be installed
- Locales for the system will be generated
- [ZSH](https://wiki.ubuntuusers.de/Zsh/) with [OhMyZSH](http://ohmyz.sh/)
    - default theme for user `vagrant` = [gnzh](https://github.com/robbyrussell/oh-my-zsh/blob/master/themes/gnzh.zsh-theme)
    - default theme for user `root` = [robbyrussel](https://github.com/robbyrussell/oh-my-zsh/blob/master/themes/robbyrussell.zsh-theme)

## Requirements

Ubuntu min. version 16.04

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

*`additional_software`*:
Names of the APT packages to install at the beginning of the provisioning

*`required_locales`*: 
Which locales to install on the VM

## Dependencies

- [staenker.timezone](https://galaxy.ansible.com/staenker/timezone/)
- [gantsign.oh-my-zsh](https://galaxy.ansible.com/gantsign/oh-my-zsh/)

## Example Playbook
    - hosts: db-servers
      become: yes
      vars:
        additional_software: { }
        required_locales:
          - en_US
          - en_US.UTF-8
          - de_DE
          - de_DE.UTF-8
      roles:
        - { role: ffb.ansible-base-setup }
## License

MIT / BSD

## Author Information

This role was created in 2018 by [four-for-business](https://www.4fb.de/).