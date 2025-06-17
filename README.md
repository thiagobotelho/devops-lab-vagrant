# 🧪 devops-lab-vagrant

Ambiente de laboratório com Vagrant para testar o setup DevOps.

Cria uma máquina Fedora 41 provisionada automaticamente com ZSH, TMUX, fontes Nerd Font e personalizações do repositório [`terminal-config`](https://github.com/thiagobotelho/terminal-config). Também pode ser utilizado para experimentar e validar outras ferramentas e configurações relacionadas a infraestrutura e produtividade em terminal.

## 🔧 Requisitos

- [Vagrant](https://www.vagrantup.com/)
- [VirtualBox](https://www.virtualbox.org/) ou [libvirt](https://vagrant-libvirt.github.io/)

## 🚀 Como usar

```bash
git clone https://github.com/thiagobotelho/devops-lab-vagrant.git
cd devops-lab-vagrant
vagrant up --provider=libvirt  # ou --provider=virtualbox
```

Após o provisionamento:

```bash
vagrant ssh
cd ~/terminal-config
python3 install.py
```

## 📦 Conteúdo

- Fedora 41 Cloud Base
- Instalação automatizada de ZSH, Oh-My-Zsh, Powerlevel10k
- TMUX com TPM e plugins customizados
- Nerd Fonts localmente aplicadas
- Estrutura pronta para testes e validações de ambiente terminal DevOps
