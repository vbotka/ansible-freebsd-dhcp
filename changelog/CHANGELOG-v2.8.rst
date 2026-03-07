=====================================
vbotka.freebsd_dhcp 2.8 Release Notes
=====================================

.. contents:: Topics


2.8.1
=====

Release Summary
---------------
Add this role to the collection vbotka.freebsd

Major Changes
-------------

Minor Changes
-------------
* Update README.


2.8.0
=====

Release Summary
---------------
Ansible 2.20 update

Major Changes
-------------
* Support FreeBSD 13.5, 14.3, and 15.0

Minor Changes
-------------
* Update README.
* Update Ansible lint config.
* Fix Ansible lint.
* Variables `ansible_` moved to the dictionary ansible_facts
* Add template dhcpd.conf-minimal.j2
* Add variables +bsd_dhcpd_rcconfd (default=false), bsd_dhcpd_rcconf
  (default=[])
* Use the module community.general.sysrc to configure rc.conf


Bugfixes
--------

Breaking Changes / Porting Guide
--------------------------------
