local_ansible_config
=========

Load one or more config entries for current ansible instance.

The output variable is like:

```
local_ansible_config: {
    "config_file": "/etc/ansible/ansible.cfg",
    "defaults": {
        "roles_path": "../",
        ";unset.xxx": true
    },
    "sections": [
        "defaults",
        "privilege_escalation",
        "paramiko_connection",
        "ssh_connection",
        "accelerate",
        "selinux",
        "colors"
    ]
}
```

Requirements
------------

Ansible >= 2.2.1.0
jinja >= 2.7

Role Variables
--------------

`config_key` (optionl) could be:
- unset (default), for dependencies
- a string of a config key in the form of "section.key"
- a list of strings of config keys

Dependencies
------------

N/A

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
      - role: ansible-local-ansible-config-role
      - role: ansible-local-ansible-config-role
        config_key: [ a.bc, defaults.roles_path ]
      - role: ansible-local-ansible-config-role
        config_key: [ defaults.roles_path, defaults.xxx ]
        config_key: defaults.xxx


License
-------

BSD
