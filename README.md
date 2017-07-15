# mage-wekan

Ansible role to install wekan (kanban board). Depends on 
https://github.com/vaizard/mage-snapd role. See the defaults for configuration options, 
also note that daily backups will be performed via a cron script installed into /etc/cron.d.

Example playbook:

```
---

- hosts: wekan
  vars:
      wekan_root_url: 'https://wekan.example.com'
      wekan_mail_url: 'smtp://user:pass@mailserver.examples.com:25/'
      wekan_mail_from: 'wekan-admin@example.com'
  roles:
     - role: mage-update
     - role: mage-wekan
```

Cheatsheet:

```
# Logs
journalctl -u snap.wekan.wekan
journalctl -u snap.wekan.mongodb

# Services
service snap.wekan.wekan <action>
service snap.wekan.mongodb <action>

# For more help see
wekan.help

# Impossible to refresh wekan to a newer version? See the last comment in
# https://forum.snapcraft.io/t/error-when-updating-snap-and-cleaning-old-revisions/786/14
```