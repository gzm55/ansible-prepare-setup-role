prepare_setup
=============

Do bootstrap works for running setup module. This will deal with ssh key, install python and so on.

Requirements
------------

ansible>=2.2

Role Variables
--------------

- `ansible_pubkey_login_is_disabled`, default is False, if set to True,
      this role skips install pubkey to remote machines, and have to login via password.

Dependencies
------------

- `gzm55.reachable`
- `gzm55.local_openssh_client_permission`
- `gzm55.local_ssh_known_hosts`
- `gzm55.ssh_pubkey_login`
- `gzm55.smart_ssh_pipelining`
- `gzm55.python_module_bootstrap`

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: gzm55.prepare_setup }

License
-------

BSD
