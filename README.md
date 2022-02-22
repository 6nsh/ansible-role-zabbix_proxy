# Ansible Role for Zabbix Proxy 5.4

![Build Status](https://github.com/6nsh/ansible-role-zabbix_server/actions/workflows/ansible-galaxy-ci.yml/badge.svg)

This role helps to install and configure Zabbix Proxy 5.4 to Debian (buster/bullseye).

Requirements
------------

This role requires Ansible 2.9 or higher.

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows:

    zabbix_proxy_hostname: zbx.proxy.com
    zabbix_proxy_server: zabbix.remote.srv.com
    zabbix_proxy_dbname: zbx_proxy
    zabbix_proxy_user: zabbix
    zabbix_proxy_pass: Aver@gEStr0ngPaSSw0rd
    zabbix_proxy_psk: 6c4ccf50bacdb3486f141ba1112e4a46  # openssl rand -hex 16/(32)

Dependencies
------------

First, for this role you need to install MySQL Server 8.0.
You can do it yourself, or by using my dependency role.

    dependencies:
      - role: 6nsh.mysql_server
        tags: mysql_server
        vars:
          mysql_root_password: "{{ mysql_root_password | mandatory }}"

  *You can use default value for {{ mysql_root_password }} or your own.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: 6nsh.zabbix_proxy, tags: zabbix_proxy }

License
-------

MIT

Author Information
------------------

This role was created by Artem Kasianchuk.
