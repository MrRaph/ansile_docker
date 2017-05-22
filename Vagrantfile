VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "xenial_docker"
  config.vm.box_url = "https://github.com/jose-lpa/packer-ubuntu_lts/releases/download/v3.1/ubuntu-16.04.box"

  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.cpus = 2
  end

  config.vm.define :dockervag01 do |dockervag01|
    dockervag01.vm.network :private_network, ip: "192.168.2.11"
    dockervag01.vm.host_name = "dockervag01"
  end

  config.vm.define :dockervag02 do |dockervag02|
    dockervag02.vm.network :private_network, ip: "192.168.2.12"
    dockervag02.vm.host_name = "dockervag02"
  end

  config.vm.define :dockervag03 do |dockervag03|
    dockervag03.vm.network :private_network, ip: "192.168.2.13"
    dockervag03.vm.host_name = "dockervag03"
  end

  config.vm.define :dockervagwork01 do |dockervagwork01|
    dockervagwork01.vm.network :private_network, ip: "192.168.2.21"
    dockervagwork01.vm.host_name = "dockervagwork01"
  end

  config.vm.define :dockervagwork02 do |dockervagwork02|
    dockervagwork02.vm.network :private_network, ip: "192.168.2.22"
    dockervagwork02.vm.host_name = "dockervagwork02"
  end

  config.vm.define :dockervagwork03 do |dockervagwork03|
    dockervagwork03.vm.network :private_network, ip: "192.168.2.23"
    dockervagwork03.vm.host_name = "dockervagwork03"
  end

  $script = <<SCRIPT
echo 'ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC06QayxKvqaCOHNlDCl0/UlGoPh+apVSTUbBQfkF0TykOotp8sXlViFIN1ZidGMjUUgEpFB7xStKmjWhHY2TNuggcUR7St2lHVeREqf4aPMMzKqnuA6rVsfHKGUL2yWen+JhFFohSNgYNJK1Es+/dZvp2FJ1k2EAxzD7+g7MJvWw9CA3T8KRJUNdajsJgHDFnwfF6L0LvfTKBl77wX6yvLALgr4iGKJ4I/JQdQnicP8A71OMTFNHv8FZGkPez3d05JgjIcI7U4/7KYznBHdMgN+mJb9ZxgPzUzdDhI415M3qhu3pOwd5xoIL+t3mQPa/bPN5w4zbq24PbMP8xPPrbh rcharrat@FR-TWSI-92' >> /home/vagrant/.ssh/authorized_keys
SCRIPT

  config.vm.provision "shell", inline: $script
end
