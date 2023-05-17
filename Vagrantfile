Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.define "soube2" do |soube2|
    soube2.vm.hostname = "soube2"
    soube2.vm.network "private_network", ip: "192.168.56.111"
    soube2.vm.provider :virtualbox do |v|
      v.memory = 2048
      v.cpus = 1
      v.name = "soube2"
    end
    soube2.vm.provision "ansible" do |ansible|
      ansible.playbook = "./apps.yml"
      ansible.become = true
    end
  end
end

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.define "soube1" do |soube1|
    soube1.vm.hostname = "soube1"
    soube1.vm.network "private_network", ip: "192.168.56.112"
    soube1.vm.provider :virtualbox do |v|
      v.memory = 2048
      v.cpus = 1
      v.name = "soube1"
    end
    soube1.vm.provision "ansible" do |ansible|
      ansible.playbook = "./haproxy.yml"
      ansible.become = true
    end
  end
end