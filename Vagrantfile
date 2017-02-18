Vagrant.configure("2") do |config|
  config.vm.define "ftpserver" do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.box_url = "https://atlas.hashicorp.com/ubuntu/boxes/trusty64"
    config.vm.hostname = "ftpserver"
    
    config.vm.network :"public_network"
    
   config.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "ftpserver"]
    end
    config.vm.provision :ansible do |ansible|
      ansible.playbook = "tasks/main.yml"
   end
  end
end
