# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
#  config.vm.box_url = "http://files.vagrantup.com/trusty64.box"
  config.vm.provider :virtualbox do |vb|
	vb.name = "Atlassian Bamboo Server VM"
  end

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network :private_network, ip: "192.168.23.3", virtualbox__intnet: "int-bamboo"
  # Uncomment the below line and comment the above line to open this VM on the local network
  #config.vm.network "public_network", type: "dhcp", :bridge => 'em1'

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  config.vm.synced_folder "./", "/vagrant", id: "vagrant-root", :owner=> 'vagrant', :group=>'www-data', :mount_options => ['dmode=775', 'fmode=775']

  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--cpus", "2"]
    v.customize ["modifyvm", :id, "--memory", "2048"]
  end


  # View the documentation for the provider you're using for more
  # information on available options.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/server-playbook.yml"
#    ansible.raw_arguments  = "--ask-vault-pass"
    ansible.inventory_path = "vagrant_ansible_inventory_default"
  end

end
