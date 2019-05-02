Kickstart
=========

Set up a Linux host to serve PXE/TFTP and Kickstart files.

This is all very simplistic – for example, we install the httpd package but do
**nothing** with the config. In the real world httpd would be a separate
install, and hopefully a proper configuration. But, out of the box, to
demonstrate principles here, it works just fine. YMMV.

Requirements
------------


Role Variables
--------------

defaults/main.yml

```
kickstart_pkgs: 
  - tftp-server
  - syslinux-tftpboot
  - createrepo
  - httpd
kickstart_tftpdir: /var/lib/tftpboot
```

You'll want to tailor `kickstart_server`

Dependencies
------------


Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: kickstart, kickstart_server: kickstart.lan }

License
-------

BSD

Author Information
------------------

Mark Phillips <mark@probably.co.uk>
