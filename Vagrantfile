Vagrant.configure("2") do |config|
  config.vm.define "db" do |ubun|
  ubun.vm.box = "sagiru/buster-amd64"
  ubun.vm.network "private_network", ip: "192.168.122.100", lxc__bridge_name: 'virbr0'
  ubun.vm.provider :lxc do |lxc|
    lxc.container_name = "servidordb"
  end
 end
  config.vm.define "servidores_web" do |ubun|
  ubun.vm.box = "sagiru/buster-amd64"
  ubun.vm.network "private_network", ip: "192.168.122.101", lxc__bridge_name: 'virbr0'
  ubun.vm.provider :lxc do |lxc|
    lxc.container_name = "servidores_web"
  end
 end
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "lxc-ansible/site.yaml"
  end
end
