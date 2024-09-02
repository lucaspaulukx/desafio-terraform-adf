# Desafio: Implementação de Azure Data Factory em Ambiente Privado

## Objetivo

Este desafio tem como objetivo criar uma infraestrutura completa no Azure utilizando **Terraform**, garantindo que todo o ambiente seja **privado**. O desafio envolve a configuração de um **Azure Data Factory (ADF)** sincronizado com um repositório privado no **Azure DevOps**, a instalação de um **Integration Runtime (IR)** em uma máquina virtual Windows utilizando **Ansible**, e a criação de uma **pipeline automatizada** no ADF para processar arquivos em um Blob Storage.

## Requisitos

### Terraform
- **Azure Data Factory (ADF)**: Provisionado em uma rede privada e sincronizado com um repositório privado no Azure DevOps.
- **Virtual Machine**: Provisione uma máquina virtual Windows em uma VNet privada.
- **Blob Storage**: Criação e configuração para interação com o ADF.
- **Pipeline de Processamento**:
  - Criação de um arquivo no Blob Storage.
  - Edição do arquivo com o número da matrícula do usuário na Minsait.
  - Criação de um segundo arquivo com o valor editado.
- **Trigger**: Configuração de uma trigger para executar a pipeline automaticamente às 9h da manhã todos os dias.
- **Integration Runtime (IR)**: Instalação na máquina virtual Windows e configuração para conectar-se ao ADF utilizando redes privadas.

### Azure DevOps
- **Pipeline Privado**: Sincronização do ADF com um repositório Git privado e automação do deployment das pipelines do ADF.

## Estrutura do Desafio

### 1. Provisionamento da Infraestrutura
- Criação do Azure Data Factory em uma sub-rede privada, sem exposição a endpoints públicos.
- Provisão de uma máquina virtual Windows em uma VNet privada, sem IP público.
- Configuração de uma VNet e sub-redes para garantir comunicação privada.
- Criação de um Blob Storage na VNet.

### 2. Sincronização com Azure DevOps
- Configuração do ADF para sincronizar com um repositório privado no Azure DevOps usando Terraform.
- Configuração do pipeline no Azure DevOps para deploy automático, assegurando que as operações ocorram dentro da rede privada.

### 3. Pipeline de Processamento de Arquivos
- Criação da pipeline no ADF utilizando Terraform que:
  - Cria um arquivo no Blob Storage.
  - Edita o arquivo com o número da matrícula do usuário na Minsait.
  - Cria um segundo arquivo com o valor editado.
- Configuração de uma trigger para execução diária às 9h da manhã.

### 4. Instalação do Integration Runtime
- Utilização de Ansible para conectar-se à máquina virtual Windows e instalar o IR.
- Configuração do IR para conectá-lo ao ADF sem expor endpoints públicos.

### 5. Automação e Inicialização
- Inicialização completa do processo com um único comando do Terraform, que provisiona os recursos e executa os scripts do Ansible.

## Ponto Extra
- Implementação de monitoramento e alertas dentro da rede privada.

## Documentação
Inclua um **README** detalhado explicando:
- Como inicializar a infraestrutura.
- Verificar a configuração dos componentes.
- Garantir que todo o tráfego permaneça privado.
- Exemplos de pipelines e scripts de configuração.
- Detalhes sobre o processo de criação e edição dos arquivos no Blob Storage.
