ansible-role-backup-gluster
=========

This role provides functionality to backup a Red Hat OCS Gluster Cluster running in independant mode, that is where Gluster is running outside of OpenShift. This process follows the work by Annette Clewett and Luis Rico here: https://github.com/red-hat-storage/rhocs-backup

Requirements
------------

Cluster-Admin on a function OpenShift cluster with a working Gluster storage cluster attached.

Role Variables
--------------

```install_storageclass_config: true
install_prereqs_config: true
storageclass_overwrite_config: true
run_backup: true

## Directory for temporary files to put the list of
## Gluster volumes /snaps to backup
snapshot_dir: /backups/snapshots

## Destination directory for mounting snapshots of Gluster volumes:
mount_directory: /mnt/source

## Heketi Route and Credentials
heketi_user: admin ## User with admin permissions to dialog with Heketi
heketi_secret: "INSERT YOUR KEY HERE" ## Heketi user key
heketi_url: http://heketi-storage-glusterfs.example.com ## Route where Heketi pod is listening```




Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: all
      roles:
         - { role: eti.ocs-gluster-backup }

License
-------

BSD

Author Information
------------------

https://eti.io
