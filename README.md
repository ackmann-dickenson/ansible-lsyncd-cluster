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

  - lsyncd_secondary_nodes: 
    - A list of nodes that should receive data
 
  - lsyncd_public_key / lsyncd_private_key:
    - Public and private keys are stored in variables and hopefully in a vault. To preserve formatting, use the pipe character, like:
  ````
  lsyncd_private_key: |
    -----BEGIN RSA PRIVATE KEY-----
    xxxxyyyy
    zzzzaaaa
    -----END RSA PRIVATE KEY-----
  ````
Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: ackmann-dickenson.ansible-lsyncd-cluster }

