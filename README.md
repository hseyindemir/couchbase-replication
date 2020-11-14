Role Name
=========

couchbase-replicate


Role Description
=========
 
The role couchbase-replicate is responsible for creating and replicating a bucket from a source cluster into destination cluster. Please keep in mind

* Both source and destination clusters' Administrator password must be the same.
* The XDCR setup is created during this operations
* Only one bucket can be replicated at a time 

Role Variables
--------------

* source_cluster: 192.168.1.1
* destination_cluster: 192.168.1.2
* xdcr_name: 'demo'
* source_xdcr_bucket: 'beer-sample'
* destination_xdcr_bucket: 'beer-sample'
* bucket_ram: 2048
* bucket_replica_count: 1
* xdcr_pass: 'some_pass'
* create_bucket_on_destination: 'no'

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```ansible
---
- hosts: all
  become: true
  roles: 
    - role: couchbase-replicate
      vars:
        source_cluster: source_ip
        destination_cluster: destination_ip
        xdcr_name: 'demo'
        source_xdcr_bucket: 'source_bucket'
        destination_xdcr_bucket: 'destination_bucket'
        bucket_ram: 128
        bucket_replica_count: 1
        xdcr_pass: 'test123'
        create_bucket_on_destination: 'yes'
```

Author Information
------------------

Hüseyin DEMİR (Database Team)
