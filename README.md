# 🧪 devops-lab-vagrant

Ambiente de laboratório com Vagrant para testar o setup DevOps.

Cria uma máquina Fedora 44 com libvirt e aplica automaticamente o perfil
`core` do repositório
[`terminal-config`](https://github.com/thiagobotelho/terminal-config).

## 🔧 Requisitos

- [Vagrant](https://www.vagrantup.com/)
- [libvirt/KVM](https://vagrant-libvirt.github.io/)
- plugin `vagrant-libvirt`

## 🚀 Como usar

```bash
git clone https://github.com/thiagobotelho/devops-lab-vagrant.git
cd devops-lab-vagrant
vagrant up
```

Após o provisionamento:

```bash
vagrant ssh
cd ~/terminal-config
python3 install.py
```

## 📦 Conteúdo

- Fedora 44 Cloud Base
- Instalação automatizada de ZSH, Oh-My-Zsh, Powerlevel10k
- TMUX com TPM e plugins customizados
- Nerd Fonts localmente aplicadas
- Estrutura pronta para testes e validações de ambiente terminal DevOps
