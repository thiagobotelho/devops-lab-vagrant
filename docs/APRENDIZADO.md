# Provisionamento com Vagrant


Vagrantfile define box, memória, CPU, pastas e provisionamento. A rede da VM não deve ser confundida com a rede do host. Use vagrant validate antes de vagrant up. Em VM descartável, rode vagrant provision novamente e confira ausência de efeitos duplicados. Confirme a referência do terminal-config antes de instalar.

## Limite da automação

Este projeto prepara a VM e delega os dotfiles ao terminal-config. Para corrigir o terminal, altere a referência desse componente, sem copiar seu instalador para o Vagrantfile. `vagrant validate` verifica a configuração; conectividade e idempotência exigem `vagrant up`, `vagrant ssh` e uma segunda execução de provisionamento.
