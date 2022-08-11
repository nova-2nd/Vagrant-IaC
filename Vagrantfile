Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--graphicscontroller", "vmsvga"]
    v.customize ["modifyvm", :id, "--nested-hw-virt", "on"]
  end
  config.vm.provider "hyperv" do |h|
    h.enable_virtualization_extensions = true
    #h.differencing_disk = true
    end
  config.vm.box = "generic/debian11"

  config.vm.define "master" do |subconfig|
    subconfig.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "dist-files/master_playbook.yaml"
    end
  end
end
