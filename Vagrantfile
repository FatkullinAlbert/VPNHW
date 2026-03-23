Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/jammy64"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.cpus = 1
  end

  config.vm.define "server" do |server|
    server.vm.hostname = "server.loc"
    server.vm.network "private_network", ip: "192.168.56.10"
  end

  config.vm.define "client" do |client|
    client.vm.hostname = "client.loc"
    client.vm.network "private_network", ip: "192.168.56.20"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
    ansible.limit = "all"
    ansible.compatibility_mode = "2.0"
  end
end
