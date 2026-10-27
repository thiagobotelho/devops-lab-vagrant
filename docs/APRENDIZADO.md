# Provisionamento com Vagrant

## O que observar

Vagrantfile define box, memória, CPU, pastas e provisionamento. A rede da VM não deve ser confundida com a rede do host. Use vagrant validate antes de vagrant up. Em VM descartável, rode vagrant provision novamente e confira ausência de efeitos duplicados. Confirme a referência do terminal-config antes de instalar.

## Roteiro de leitura e validação

1. Leia o README e identifique o componente que recebe a configuração.
2. Confira namespaces, seletores, portas, identidades e dependências nos exemplos.
3. Ajuste apenas os campos necessários em um ambiente isolado; não use credenciais de produção.
4. Valide sintaxe e contratos locais antes de aplicar. Registre o resultado real separado deste guia.
5. Execute um caso permitido e um caso negado, conferindo a causa da resposta.
6. Defina reversão por recurso/arquivo e preserve dados persistentes antes de mudanças.

Os comentários dos manifests explicam escolhas; não comprovam disponibilidade do componente. Exemplos fora de entradas Kustomize não são implantados automaticamente.
