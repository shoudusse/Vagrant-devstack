#-*-mode:ruby-*-
#vi:setft=ruby:

VAGRANTFILE_API_VERSION='2'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box='ubuntu/trusty64'
  config.vm.provider "virtualbox" do |v|
    v.name = "devstack"
    v.memory = 8192
    v.cpus = 2
  end
  config.vm.define 'devstack' do |devstack|
    devstack.vm.hostname="devstack"
    devstack.vm.network 'private_network',ip:'10.20.0.15' #Itgoesto15.
    devstack.vm.provision "ansible" do |ansible|
        ansible.playbook = "ansible/playbook.yml"
    end
  end
end

