rbenv
======

[![Build Status](https://travis-ci.org/suzuki-shunsuke/ansible-rbenv.svg?branch=master)](https://travis-ci.org/suzuki-shunsuke/ansible-rbenv)

Install [rbenv](https://github.com/rbenv/rbenv) and [ruby-build](https://github.com/rbenv/ruby-build).

Requirements
------------

* [motemen/ghq](https://github.com/motemen/ghq)

Role Variables
--------------

* ghq_executable: The executable path of ghq command. The default is "ghq".

Dependencies
------------

* [suzuki-shunsuke.ghq-module](https://galaxy.ansible.com/suzuki-shunsuke/ghq-module/)

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
  - suzuki-shunsuke.rbenv
```

License
-------

MIT
