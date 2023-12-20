# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # We'll use a standard Debian Stable box.
  config.vm.box = "debian/bookworm64"
  config.vm.box_check_update = false

  # We override the default shared folder dir to use 9p, rather than NFS.
  # Consider changing `./` to a host directory that should be mounted in the VM.
  config.vm.synced_folder "./", "/vagrant", type: "9p", disabled: false, accessmode: "squash", access: "1000"

  # Customize the resources allotted to the VM. Changes require a `vagrant reboot`.
  config.vm.provider "libvirt" do |lv|
    lv.memory = "8000"
    lv.cpus = 4
  end

  # Name the box something unique. Should only be altered when VM does not exist!
  config.vm.define "devbox" do |vm|
  end

  # Shell provisioner will only run once, at VM creation time,
  # not every time it boots.
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y curl vim
  SHELL
end
