Vagrant.configure("2") do |config|
  config.vm.define "master" do |subconfig|
    config.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--graphicscontroller", "vmsvga"]
    end

    subconfig.vm.box = "generic/debian11"

    subconfig.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "master_playbook.yaml"
    end
  end
end
