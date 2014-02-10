# Debian Packer template

## Box description

* OS : Debian 7.3 amd64
* 512MB Ram, 1 CPU
* Default packages : build-essential, curl, puppet, vim, nfs-common

## Prerequisites

* Packer (>= 0.2.0)(http://www.packer.io/downloads.html)
* Vagrant (>= 1.2.4)(http://downloads.vagrantup.com/)
* Virtualbox

### Installing Packer via Homebrew

```bash
$ brew tap homebrew/binary
$ brew install packer
```

## Build vagrant box

```bash
$ packer build debian-7.3.0-amd64.json
```

### Install your new box

```bash
$ vagrant box add debian-7.3.0-amd64 ./debian-7.3.0-amd64.box
```

The VM image has been imported to vagrant, it's now available on your system.

## Vagrant

### Getting Started

To use this image with Vagrant, create a vagrant file (```vagrant init```), and use the newly created box:

```ruby
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "debian-7.3.0-amd64"
end
```

And initialize the vm:

```bash
$ vagrant up
```
