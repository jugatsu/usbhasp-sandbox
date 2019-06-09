Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |v|
    v.memory = 512
    v.cpus = 1
  end
  config.vm.box = "bento/ubuntu-18.04"
  config.vm.synced_folder "./provisioning/", "/srv/provisioning"
  config.vm.network "private_network", ip: "192.168.43.10"
  config.vm.provision "ansible_local" do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "/srv/provisioning/main.yml"
    ansible.install_mode = "pip"
    ansible.version = "2.8.0"
  end
end
