# role-homeshick

### Master:
[![role-homeshick](https://github.com/osx-provisioner/role-homeshick/actions/workflows/push.yml/badge.svg?branch=master)](https://github.com/osx-provisioner/role-homeshick/actions/workflows/push.yml)

### Production:
[![role-homeshick](https://github.com/osx-provisioner/role-homeshick/actions/workflows/push.yml/badge.svg?branch=production)](https://github.com/osx-provisioner/role-homeshick/actions/workflows/push.yml)

Ansible role that installs homeshick, and the specified dotfiles repository on OSX machines.

### Notes:
- See the [homeshick GitHub Repository](https://github.com/andsens/homeshick) for further details about this tool.

Requirements
------------

- [Git](https://git-scm.com/) must be present on the machine.  (See the [Dependencies](#Dependencies) section below.)


Role Variables
--------------
- `homeshick_user`:
  - The user to become when installing the dotfiles and homeshick repos.
- `homeshick_user_home`:
  - The home directory where the dotfiles should be installed.
- `homeshick_repository`:
  - Specifies the location of the base homeshick repository.
- `homeshick_version`:
  - Specifies the version of homeshick to check out.
- `homeshick_dotfiles_repo`:
  - Specifies the URL of a user dotfiles definition to install.
- `homeshick_force`:
  - When symlinking the dotfiles, overwrite any existing content.

[See The Default Values](defaults/main.yml)

Dependencies
------------

- [elliotweiser.osx-command-line-tools](https://galaxy.ansible.com/elliotweiser/osx-command-line-tools)

Example Playbook
----------------

```yaml
- hosts: all
  roles:
  - role: osx_provisioner.homeshick
    homeshick_dotfiles_repo: "https://github.com/niall-byrne/dotfiles.git"
    homeshick_version: "v2.0.0"
    homeshick_force: true
```

License
-------

MIT

(homeshick is also licensed as MIT)

Author Information
------------------

Niall Byrne <niall@niallbyrne.ca>
