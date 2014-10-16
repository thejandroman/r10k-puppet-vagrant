# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = '2'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # CentOS 6.5
  #config.vm.box = 'centos-6.5-x64-puppet'
  #config.vm.box_url = 'http://puppet-vagrant-boxes.puppetlabs.com/centos-65-x64-virtualbox-puppet.box'

  # Ubuntu 12.04
  #config.vm.box = 'ubuntu-12.04.2-x64-puppet'
  #config.vm.box_url = 'http://puppet-vagrant-boxes.puppetlabs.com/ubuntu-server-12042-x64-vbox4210.box'

  # Ubuntu 14.04
  config.vm.box = 'ubuntu/trusty64'

  #config.vm.network 'public_network', ip: '192.168.1.XXX'
  config.vm.hostname = 'thejandroman.kixeye.com'

  config.ssh.forward_agent

  config.vm.network 'forwarded_port', guest: 443, host: 8443
  config.vm.network 'forwarded_port', guest: 80, host: 8080

  # Configure RAM and CPU(s)
  config.vm.provider :virtualbox do |vb|
    vb.customize ['modifyvm', :id, '--memory', '2048']
    vb.customize ['modifyvm', :id, '--cpus', 1]
    vb.customize ['setextradata', :id, 'VBoxInternal2/SharedFoldersEnableSymlinksCreate/v-root', '1']
  end
end
