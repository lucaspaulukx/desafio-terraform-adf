Desafio: Implementação de Azure Data Factory em Ambiente Privado com Ansible, Azure DevOps e Pipelines Automatizadas
Objetivo
Criar uma infraestrutura no Azure usando Terraform que inclui:

Azure Data Factory (ADF): Sincronizado com um repositório privado no Azure DevOps.
Integration Runtime (IR): Instalado em uma máquina virtual Windows em uma rede privada, usando Ansible.
Pipeline de Processamento de Arquivos: Criação e edição automatizada de arquivos no Blob Storage.
Automação Completa: Todo o processo deve ser inicializado e gerenciado via Terraform.
Ambiente Totalmente Privado: Toda a comunicação deve ocorrer em uma rede privada.
Requisitos
Terraform:

Provisionar o Azure Data Factory em uma rede privada.
Criar uma máquina virtual Windows em uma VNet privada.
Configurar a integração do ADF com um repositório privado no Azure DevOps.
Criar um Blob Storage e configurar o ADF para interagir com ele.
Implementar a pipeline que:
Crie um arquivo no Blob Storage.
Edite esse arquivo com o número da matrícula do usuário na Minsait.
Crie um segundo arquivo com esse valor.
Configurar uma trigger no ADF para executar essa pipeline às 9h da manhã todos os dias.
Ansible:

Instalar o Integration Runtime na máquina virtual Windows.
Configurar o IR para conectar-se ao Azure Data Factory usando redes privadas.
Azure DevOps:

Configurar um pipeline privado para sincronizar o Azure Data Factory com um repositório Git, acessível apenas dentro da rede privada.
Automação do deployment das pipelines do ADF, garantindo que a comunicação seja feita de forma privada.
Passos Detalhados
Provisionamento da Infraestrutura:

Crie o Azure Data Factory em uma sub-rede privada, sem exposição a endpoints públicos.
Provisione uma máquina virtual Windows em uma VNet privada, sem IP público.
Configure uma VNet e sub-redes para garantir que todas as comunicações sejam privadas.
Crie um Blob Storage na mesma VNet.
Sincronização com Azure DevOps:

Use Terraform para configurar o Azure Data Factory para sincronizar com um repositório privado no Azure DevOps.
Configure o pipeline no Azure DevOps para deploy automático, garantindo que todas as operações sejam realizadas dentro da rede privada.
Pipeline de Processamento de Arquivos:

Use Terraform para criar a pipeline no ADF que:
Cria um arquivo no Blob Storage.
Edite esse arquivo com o número da matrícula do usuário na Minsait.
Crie um segundo arquivo com o valor editado no mesmo Blob Storage.
Configure uma trigger para que essa pipeline seja executada automaticamente às 9h da manhã todos os dias.
Instalação do Integration Runtime:

Utilize Ansible para conectar-se à máquina virtual Windows usando uma rede privada.
Instale e configure o Integration Runtime, conectando-o ao Azure Data Factory sem expor endpoints públicos.
Automação e Inicialização:

Garanta que todo o processo possa ser inicializado a partir de um único comando do Terraform, que provisionará todos os recursos necessários em um ambiente privado e disparará os scripts do Ansible.
Documentação:

O desafio deve incluir um README detalhado, explicando como inicializar a infraestrutura, verificar a configuração dos componentes e como garantir que todo o tráfego permaneça privado.
Incluir exemplos de pipelines, scripts de configuração e detalhes sobre o processo de criação e edição dos arquivos no Blob Storage.
Ponto Extra
Implementar soluções de monitoramento e alertas dentro da rede privada.
Este desafio proporciona uma experiência completa de infraestrutura como código e automação, ao mesmo tempo em que garante um ambiente seguro e privado.
