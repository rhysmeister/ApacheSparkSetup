Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"

  config.vm.network "private_network", ip: "192.168.44.214"
  config.vm.hostname = "spark"
  # Add 4GB RAM
  config.vm.provider :virtualbox do |vb|
    vb.customize [
      "modifyvm", :id,
      "--name", "spark",
      "--memory", "4192"
    ]
  end

 system("mkdir -p vm_vagrant_home")
 #config.vm.synced_folder "vm_vagrant_home/", "/home/vagrant"

 config.vm.provision :ansible do |ansible|
   ansible.playbook = "spark.yaml"
 end

end
