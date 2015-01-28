# -*- ruby -*-

Vagrant.configure("2") do |config|
  config.vm.box = "CentOS-6.5-puppet"
  config.vm.box_url = "http://puppet-vagrant-boxes.puppetlabs.com/centos-65-x64-virtualbox-nocm.box"
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "1024"]
  end

  config.vm.define "test" do |test|
    test.vm.network :private_network, ip: "192.168.66.11"
    test.vm.provision :ansible do |ansible|
      ansible.playbook = "test.yml"
      ansible.inventory_path = "inventory/test"
    end
  end

end
