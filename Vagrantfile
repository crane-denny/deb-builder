# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "craneworks/jessie"
  config.vm.box_check_update = false
  config.ssh.forward_agent = true

  config.vm.provision "file", source: "#{ENV['HOME']}/.gnupg/pubring.gpg", destination: "/home/vagrant/.gnupg/pubring.gpg"
  config.vm.provision "file", source: "#{ENV['HOME']}/.gnupg/secring.gpg", destination: "/home/vagrant/.gnupg/secring.gpg"
  config.vm.provision "file", source: "#{ENV['HOME']}/.gnupg/trustdb.gpg", destination: "/home/vagrant/.gnupg/trustdb.gpg"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/main.yml"
  end

end
