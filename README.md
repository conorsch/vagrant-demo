# Using Vagrant for Dev VMs

## Motivation
I want to install software for work, but not junk up my host machine with permanent changes.
In particular, I want to use work VPNs, without routing all my host machine's traffic through same.
Ideally, a CLI tool exists to enable this.

## Solution
Just use Vagrant. It's antiquated technology, but boring tools are reliable tools.

## Installation

1. Install [Vagrant].
2. Install [vagrant-libvirt](https://github.com/vagrant-libvirt/vagrant-libvirt).

## First run setup

Check out this repository, then run:

```

vagrant box add debian/bookworm64
# when prompted, choose libvirt
vagrant up
vagrant ssh
```

You should now have a shell inside the VM.

## Common operations

```
# to enter the VM:
cd path/to/directory/with/Vagrantfile
vagrant up

# to put it away for later
vagrant halt

# to completely nuke the VM, including all private state
vagrant destroy
```

[Vagrant]: https://www.vagrantup.com/
