Vagrant.configure("2") do |config|

  config.vm.define "host1" do |vm1|
    config.ssh.private_key_path = "/home/dell/Ansible/.ssh/id_rsa"
    config.ssh.verify_host_key = false
    config.ssh.forward_agent = true
    config.ssh.username = "vagrant"
    config.ssh.password = "vagrant"
    vm1.vm.hostname = "host1"
    vm1.vm.synced_folder ".", "/home/vagrant/"
    vm1.vm.box = "bento/ubuntu-22.04"
    # vm1.ssh.username = "vagrant"  # SSH username
    # vm1.ssh.password = "vagrant"  # Set SSH password
    vm1.vm.provision "shell", inline: "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/' /etc/ssh/sshd_config && sudo systemctl restart sshd"
    vm1.vm.provider "virtualbox" do |vb|
      vb.name = "host1"
      vb.memory = "8192"
      vb.cpus = 4
      vb.gui = false
    end
  end

  config.vm.define "host2" do |vm2|
    config.ssh.private_key_path = "/home/dell/Ansible/.ssh/id_rsa"
    config.ssh.verify_host_key = false
    config.ssh.forward_agent = true
    config.ssh.username = "vagrant"
    config.ssh.password = "vagrant"
    vm2.vm.hostname = "host2"
    vm2.vm.synced_folder ".", "/home/vagrant/"
    vm2.vm.box = "bento/ubuntu-22.04"
    # vm2.ssh.username = "vagrant"
    # vm2.ssh.password = "vagrant"  # Set SSH password
    vm2.vm.provision "shell", inline: "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/' /etc/ssh/sshd_config && sudo systemctl restart sshd"
    vm2.vm.provider "virtualbox" do |vb|
      vb.name = "host2"
      vb.memory = "8192"
      vb.cpus = 4
      vb.gui = false
    end
  end

end

