Vagrant.configure("2") do |config|

    config.vm.provider "virtualbox" do |vb|
      vb.name = "Maquina Ansible"
      vb.memory = 1024
        vb.cpus = 1
       end

     config.vm.box = "hashicorp/bionic64"
      config.vm.network "public_network"
      
      config.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt install -y software-properties-common
      sudo add-apt-repository --yes -update ppa:ansible/ansible
      sudo apt install -y ansible
    SHELL

      config.vm.provision "ansible" do |ansible|
        ansible.playbook = "update_ubuntu_packages.yml"
        ansible.playbook = "ansible/common/tasks/tasks/main.yml"
 
      end
    end
