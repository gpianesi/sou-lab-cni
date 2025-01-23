Vagrant.configure("2") do |config|
  config.vm.box = "generic/rocky9"
  config.vm.box_version = "4.3.12"
  # Create soufe1
  config.vm.define "soufe1" do |soufe1|
    soufe1.vm.network "private_network", ip: "192.168.55.20"
    config.vm.provider "virtualbox" do |v|
      v.memory = 2048
      v.cpus = 1
    end
  end
  # Create soube2
  config.vm.define "soube2" do |soube2|
    soube2.vm.network "private_network", ip: "192.168.55.21"
    config.vm.provider "virtualbox" do |v|
      v.memory = 2048
      v.cpus = 1
    end
  end
  # Launch Ansible Playbook
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "./deploy.yml"
    ansible.inventory_path = "./inventory"
  end 
end
