Role Name
=========

Update `/etc/ssh/sshd.conf` according to the `sshd_config_regex_changes`.

Requirements
------------

No requirements.


Role Variables
--------------

```
sshd_config_regex_changes:
- old: "^#?Port "
  new: "Port 4558"

  # possible values:
  # yes, without-password, forced-commands-only, no
- old: "^#?PermitRootLogin "
  new: "PermitRootLogin without-password"

- old: "^#?X11Forwarding "
  new: "X11Forwarding no"   
```


Dependencies
------------

No dependencies

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - sshd_config

License
-------

BSD

(c) 2021 Pawel Idzikowski

Author Information
------------------

Pawel Idzikowski  
http://polenter.com
