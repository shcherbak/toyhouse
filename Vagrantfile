# -*- mode: ruby -*-
# vi: set ft=ruby :

unless Vagrant.has_plugin?("vagrant-vbguest")
  raise 'some-plugin is not installed! try: vagrant plugin install vagrant-vbguest'
end

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  # install Vagrant plugin for disk resize
  #required_plugins = %w( vagrant-vbguest vagrant-disksize )
  #_retry = false
  #required_plugins.each do |plugin|
  #    unless Vagrant.has_plugin? plugin
  #        system "vagrant plugin install #{plugin}"
  #        _retry=true
  #    end
  #end
  #
  #if (_retry)
  #    exec "vagrant " + ARGV.join(' ')
  #end

  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  #config.vm.box = "base"
  #
  # https://app.vagrantup.com/aspyatkin/boxes/ubuntu-16.04-server-amd64
  # A minimal Ubuntu 16.04.4 LTS Server installation built for VirtualBox 5.2.8 & Vagrant 2.0.3
  #config.vm.box = "aspyatkin/ubuntu-16.04-server-amd64"
  # https://app.vagrantup.com/debian/boxes/stretch64
  # debian/stretch64 Vagrant box
  config.vm.box = "debian/stretch64"
  #config.disksize.size = "10GB"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
  config.vm.network :forwarded_port, guest: 22, host: 2222, id: 'ssh'
  #config.vm.network :forwarded_port, guest: 80, host: 8080, id: 'http', host_ip: "127.0.0.1"
  #config.vm.network :forwarded_port, guest: 443, host: 8443, id: 'https', host_ip: "127.0.0.1"
  #config.vm.network :forwarded_port, guest: 3306, host: 13306, id: 'mysql', host_ip: "127.0.0.1"
  #config.vm.network :forwarded_port, guest: 9200, host: 19200, id: 'elasticsearch', host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"
  #config.vm.synced_folder "./app", "/var/www", id: "vagrant-root", :group=>'www-data', :mount_options=>['dmode=775,fmode=775']
  #config.vm.synced_folder "../startup-shop", "/var/www/startup-shop", id: "startup-shop", :group=>'www-data', :mount_options=>['dmode=775,fmode=775']

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
   config.vm.provider "virtualbox" do |vb|
     # Display the VirtualBox GUI when booting the machine
     #vb.gui = true
     # Customize the amount of memory on the VM:
     vb.memory = "2048"
   end
  #
  # View the documentation for the provider you are using for more
  # information on available options.
  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # Since an Ansible playbook can include many files, you may also collect the
  # related files in a directory structure like this:
  #
  # .
  # |-- Vagrantfile
  # |-- manifests
  # |   |-- default.pp
  config.vm.provision "shell" do |s|
    s.inline = "apt install puppet -y"
  end


  # $ vagrant --version
  # Vagrant 1.9.1
  # $ puppet --version
  # 4.8.2

  config.vm.provision "puppet" do |puppet|
    #puppet.manifests_path = "manifests"
    #puppet.manifest_file = "default.pp"
    puppet.environment_path = "./environments"
    puppet.environment = "vagrant"
    puppet.options = "--verbose --debug"
  end

end
