# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  config.vm.box = "bento/centos-6.7"
  
  config.vm.define "elk" do |elk|
    elk.vm.network "forwarded_port", guest: 80, host: 8080

    # Run Ansible from the Vagrant VM
    elk.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "elk.yml"
    end
  end

  config.vm.define "web" do |web|
    web.vm.network "forwarded_port", guest: 80, host: 8080
  end
end
