openwrt-system
==============

configure general aspects of your openwrt system.
compare: [http://wiki.openwrt.org/doc/uci/system]

Dependencies
------------

* [openwrt-uci](module https://github.com/flandiGT/openwrt-uci)

Role Variables
--------------

| variable name     | type                   | default                                                                                     |
|-------------------|------------------------|---------------------------------------------------------------------------------------------|
| hostname          | text                   | OpenWRT                                                                                     |
| timezone          | text                   | <empty>                                                                                     |
| zonename          | text                   | UTC                                                                                         |
| enable_ntp_client | boolean                | true                                                                                        |
| enable_ntp_server | boolean                | false                                                                                       |
| ntp_servers       | array of strings       | [] (means: no changes on existing configuration)                                            |
| leds              | map of objects         | {} (means: no changes on existing configuration)                                            |

led object structure:

| attribute name | property type       | description                                                                     |
|----------------|---------------------|---------------------------------------------------------------------------------|
| name           | text                | Name or description text                                                        |
| default        | integer             | LED state before trigger: 1 means ON and 0 means OFF                            |
| sysfs          | text                | LED device name (like "tp-link:blue:wlan2g" or "tp-link:green:usb1")            |
| trigger        | text                | trigger, like: phy0rx (see OpenWRT documentation)                               |

Example Playbook
----------------

```
- role: openwrt-system
  hostname: OpenWrt
  enable_ntp_client: true
  enable_ntp_server: false
  ntp_servers:
    - 0.openwrt.pool.ntp.org
    - 1.openwrt.pool.ntp.org
    - 2.openwrt.pool.ntp.org
    - 3.openwrt.pool.ntp.org
  leds:
    led_wlan2g:
      name: WLAN2G
      sysfs: "tp-link:blue:wlan2g"
      default: 0
      trigger: phy0rx
    led_wlan5g:
      name: WLAN5G
      sysfs: "tp-link:blue:wlan5g"
      default: 0
      trigger: phy1rx
```

Official documentation
* [OpenWRT Wiki / System configuration](http://wiki.openwrt.org/doc/uci/system)

Got idea from:
* [lefant/ansible-openwrt-system](https://github.com/lefant/ansible-openwrt-system)
