
Vagrant.configure("2") do |config|

    config.vm.provider :virtualbox do |v|
        v.name = "Linux-Gui"
        v.customize [
            "modifyvm", :id,
            "--name", "Sora",
            "--memory", 2096,
            "--ioapic", "on",
            "--cpus", 2,
        ]
    end

    config.vm.box = "debian/contrib-stretch64"
    config.vm.network    "private_network", ip: "192.168.0.88"
	config.vm.network    "forwarded_port", guest: 8000, host: 8000
    config.ssh.forward_agent = true
    config.vm.synced_folder ".", "/vagrant", create: true
	config.vm.synced_folder "~", "/home/vagrant/host-home", create: true
	
	
	# Deploy ansible on Machine and Deploy playbook
	  $script = <<SCRIPT
  	# Install Ansible dependencies on first run:
  	if [ ! -f /etc/ansible/hosts ]; then
  		 temp /etc/apt/sources.list
		sudo apt-get update
		sudo apt-get install -y software-properties-common
                sudo apt-get install -y git
		sudo apt-get install -y python-pip
		sudo pip install ansible
		# Create a simple inventory file for localhost:
		mkdir -p /etc/ansible
		echo "[local]" > /etc/ansible/hosts
		echo "localhost	ansible_connection=local" >> /etc/ansible/hosts
  	fi
  	cd /vagrant
  	# We want Ansible's output line by line:
  	export PYTHONUNBUFFERED=1
	
        # Download the Ansible Config files from your Repo 
        git clone git@github.com:wieczoreko/vagrant-ansible.git /home/vagrant/vagrant-ansible

  	# Run the actual playbook:
  	ansible-playbook /home/vagrant/ansible/playbook.yml
	#Display the Public Key to add it in Github
	echo "SSH PUBLIC KEY"
	cat /home/vagrant/.ssh/id_rsa.pub
SCRIPT

  config.vm.provision "shell", inline: $script
end
