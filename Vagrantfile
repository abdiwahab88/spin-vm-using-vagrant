# vi: set ft=ruby :
Vagrant.configure("2") do |config| config.vm.define "managed-node" do |vm1|
    vm1.vm.hostname = "managed-node"
    vm1.vm.box = "bento/ubuntu-16.04"
    vm1.vm.network "private_network", type: "static", ip: "192.168.33.10" 
    #config.vm.network "private_network", type: "static", ip: "192.168.33.10"  
    vm1.vm.provider "virtualbox" do |vb|
      vb.name = "managed-node"
      vb.gui = false
      vb.memory = "1024"
    end

    vm1.vm.provision "shell", run: "always", inline: <<-SHELL
        echo "Hello from the Managed node"
    SHELL
   # vm1.ssh.private_key_path = "~/.ssh/id_ed25519"
    #vm1.ssh.public_key_path = "~/.ssh/id_ed25519.pub"
  end

  config.vm.define "worker-node" do |vm2|
    vm2.vm.hostname = "worker-node"
    vm2.vm.box = "bento/ubuntu-16.04"
    vm2.vm.network "private_network", type: "static", ip: "192.168.33.20" 
    
    vm2.vm.provider "virtualbox" do |vb|
      vb.name = "worker-node"
      vb.gui = false
      vb.memory = "1024"
    end

    vm2.vm.provision "shell", run: "always", inline: <<-SHELL
        echo "Hello from the worker-node"
    SHELL
    #vm2.ssh.private_key_path = "~/.ssh/id_ed25519"
   # vm2.ssh.public_key_path = "~/.ssh/id_ed25519.pub"
  end
  
end
