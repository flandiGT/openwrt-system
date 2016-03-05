openwrt-system
==============

configure general aspects of your openwrt system.
compare: [http://wiki.openwrt.org/doc/uci/system]

Role Variables
--------------

| variable name     | type                   | default |
|-------------------|------------------------|---------|
| hostname          | text                   | OpenWRT |
| timezone          | text                   | <empty> |
| zonename          | text                   | UTC     |
| enable_ntp_client | boolean                | true    |
| enable_ntp_server | boolean                | false   |
| ntp_servers       | text (comma-separated) | 0.openwrt.pool.ntp.org,1.openwrt.pool.ntp.org,2.openwrt.pool.ntp.org,3.openwrt.pool.ntp.org |

Dependencies
------------

* openwrt-uci

Example Playbook
----------------

```
- role: openwrt-system
  hostname: OpenWrt
  enable_ntp_client: true
  enable_ntp_server: false
  ntp_servers: 0.openwrt.pool.ntp.org,1.openwrt.pool.ntp.org,2.openwrt.pool.ntp.org,3.openwrt.pool.ntp.org
```

[http://wiki.openwrt.org/doc/uci/system]: http://wiki.openwrt.org/doc/uci/system
[lefant.openwrt-uci]: https://galaxy.ansible.com/list#/roles/1645
[https://github.com/lefant/ansible-openwrt/blob/master/openwrt.yml]: https://github.com/lefant/ansible-openwrt/blob/master/openwrt.yml
