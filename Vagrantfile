# -*- mode: ruby -*-
# vi: set ft=ruby :

$script = <<SCRIPT
echo Install epel-release
sudo yum install -y epel-release > /dev/null 2>&1
echo Install gcc libffi-devel \
openssl-devel python-devel python-pip
sudo yum install -y gcc libffi-devel \
openssl-devel python-devel python-pip > /dev/null 2>&1
echo Install ansible via pip
sudo pip install ansible > /dev/null 2>&1
echo Install cryptography via pip
sudo pip install cryptography > /dev/null 2>&1
SCRIPT

Vagrant.configure(2) do |config|
  config.vm.box = "boxcutter/centos72"
  config.vm.provision "shell",
    inline: $script
  #Workaround for Vagrant v1.8.5 bug
  #https://github.com/mitchellh/vagrant/issues/7610
  config.ssh.insert_key = false
end