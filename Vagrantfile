VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "xenial_docker"
  config.vm.box_url = "https://github.com/jose-lpa/packer-ubuntu_lts/releases/download/v3.1/ubuntu-16.04.box"
  config.vm.define :dockervag01 do |dockervag01|
    dockervag01.vm.network :private_network, ip: "192.168.2.10"
    dockervag01.vm.host_name = "dockervag01"
  end
  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.cpus = 2
  end
end
