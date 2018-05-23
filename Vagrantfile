Vagrant.configure("2") do |config|
  config.vm.box = "jeqo/oracle-jdk-8-centos7"
  config.vm.box_version = "8.66.20160116222952"

  config.vm.hostname = "spark"

  # Add 4GB RAM
 config.vm.provider :virtualbox do |vb|
   vb.customize [
     "modifyvm", :id,
     "--name", "spark",
     "--memory", "4192"
   ]
 end

 config.vm.provision :ansible do |ansible|
   ansible.playbook = "spark.yaml"
 end

end
