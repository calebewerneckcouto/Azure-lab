# Azure-lab

# 🚀 Guia Azure: Fundamentos, Configurações e Boas Práticas

Este documento reúne conteúdos essenciais estudados nas aulas sobre Microsoft Azure, incluindo modelos de nuvem, criação de recursos, conceitos de infraestrutura e exemplos práticos como hospedagem escalável de WordPress.

---

## 🌩️ Modelos de Serviço em Nuvem

### 🔹 SaaS (Software como Serviço)
- Software pronto para uso, gerenciado pelo provedor.
- Ex: Microsoft 365, Gmail
- ✅ *"Os usuários pagam pelo software que utilizam em modelo de assinatura."*

### 🔹 PaaS (Platform as a Service)
- Plataforma para desenvolvimento sem gerenciar infraestrutura.
- Ex: Azure App Services, Azure Container Instances
- ✅ *"Os usuários podem criar e implantar um aplicativo sem se preocupar com a infraestrutura."*

### 🔹 IaaS (Infrastructure as a Service)
- Infraestrutura como serviço, você gerencia VMs, rede, SO.
- Ex: Azure Virtual Machines
- ✅ *"O cliente é responsável por configurar e manter o sistema operacional e aplicativos."*

---

## 📊 SLA (Acordos de Nível de Serviço) no Azure

| SLA         | Tempo de inatividade estimado por semana |
|-------------|------------------------------------------|
| 99%         | 1h 40min                                  |
| 99,9%       | 10min                                     |
| 99,95%      | 5min                                      |
| 99,99%      | 1min                                      |
| 99,999%     | 6 segundos                                |

---

## 🧠 Modelo de Responsabilidade Compartilhada

| Ambiente | Responsável |
|----------|-------------|
| On-premises | Cliente |
| IaaS | Cliente: SO, Aplicativos • Azure: Infraestrutura |
| PaaS | Azure gerencia infra e middleware |
| SaaS | Azure gerencia tudo (infra, app, dados) |

---

## 🌍 Estrutura Global do Azure

- **Região**: Conjunto de datacenters geograficamente próximos.
- **Zona de Disponibilidade**: Datacenters independentes em uma região.
- **Pares de Região**: Redundância entre regiões.
- **Geografia**: Conjunto de regiões de um mesmo país/região legal.

Exemplo:
- Brasil: São Paulo (Sul do Brasil) e Rio de Janeiro (Backup/Zona de Recuperação)
- Tour virtual em datacenters: [https://infrastructure.microsoft.com](https://infrastructure.microsoft.com)

---

## 🧱 Grupos de Recursos

- Contêiner lógico para agrupar recursos.
- ✅ "Os recursos podem existir em apenas um grupo de recursos."
- ❌ "Os grupos de recursos podem conter apenas recursos de uma mesma região." (Incorreta)

---

## 🔐 IAM - Controle de Acesso (Azure Role-Based Access Control)

- Controle de quem pode acessar, visualizar ou modificar recursos.
- Definido por:
  - **Usuário/Grupo**
  - **Função (Role)**
  - **Escopo (Grupo de recurso, recurso individual, etc.)**

---

## 🕸️ Rede Virtual no Azure (VNet)

- Isolamento de rede dentro da nuvem.
- Sub-redes, grupos de segurança, roteamento personalizado.

✅ **ExpressRoute**: Extende redes locais para o Azure por meio de conexão privada (fora da internet pública).

---

## 🖥️ Máquinas Virtuais (VMs)

### ✅ Criando uma VM Otimizada no Azure – Passo a Passo

1. Acesse o portal: https://portal.azure.com
2. Vá em **Máquinas Virtuais > Criar nova**
3. Preencha:
   - **Nome da VM**
   - **Região** e **Sistema Operacional** (ex: Windows Server 2019 Datacenter)
   - **Tamanho da VM** (escolha com base em carga de trabalho)
   - **Tipo de disco** (SSD, Standard HDD, etc.)
4. Configurar:
   - **Rede virtual e sub-rede**
   - **IP público ou não**
   - **Abertura de portas (RDP, HTTP, etc.)**
   - **Disco de dados adicional (opcional)**
5. Validar e Criar

### 🧪 Validando Modelos de VM
- Use a calculadora: https://azure.microsoft.com/en-us/pricing/calculator/
- Tipos comuns:
  - **B-series**: econômicas, ideais para testes
  - **D-series**: balanceadas
  - **E-series**: otimizadas para memória
  - **F-series**: otimizadas para CPU

---

## 🌐 Exemplo Prático: Hospedagem Escalável de WordPress no Azure

1. Vá em **Marketplace > WordPress on Ubuntu**
2. Configure:
   - Nome da instância
   - Criar novo grupo de recursos
   - Criar novo servidor MySQL
3. Habilitar **Autoescalonamento**
4. Configurar backup, alertas, SSL e monitoramento

---

## 💾 Criando Conta de Armazenamento no Azure

1. Vá em **Armazenamento > Criar**
2. Defina:
   - Nome único
   - Região
   - Tipo de redundância (LRS, GRS, etc.)
3. Escolher:
   - Tipo de desempenho (Standard ou Premium)
   - Tipo de conta: BlobStorage, FileStorage, etc.
4. Criar contêiner (ex: `imagens`, `backups`) e definir permissões (privado, público)

---

## 🛢️ Criando Banco de Dados SQL no Azure

1. Vá em **SQL Databases > Criar novo**
2. Nome do banco, grupo de recursos
3. Criar **novo servidor SQL**
   - Nome, login, senha, localização
4. Escolher tamanho, DTUs/vCores
5. Configurar firewall para IP local (permitir acesso)
6. Criar banco de dados

---

## 📦 Contêineres vs VMs

| Recurso           | VM                           | Contêiner                             |
|------------------|------------------------------|----------------------------------------|
| Sistema Operacional | Cada VM tem o seu próprio SO | Compartilham o SO do host             |
| Início            | Minutos                      | Segundos                               |
| Peso              | Mais pesado                  | Leve                                   |
| Isolamento        | Total                        | Parcial (usam o mesmo kernel)          |

---

## 🧠 Resumo das Questões e Respostas Importantes

- **Modelo SaaS**: "Os usuários pagam por assinatura do software."
- **Modelo PaaS**: "Permite criar aplicativos sem gerenciar a infraestrutura."
- **Modelo com mais flexibilidade**: ✅ **Nuvem Híbrida**
- **Azure Container Instances**: ✅ **PaaS**
- **Serviços de Aplicativos (App Services)**: ✅ Criar e escalar WebApps e APIs facilmente
- **Conjuntos de Disponibilidade**: ✅ Domínios de falha e atualização
- **Azure Space**: Satélites e conectividade global para ambientes remotos

---

📚 *Esse guia serve como base para revisões, provas de certificação (AZ-900) ou aplicação prática no dia a dia com Azure.*

---
