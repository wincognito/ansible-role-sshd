SSHD
=========

Updates `/etc/ssh/sshd.conf` according to the `sshd_config_regex_changes`.

Requirements
------------

No requirements.


Role Variables
--------------

Change the variables:
```
sshd_port: 22 # i.e. 4558
sshd_permit_root_login: without-password # possible values: yes, without-password, forced-commands-only, no
sshd_strict_mode: yes # Checks ~/.ssh permissions
sshd_max_auth_tries: 3
sshd_login_grace_time: 30s
```

For complete customization change `sshd_config_regex_changes` according to your needs.

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

#### In case sshd does not want to restart
Validate configuration
```
sudo sshd -t
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

MIT

(c) 2021 Pawel Idzikowski

Author Information
------------------

Pawel Idzikowski
