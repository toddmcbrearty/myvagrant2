Vagrant.configure(2) do |config|
    config.vm.box = "stink"
    config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/saucy/current/saucy-server-cloudimg-amd64-vagrant-disk1.box"

    config.vm.network :private_network, ip: '33.33.33.10'
    config.vm.provision :shell, :path => "./bootstrap.sh"
    config.vm.provision :shell, :inline => "/etc/init.d/networking restart"
    config.vm.synced_folder ".", "/vagrant", nfs: true

    config.vm.provider :virtualbox do |vb|
        #vb.customize ["setextradata", :id, "VBoxInternal2/SharedFoldersEnableSymlinksCreate/v-root", "1"]
        vb.customize ["modifyvm", :id, "--memory", "1024"]
    end
end
