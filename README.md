ansible systemd-cifs-mounts
===========================
[![Build Status](https://travis-ci.org/ypsman/ansible-systemd-cifs-mounts.svg?branch=master)](https://travis-ci.org/ypsman/ansible-systemd-cifs-mounts)

Setup mounts as sysemd Service.

This Playbook creates a Systemd Service for mounting CIFS Shares.

So you can use mounts as system Servie.

Works for debian stretch, and Jessie if you use systemd.

It mounts several Folders from one Server.

for Example:

    systemctl status mount-point.mount
    systemctl start mount-point.mount
    systemctl stop mount-point.mount

    systemctl status mount-point.automount
    systemctl start mount-point.automount
    systemctl stop mount-point.automount

Options:
--------

    cifs_mount_share: //apps.local/apps$         # Server to mount From
    cifs_mount_path: /opt/app                    # Folder to mount in
    cifs_mount_options: uid=1000                 # Options, username...

Example Playbook
----------------

    - hosts: all
      roles:
        - role: systemd-cifs-mounts
            cifs_mounts:
              - folder1
              - folder2
