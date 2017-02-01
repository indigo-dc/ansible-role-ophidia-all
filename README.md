Role Name
=========

The ansible role deploys and configures all services for the Ophidia Big
Data Framework

Introduction
------------

The repository contains ansible-roles that are published in
ansible galaxy: https://galaxy.ansible.com/indigo-dc/ophidia-all/

The directories docker-ophidia-all are linked to
dockerhub with automatic build of image.

Requirements
------------

No aditional requirements

Role Variables
--------------

Default role varibles are:

1. oph_user: user that will run the framework
2. cert_passwd: the password for the certificates, user account and mysql

Dependencies
------------

None

Example Playbook
----------------


An example of playbook to deploy Ophidia:

```yaml
- hosts: localhost
  roles:
    - { role: indigo-dc.ophidia-all }
```

Or execute:

```
$ ansible-playbook /etc/ansible/roles/indigo-dc.ophidia-all/tests/test.yml
```

Ophidia terminal test session
-----------------------------

The following commands define a complete test session that can be run through the Ophidia terminal

```
/usr/local/ophidia/oph-terminal/bin/oph_term -H 127.0.0.1 -u oph-test -p abcd -P 11732
oph_term> oph_list level=2;
oph_term> oph_man function=oph_list;
oph_term> oph_createcontainer container=test;dim=lat|lon|time;hierarchy=oph_base|oph_base|oph_time;dim_type=double|double|double;
oph_term> oph_randcube container=test;dim=lat|lon|time;dim_size=10|10|10;measure=test;measure_type=double;nfrag=10;ntuple=10;concept_level=c|c|d;exp_ndim=2;compressed=no; 
oph_term> oph_cubeschema
oph_term> oph_reduce operation=max;
oph_term> oph_aggregate operation=max;
oph_term> oph_explorecube
oph_term> oph_delete cube=[container=test];
oph_term> quit
```

Further documentation
---------------------

* Ophidia: http://ophidia.cmcc.it/documentation/
* Installation and configuration: http://ophidia.cmcc.it/documentation/admin/index.html

License
-------

Apache v2

Author Information
------------------

Mario David: mariojmdavid@gmail.com
LIP and Indigo-DataCloud project

Acknowledgments
---------------

* Ophidia CMCC group