#-*-mode:ruby-*-
#vi:setft=ruby:

VAGRANTFILE_API_VERSION='2'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box='ubuntu/trusty64'

  config.vm.define 'devstack' do |devstack|
    devstack.vm.hostname="devstack"
    devstack.vm.provider:libvirt do |lv|
        lv.memory=8192
        lv.cpus=2
    end
    config.vm.provider "virtualbox" do |vb|
      vb.name = "devstack"
      vb.memory = 8192
      vb.cpus = 2
    end
    devstack.vm.network 'private_network',ip:'10.20.0.15' #Itgoesto15.
    devstack.vm.provision "ansible" do |ansible|
        ansible.playbook = "ansible/playbook.yml"
    end
  end
end

