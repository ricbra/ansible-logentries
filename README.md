logentries
==========

This role installs and configures the logentries.com agent.

Requirements
------------

Tested on:
- Debian wheezy
- Ubuntu trusty, precise
- Centos 6

Role Variables
--------------

Only thing required by this role is your logentries.com account key. But you probably want to follow one or more logs so
an average configration looks like this:

```yml
logentries_account_key: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxx"

logentries_logs:
  - name: "Authentication"
    path: "/var/log/auth.log"

```

When you later on want to unfollow a log:

```yml

logentries_logs:
  - name: "Authentication"
    path: "/var/log/auth.log"
    state: absent

```

Dependencies
------------

None.

Example Playbook
----------------

Small example of how to use this role in a playbook:

    - hosts: servers
      roles:
         - { role: ricbra.logentries, logentries_account_key: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxx" }

License
-------

MIT

Author Information
------------------

Richard van den Brand
