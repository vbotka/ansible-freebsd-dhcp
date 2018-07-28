freebsd_dhcp
============

[![Build Status](https://travis-ci.org/vbotka/ansible-freebsd-dhcp.svg?branch=master)](https://travis-ci.org/vbotka/ansible-freebsd-dhcp)

[Ansible role.](https://galaxy.ansible.com/vbotka/freebsd_dhcp/) Configure DHCP in FreeBSD.


Requirements
------------

No requiremenst.



Variables
---------

TBD (Check the defaults).


Workflow
--------

1) Change shell to /bin/sh.

```
ansible do-bsd-test -e 'ansible_shell_type=csh ansible_shell_executable=/bin/csh' -a 'sudo pw usermod freebsd -s /bin/sh'
```

2) Install role.

```
ansible-galaxy install vbotka.freebsd_dhcp
```

3) Fit variables.

```
~/.ansible/roles/vbotka.freebsd_dhcp/vars/main.yml
```

4) Create and run the playbook.

```
> cat ~/.ansible/playbooks/freebsd-dhcp.yml
---
- hosts: do-bsd-tetst
  become: yes
  become_method: sudo
  roles:
    - role: vbotka.freebsd_dhcp
    
> ansible-playbook ~/.ansible/playbooks/freebsd-dhcp.yml
```


License
-------

[![license](https://img.shields.io/badge/license-BSD-red.svg)](https://www.freebsd.org/doc/en/articles/bsdl-gpl/article.html)


Author Information
------------------

[Vladimir Botka](https://botka.link)
