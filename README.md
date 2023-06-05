system_systemd_timer
=========

This role allows you to use the ansible.builtin.systemd and ansible.builtin.template modules to create/remove, enable/disable and start/stop systemd timer unit files.
See the systemd.timer manual page.

Requirements
------------

ansible >= 2.10

Role Variables
--------------

```yml
system_systemd_timer:
  first_entry:
    accuracysec: ...
    description: ...
    fixedrandomdelay: ...
    name: ...
    oncalendar: ...
    onclockchange: ...
    ontimezonechange: ...
    persistent: ...
    state: ...
    randomizeddelaysec: ...
    remainafterelaps: ...
    unit: ...
    wakesystem: ...
  second_entry:
    .
    .
    .
  .
  .
  .
```

Dependencies
------------

None

Example Playbook
----------------

#### Create a plocate-updatedb timer:
```yml
- hosts: servers
  vars:
    system_systemd_timer:
      timer1:
        accuracysec: 20min
        description: Update the plocate database daily
        name: plocate-updatedb
        oncalendar: daily
        persistent: true
        randomizeddelaysec: 12h
```

#### Remove a timer:
```yml
- hosts: servers
  vars:
    system_systemd_timer:
      timer2:
        name: fstrim
        state: absent
```


License
-------

GPL-3.0-only

Author Information
------------------

Role created by Turcu Mihai Ioan
