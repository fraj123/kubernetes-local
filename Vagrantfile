# -*- mode: ruby -*-
# vi: set ft=ruby :

BOX_IMAGE = "ubuntu/bionic64"
NUM_WORKER_NODES = 2
IP_NW = "10.0.0."
IP_START = 10

Vagrant.configure("2") do |config|

  config.vm.box = BOX_IMAGE
  config.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 2
  end

  config.vm.define "master" do |master|
    master.vm.hostname = "master"
    master.vm.network :private_network, ip: IP_NW + "#{IP_START}" 
    master.vm.provision "shell", path: "./scripts/k8scp.sh"
  end

  (1..NUM_WORKER_NODES).each do |i|
    config.vm.define "worker-0#{i}" do |worker|
      worker.vm.hostname = "worker-0#{i}"
      worker.vm.network :private_network, ip: IP_NW + "#{IP_START + i}"
      worker.vm.provision "shell", path: "./scripts/k8sSecond.sh"
    end
  end

end
