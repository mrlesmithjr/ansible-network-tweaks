Role Name
=========

A role to configure sysctl settings in order to tweak network performance more optimally.

Requirements
------------

None

Role Variables
--------------
````
---
# defaults file for ansible-network-tweaks
enable_network_tweaks: true  #defines if settings should be applied
network_tweaks:
  - name: net.ipv4.tcp_tw_reuse
    value: 1
    set: true
  - name: net.ipv4.ip_local_port_range
    value: "1024 65023"
    set: true
  - name: net.ipv4.tcp_max_syn_backlog
    value: 40000
    set: true
  - name: net.ipv4.tcp_max_tw_buckets
    value: 400000
    set: true
  - name: net.ipv4.tcp_max_orphans
    value: 60000
    set: true
  - name: net.ipv4.tcp_syncookies
    value: 1
    set: true
  - name: net.ipv4.tcp_synack_retries
    value: 3
    set: true
  - name: net.core.somaxconn
    value: 40000
    set: true
  - name: net.ipv4.tcp_fin_timeout
    value: 5
    set: true
````
Dependencies
------------

Example Playbook
----------------

#### Galaxy
-----------
    - hosts: servers
      roles:
         - { role: mrlesmithjr.domain-join }
#### GitHub
-----------
    - hosts: servers
      roles:
        - ansible-domain-join

License
-------

BSD

Author Information
------------------

Larry Smith Jr.
- @mrlesmithjr
- http://everythingshouldbevirtual.com
- mrlesmithjr [at] gmail.com
