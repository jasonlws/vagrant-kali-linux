# -*- mode: ruby -*- 
# vi: set ft=ruby : 

ENV['VAGRANT_NO_PARALLEL'] = 'yes' 

Vagrant.configure(2) do |config| 

	config.vm.define "jasonlws-kali" do |kali| 

		kali.vm.hostname = "jasonlws-kali" 

		kali.vm.box = "kalilinux/rolling" 

		kali.vm.network "private_network", ip: "192.168.56.110", netmask: "255.255.255.0"

		kali.vm.network "forwarded_port", guest: 22, host: 2223, id: "ssh" #ssh

		kali.vm.box_check_update = false 

		kali.vm.synced_folder ".\\shared\\jasonlws-kali", "/root/jasonlws-kali"

		kali.vm.provision "shell", path: "config/kali-provision.sh"

		kali.vm.provider :virtualbox do |v| 

			v.name = "jasonlws-kali" 
			v.memory = 49152 # 48GB 
			v.cpus = 16 

		end 

	end 

end 