Vagrant.configure("2") do |config|
  config.vm.box = "fedora/44-cloud-base"
  # Escolher a versão no catálogo antes de provisionar; não seguir releases móveis.
  config.vm.box_version = ENV.fetch("VAGRANT_BOX_VERSION") { abort "Defina VAGRANT_BOX_VERSION com uma versão libvirt existente da box escolhida" }
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
    # Referência aprovada para repetir o provisionamento sem seguir main implicitamente.
    sudo -u vagrant git -C /home/vagrant/terminal-config fetch origin 1c1d6180359b230c5cc624724654a834225a67e4
    sudo -u vagrant git -C /home/vagrant/terminal-config checkout --detach 1c1d6180359b230c5cc624724654a834225a67e4
    sudo -u vagrant python3 /home/vagrant/terminal-config/install.py --profile core
  SHELL
end
