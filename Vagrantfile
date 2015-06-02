# -*- mode: ruby -*-
# vi: set ft=ruby :
VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define "ubuntu" do |guest|
    guest.vm.box = "ubuntu/trusty64"
    # guest.vm.network "public_network", ip: "10.0.0.2"
    guest.vm.network "public_network", bridge: "en0: Wi-Fi (AirPort)"
  end
  config.vm.provision :ansible do |ansible|
    ansible.groups = {
      "main" => ["ubuntu"]
    }
    ansible.playbook = "host.yml"
  end
end
