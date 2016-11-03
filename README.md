# ansible-rsyslog
Open-source replacement for syslogd, supporting TCP, SSL, TLS, and RELP while interfacing with MySQL, PostgreSQL, and Oracle.

[![Platforms](http://img.shields.io/badge/platforms-ubuntu-lightgrey.svg?style=flat)](#)
[![Licence](https://img.shields.io/badge/License-MIT-blue.svg)](https://tldrlegal.com/license/mit-license)

Tunables
--------
* `rsyslog_isrelay` (boolean) - Configure this server as a relay (uses both client and server configurations)
* `rsyslog_isclient` (boolean) - Configure this server as a client to only send logs
* `rsyslog_isserver` (boolean) - Configure this server as a server to receive logs
* `rsyslog_remote` (associative array) - Configures the client on how and where to find the server


Example Playbook
----------------
    - hosts: servers
      roles:
         - role: stevenharradine.rsyslog
           rsyslog_isclient: yes
           rsyslog_remote:
             - { mask: "*.*", protocol: "@@", host: localhost, port: 514 }

Contributors
------------
* Steven Harradine
