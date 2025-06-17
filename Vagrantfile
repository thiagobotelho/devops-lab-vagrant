Vagrant.configure("2") do |config|
  config.vm.box = "fedora/41-cloud-base"
  config.vm.hostname = "terminal-test"

  config.vm.provider :libvirt do |libvirt|
    libvirt.memory = 2048
    libvirt.cpus = 2
  end

  config.vm.synced_folder ".", "/vagrant", type: "rsync"

  config.vm.provision "shell", inline: <<-SHELL
    sudo dnf install -y git curl wget zsh tmux fontconfig python3
    if [ ! -d "/home/vagrant/terminal-config" ]; then
      git clone https://github.com/thiagobotelho/terminal-config.git /home/vagrant/terminal-config
      chown -R vagrant:vagrant /home/vagrant/terminal-config
    fi
  SHELL
end