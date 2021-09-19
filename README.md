# ansible-pmm-server-k8s

**Currently this repository is a placeholder.**

Ansible role to run PMM Server on Kubernetes.


## Requisites

Kubernetes is required. This role was initially developed for
Red Hat Enterprise Linux Server release 7.9 (Maipo).

Ansible version: 2.9.


## Variables

A PMM Server and all the clients connecting to it should form a hostgroup.
These variables should be specified at group level. This will allow us to specify
this information once, and make it available to all hosts that need it.

* `pmm_server_host`: PMM Server IP or hostname. Hint: you may want to specify this in your inventory.
* `pmm_server_port`: PMM Server port. Hint: you may want to specify this in your inventory.
* `pmm_server_user`: Username used by PMM Clients to access PMM Server.
* `pmm_server_password`: Password for `pmm_server_user`.


## Tags

Normal operations:

- `pmm`: Run this role and PMM client roles that use this tag.
- `pmm-server`: Run this role.

Validation (use these tags after making changes):

- `validate`: Validate this role and other roles that support this tag.
- `pmm-validate`: Validate this role and other PMM Server and Client roles that support this role.
- `pmm-server-validate`: Validate this role.


## Examples

Deploying PMM Server on a host group called `pmm_server`:

```
ansible-playbook -t pmm-server -l pmm_server -i mariadb mariadb.yml
```


## Copyright and License

Copyright  2021  Vettabase Ltd

License: BSD 3 (BSD-New).

Developed and maintained by Vettabase Ltd:

https://vettabase.com

Contributions are welcome.



