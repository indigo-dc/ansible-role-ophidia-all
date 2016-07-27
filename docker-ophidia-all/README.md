docker-ophidia-terminal
=======================

Dockerfile to run the ophidia big data framework


Introduction
------------

The image is built from the ansible-role of the following github
repository:
* https://github.com/indigo-dc/ansible-role-ophidia-all

It builds the ophidia framework application from:
* https://github.com/indigo-dc/ophidia-terminal
* https://github.com/indigo-dc/ophidia-server
* and other components

Information on running ophidia-terminal is in this repository and at
* http://ophidia.cmcc.it/documentation

Build docker image
------------------

The image can be built with
```
docker build -t ophidia-all .
```

Or you can pull it from the dockerhub:
```
$ docker pull indigodatacloudapps/ophidia-all
```

Run docker-ophidia-all
----------------------

To run the container either:

```
docker run -it ophidia-all oph_term
```

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
* Further information can be found at: http://ophidia.cmcc.it/documentation.
