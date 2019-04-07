# -*- mode: ruby -*-

# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.define "n9kv1" do |n9kv1|

    n9kv1.vm.box = "cisco/n9kv"

    # Dont try to change the insecure public key
    n9kv1.ssh.insert_key = false

    # Give the VM time to boot as Vagrant cannot tell when it is booted
    n9kv1.vm.boot_timeout = 180

    # Disable default host to guest synced folder
    n9kv1.vm.synced_folder '.', '/vagrant', disabled: true

    # Additional interfaces
    n9kv1.vm.network "private_network", ip: "192.168.1.2", auto_config: false, virtualbox__intnet: "nxosv_network1"
    n9kv1.vm.network "private_network", auto_config: false, virtualbox__intnet: "nxosv_network2"
    n9kv1.vm.network "private_network", auto_config: false, virtualbox__intnet: "nxosv_network3"
    n9kv1.vm.network "private_network", auto_config: false, virtualbox__intnet: "nxosv_network4"
    n9kv1.vm.network "private_network", auto_config: false, virtualbox__intnet: "nxosv_network5"
    n9kv1.vm.network "private_network", auto_config: false, virtualbox__intnet: "nxosv_network6"
    n9kv1.vm.network "private_network", auto_config: false, virtualbox__intnet: "nxosv_network7"

    # Make the interfaces promiscuous
    n9kv1.vm.provider :virtualbox do |vb|
            vb.customize ['modifyvm',:id,'--nicpromisc2','allow-all']
            vb.customize ['modifyvm',:id,'--nicpromisc3','allow-all']
            vb.customize ['modifyvm',:id,'--nicpromisc4','allow-all']
            vb.customize ['modifyvm',:id,'--nicpromisc5','allow-all']
            vb.customize ['modifyvm',:id,'--nicpromisc6','allow-all']
            vb.customize ['modifyvm',:id,'--nicpromisc7','allow-all']
            vb.customize ['modifyvm',:id,'--nicpromisc8','allow-all']

      end
  end
end