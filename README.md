# ansible-rbenv

[![Build Status](https://travis-ci.org/suzuki-shunsuke/ansible-rbenv.svg?branch=master)](https://travis-ci.org/suzuki-shunsuke/ansible-rbenv)

ansible role to install [rbenv](https://github.com/rbenv/rbenv) and [ruby-build](https://github.com/rbenv/ruby-build).

https://galaxy.ansible.com/suzuki-shunsuke/rbenv/

## Requirements

* git

## Role Variables

name | required | default | description
--- | --- | --- | ---
rbenv_root | no | $RBENV_ROOT >> $HOME/.rbenv
rbenv_repo | no | https://github.com/rbenv/rbenv |
rbenv_version | no | HEAD |
rbenv_update | no | yes |
rbenv_is_dependencies_installed | no | no | By default build dependencies are not installed
rbenv_rc_path | no | "NOT ADD" | By default configuration is not added
rbenv_darwin_build_dependencies | no | see [defaults/main.yml](https://github.com/suzuki-shunsuke/ansible-rbenv/blob/master/defaults/main.yml) | If rbenv_is_dependencies_installed is "no" this is ignored
rbenv_redhat_build_dependencies | no | see [defaults/main.yml](https://github.com/suzuki-shunsuke/ansible-rbenv/blob/master/defaults/main.yml) | If rbenv_is_dependencies_installed is "no" this is ignored
rbenv_debian_build_dependencies | no | see [defaults/main.yml](https://github.com/suzuki-shunsuke/ansible-rbenv/blob/master/defaults/main.yml) | If rbenv_is_dependencies_installed is "no" this is ignored

About build dependencies, see also [here](https://github.com/rbenv/ruby-build/wiki#suggested-build-environment).

## Dependencies

Nothing.

## Example Playbook

```yaml
- hosts: servers
  roles:
  - role: suzuki-shunsuke.rbenv
    rbenv_version: v1.1.1
    rbenv_update: no
    rbenv_root: "{{ ansible_env.HOME }}/.ghq/github.com/rbenv/rbenv"
    rbenv_is_dependencies_installed: yes
    rbenv_rc_path: "{{ ansible_env.HOME }}/.bashrc"
    rbenv_darwin_build_dependencies:
    - readline
```

## Change Log

See [CHANGELOG](CHANGELOG.md).

## See also

* [suzuki-shunsuke.rbenv-module](https://github.com/suzuki-shunsuke/ansible-rbenv-module): ansible module to run `rbenv` command

## License

[MIT](LICENSE)
