# -*- mode: ruby -*-
# vi: set ft=ruby :

BOX_IMAGE = "ubuntu/bionic64"
NODE_COUNT = 2

Vagrant.configure("2") do |config|

  config.vm.box = BOX_IMAGE
  config.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 2
  end

  config.vm.define "master" do |master|
    master.vm.hostname = "master"
    master.vm.network :private_network, ip: "192.168.56.10"
  end

  (1..NODE_COUNT).each do |i|
    config.vm.define "worker-0#{i}" do |worker|
      worker.vm.hostname = "worker-0#{i}"
      worker.vm.network :private_network, ip: "192.168.56.#{i + 10}"
    end
  end

end
