Vagrant.configure("2") do |config|
  config.vm.box = "generic/rocky9"
  config.vm.box_version = "4.3.12"

  vms = {
         "soufe1" => "192.168.55.20",
         "soube2" => "192.168.55.21"
	}

  vms.each do |name, ip|
   config.vm.define "#{name}" do |name|
    name.vm.network "private_network", ip: "#{ip}"
   config.vm.provider "virtualbox" do |v|
     v.memory = 2048
     v.cpus = 1
   end
  end

  end
  # Launch Ansible Playbook
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "./deploy.yml"
    ansible.inventory_path = "./inventory"
  end 
end
