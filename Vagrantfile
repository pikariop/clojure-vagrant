Vagrant.require_version ">= 1.4"
Vagrant.configure("2") do |config|

    config.vm.define :megatunkki do |config|

        config.vm.synced_folder ".", "/vagrant", :nfs => true
        config.vm.box = "trusty64"
        config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
        config.vm.network :private_network, ip: "192.168.1.1"
        config.vm.hostname = "megatunkki"

        config.vm.provider "virtualbox" do |vb|
            vb.customize ["modifyvm", :id, "--memory", "1024"]
        end

        config.vm.provision :ansible do |a|
            a.playbook = "playbook.yml"
            a.inventory_path = "ansible_hosts"
        end
    end
end
