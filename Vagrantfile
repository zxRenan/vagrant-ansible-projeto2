Vagrant.configure("2") do |config|
  config.vm.define "vingadores" do |vingadores|
    vingadores.vm.box = "ubuntu/focal64"
    vingadores.vm.network "public_network", ip: "192.168.1.56"
    vingadores.vm.synced_folder "./", "/ansible"
    vingadores.vm.provider "virtualbox" do |v|
      v.name = "vingadores"
      v.memory = 2048
      v.cpus = 2
    end

    vingadores.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y ansible
      ansible-playbook --connection=local /ansible/playbook.yml
    SHELL
  end
end






