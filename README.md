openwrt-system
==============

configure general aspects of your openwrt system.
compare: [http://wiki.openwrt.org/doc/uci/system]

Role Variables
--------------

* hostname
* timezone
* zonename

Dependencies
------------

* openwrt-uci

Example Playbook
----------------

  roles:
    - role: openwrt-system
      hostname: OpenWrt
      timezone: UTC


[http://wiki.openwrt.org/doc/uci/system]: http://wiki.openwrt.org/doc/uci/system
[lefant.openwrt-uci]: https://galaxy.ansible.com/list#/roles/1645
[https://github.com/lefant/ansible-openwrt/blob/master/openwrt.yml]: https://github.com/lefant/ansible-openwrt/blob/master/openwrt.yml
