app = ENV['APP'] || 'ansible'


Vagrant.configure("2") do |config|
  config.vm.hostname = "vagrant"
  config.vm.box = "bento/ubuntu-20.04"
  config.vm.define "vagrant-#{app}"
  config.vm.provider "virtualbox" do |vb|
    # Customize the amount of memory on the VM:
    vb.memory = "2048"
    vb.name = "vagrant-#{app}"
  end
  config.vm.network :private_network, ip: "192.168.56.168"
  config.vm.provision "ansible" do |ansible| 
    ansible.playbook="vagrant_provision.yml" 
    ansible.extra_vars = {
    } 
  end 

end
