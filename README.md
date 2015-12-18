Dockernet
=========

[![Join the chat at https://gitter.im/mpeuster/dockernet](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/mpeuster/dockernet?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

### Use Docker containers as hosts inside your Mininet topologies. Interact with the containers through Mininet's CLI.

This fork of Mininet allows to use Docker containers as Mininet hosts. This enables interesting functionalities to built networking/cloud testbeds. The integration is done subclassing the original Host class.


* WIP! Not fully functional yet.
* Contributions welcome :)

Based on: Mininet 2.2.1

### Features

* Add, remove Docker containers to Mininet topologies
* Connect Docker containers to topology (to switches, other containers, or legacy Mininet hosts )
* Execute commands inside Docker containers by using the Mininet CLI 
* Dynamic topology changes (lets behave like a small cloud ;-) )
 * Add Hosts/Docker containers to a *running* Mininet topology
 * Connect Hosts/Docker containers to a *running* Mininet topology
 * Remove Hosts/Docker containers/Links from a *running* Mininet topology
* Automated unit tests for all new features

### Dependencies

* Ubuntu 14.04 LTS
* Docker
* docker-py

### Installation
Automatic installation is provide through an Ansible playbook.
* Requires: Ubuntu 14.04 LTS
* `sudo apt-get install ansible git`
* `sudo vim /etc/ansible/hosts`
* Add: `localhost ansible_connection=local`
* `git clone https://github.com/mpeuster/dockernet.git`
* `cd dockernet/ansible`
* `sudo ansible-playbook install.yml`
* Wait (and have a coffee) ...

### Usage / Run
Start example topology with some empty Docker containers connected to the network.

* `cd dockernet`
* run: `sudo python examples/dockerhosts.py`
* use: `mininet> d1 ifconfig` to see config of container d1

### Tests
There is a set of Dockernet specific unit tests located in `mininet/test/test_dockernet.py`. To run these, do:

* `cd dockernet/mininet`
* `sudo python test -d`

### TODOs
* see Wiki: https://github.com/mpeuster/dockernet/wiki/Dockernet-TODO

### Credits
Dockernet (c) 2015 by Manuel Peuster

* Inspired by: http://techandtrains.com/2014/08/21/docker-container-as-mininet-host/


### Contact
Manuel Peuster
manuel (dot) peuster (at) upb (dot) de
