# freebsd_dhcp

[![quality](https://img.shields.io/ansible/quality/27910)](https://galaxy.ansible.com/vbotka/freebsd_dhcp)[![Build Status](https://travis-ci.org/vbotka/ansible-freebsd-dhcp.svg?branch=master)](https://travis-ci.org/vbotka/ansible-freebsd-dhcp)

[Ansible role.](https://galaxy.ansible.com/vbotka/freebsd_dhcp/) Configure DHCP in FreeBSD.

Feel free to [share your feedback and report issues](https://github.com/vbotka/ansible-freebsd-dhcp/issues).

[Contributions are welcome](https://github.com/firstcontributions/first-contributions).


## Requirements

None.


## Role Variables

Review the defaults and examples in vars.


## Workflow

1) Change shell to /bin/sh

```
shell> ansible do-bsd-test -e 'ansible_shell_type=csh ansible_shell_executable=/bin/csh' -a 'sudo pw usermod freebsd -s /bin/sh'
```

2) Install role

```
shell> ansible-galaxy install vbotka.freebsd_dhcp
```

3) Fit variables

```
shell> ~/.ansible/roles/vbotka.freebsd_dhcp/vars/main.yml
```

4) Create and run the playbook

```
shell> cat ~/.ansible/playbooks/freebsd-dhcp.yml
---
- hosts: do-bsd-tetst
  become: yes
  become_method: sudo
  roles:
    - role: vbotka.freebsd_dhcp
    
shell> ansible-playbook ~/.ansible/playbooks/freebsd-dhcp.yml
```

## Firewall

Add the following rules to /etc/pf.conf

```
dhcp_ports="{ bootps, bootpc }"
pass quick on $if proto { tcp, udp } to $if port $dhcp_ports
```


## References

- [FreeBSD handbook: 29.6. Dynamic Host Configuration Protocol (DHCP)](https://www.freebsd.org/doc/handbook/network-dhcp.html)
- [Highly Available DHCP Server on FreeBSD](https://medium.com/@vermaden/highly-available-dhcp-server-on-freebsd-2bf81a5e4e77)
- [man dhcpd(8)](https://www.freebsd.org/cgi/man.cgi?query=dhcpd)
- [man dhcpd.conf(5)](https://www.freebsd.org/cgi/man.cgi?query=dhcpd.conf)
- [FreeBSD Forum: pf.conf rules for dhcp](https://forums.freebsd.org/threads/pf-conf-rules-for-dhcp.15213/)


## License

[![license](https://img.shields.io/badge/license-BSD-red.svg)](https://www.freebsd.org/doc/en/articles/bsdl-gpl/article.html)


## Author Information

[Vladimir Botka](https://botka.link)
