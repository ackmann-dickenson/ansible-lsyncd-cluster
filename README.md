lsyncd-cluster
=========

Installs and configures a set of lsyncd installations on different hosts and assings 1 host to be the master. From https://github.com/markmaas/ansible-lsyncd-cluster.

Requirements
------------

None

Role Variables
--------------

  - lsyncd_max_user_watches: 4194304
    - Desired number of inotify watches in the kernel. Should be more then the number of files and folders you want to be kept in sync

  - lsyncd_path: /data
    - The folder you want to keep in sync

  - lsyncd_master_node: nfs_1
    - This is a part of, or the complete hostname that you want to assing as the "master" lsyncd

  - play_hosts
    - Built-in variable containing all the hosts in the current play that this role finds itself in.

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: markmaas.ansible-lsyncd-cluster }

License
-------

GPLv3

Author Information
------------------

Mark Maas
mark@maas-martin.nl
Fastest way to my heart is via email
