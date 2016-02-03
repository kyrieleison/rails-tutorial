Vagrant.configure(2) do |config|
  config.vm.box = "nrel/CentOS-6.5-x86_64"
  config.vm.network "private_network", ip: "192.168.35.10"
  config.vm.hostname = "local.dev.com"
  config.ssh.forward_agent = true

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "1024"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.limit = 'all'
    ansible.inventory_path = "ansible/hosts"
    ansible.playbook = "ansible/build.yml"
    ansible.sudo = true
  end
end
