Ansible Role: OSSEC-HIDS
=========

This role installs and configures OSSEC-HIDS in local mode. Depending on the defined variables, it is possible to choose the protections and also if email notifications are enabled.

Requirements
------------

No specific requirements for this role.

Role Variables
--------------

There are a bunch of variables for this particular role. Most of them are used during the installation of OSSEC-HIDS which asks a number of questions.

Here is an example of configuration with all protections and email notifications enabled:


```
# OSSEC installation questions (with email notifications)
ossec_dir: /var/ossec
ossec_install_type: local
ossec_email: y
ossec_email_address: myemail@email.com
ossec_detected_smtp_use: n
ossec_smtp_server: localhost
ossec_integritycheck_daemon: y
ossec_rootkit_engine: y
ossec_active_response: y
ossec_firewalldrop_response: y
```


This other example enables all protections but disables email notifications:


```
# OSSEC installation questions (without email notification)
ossec_dir: /var/ossec
ossec_install_type: local
ossec_email: n
ossec_integritycheck_daemon: y
ossec_rootkit_engine: y
ossec_active_response: y
ossec_firewalldrop_response: y
```

These variables should be defined in either group_vars or host_vars.

Dependencies
------------

No dependencies from other roles required.

Example Playbook
----------------

Here is a simple example playbook to use this role:

```
hosts: all
user: myuser
become: true
roles:
  - { role: ossec, tags: [ 'ossec' ] }
```

License
-------

MIT / BSD

Author Information
------------------

My name is Gaétan. You can follow me on [Twitter](https://twitter.com/gaetanict)

Website: [ICT Pour Tous](https://www.ictpourtous.com)
