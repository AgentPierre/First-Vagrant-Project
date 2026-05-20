# First-Vagrant-Project Vagrantfile 
# A development environment mirroring production Ubunut 22.04

Vagrant.configure("2") do |config|
    # OS box: Ubunut 22.04 LTS (Jammy)
    config.vm.box = "ubuntu/jammy64"
    config.vm.boot_timeout = 300

    # VM resources 
    config.vm.provider "virtualbox" do |vb| 
        vb.memory = 2048
        vb.cpus = 2 
    end

    # Port mapping 
    config.vm.network "forwarded_port", guest: 8000, host: 8000

    # Shared folder
    config.vm.synced_folder ".", "/vagrant"
end
