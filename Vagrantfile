Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.hostname = "intro-to-ansible"

  config.vm.network "private_network", ip: "192.168.33.20"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "512"
  end

  config.vm.provision "file", source: "foobar", destination: "/home/ubuntu/foobar"
  config.vm.provision "file", source: "ssh/intro_to_ansible", destination: "/home/ubuntu/intro_to_ansible"
  config.vm.provision "file", source: "ssh/intro_to_ansible.pub", destination: "/home/ubuntu/intro_to_ansible.pub"
  config.vm.provision "shell", inline: "sudo cp /home/ubuntu/intro_to_ansible* /root/.ssh"
  config.vm.provision "shell", inline: "sudo chmod 600 /root/.ssh/intro_to_ansible*"
  config.vm.provision "shell", inline: "sudo cat /root/.ssh/intro_to_ansible.pub >/root/.ssh/authorized_keys"
  config.vm.provision "shell", inline: "sudo chmod 600 /root/.ssh/authorized_keys"
  config.vm.provision "shell", inline: "rm -f /home/ubuntu/intro_to_ansible*"
  config.vm.provision "shell", inline: "apt-get install -y ansible"

end
