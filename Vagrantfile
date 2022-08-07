Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--graphicscontroller", "vmsvga"]
  end
  config.vm.box = "generic/debian11"

  config.vm.define "master" do |subconfig|
    subconfig.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "master_playbook.yaml"
    end
  end
end
