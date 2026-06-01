# Documentação de Negócio: Menu Consulta > Financeiro

## Visão Geral do Módulo

Este documento descreve as funcionalidades de negócio disponíveis no menu **Consulta > Financeiro** do sistema Gemco Varejo. O módulo é responsável por fornecer consultas e relatórios relacionados às operações financeiras da empresa, abrangendo tanto contas a pagar quanto contas a receber, além de integrações bancárias.

**Data de Geração:** Dezembro de 2024  
**Sistema:** Gemco Varejo - Módulo Financeiro  
**Arquitetura:** 3 Camadas (VB6)

---

## 1. Contas a Pagar

### 1.1. Consulta Cheques

**Objetivo:** Consultar e gerenciar cheques emitidos pela empresa para pagamento a fornecedores e demais credores.

#### Funcionalidades de Negócio:

**Filtros de Pesquisa:**
- **Banco:** Permite selecionar o banco emissor dos cheques
- **Número da Conta:** Filtra cheques por conta bancária específica
- **Favorecido:** Busca cheques por nome do beneficiário
- **Período:** Oferece duas opções de consulta:
  - Por Data de Emissão: quando o cheque foi emitido
  - Por Data de Pagamento: quando o cheque foi ou será compensado

**Situação dos Cheques:**
- **Emitido:** Cheques que foram criados no sistema
- **Confirmado:** Cheques que tiveram o pagamento confirmado
- **Cancelado:** Cheques que foram anulados

**Visualização de Dados:**
A consulta apresenta informações como:
- Número do cheque e da conta
- Banco e agência
- Data de emissão e data de pagamento
- Valor do cheque
- Favorecido (beneficiário)
- Histórico e observações
- Status atual
- Tipo de pagamento
- Número do lote
- Código da conta contábil

**Aba de Títulos Pagos:**
Exibe os títulos que foram quitados com cada cheque selecionado:
- Número e descrição do título
- Nome fantasia e emitente
- Valores: original, principal, desconto, multa, juros, abatimento e valor pago

#### Benefícios:
- Rastreabilidade completa dos pagamentos via cheque
- Controle de situação de cada cheque emitido
- Conciliação bancária facilitada
- Auditoria de pagamentos realizados

---

### 1.2. Consulta Lançamentos

**Objetivo:** Consultar todos os lançamentos de contas a pagar, permitindo análise detalhada das obrigações financeiras da empresa.

#### Funcionalidades de Negócio:

**Filtros Principais:**
- **Tipo de Negócio:** Classificação do tipo de operação comercial
- **Filial:** Permite filtrar por unidade específica (em ambientes multi-filial)
- **Tipo de Emitente:** Categoria do credor (Fornecedor, Transportadora, Cliente, etc.)
- **Título e Desdobro:** Identificação única do lançamento financeiro
- **Documento de Devolução:** Para rastrear devoluções e suas implicações financeiras
- **Período:** Data de vencimento ou data contábil
- **Evento:** Classificação do tipo de lançamento (compras, despesas, devoluções, etc.)
- **Origem:** Sistema ou módulo que originou o lançamento

**Informações Apresentadas:**
- **Dados do Título:**
  - Número do lançamento e título
  - Desdobramento (parcelas)
  - Filial de origem
  - Data contábil e data de vencimento

- **Dados do Emitente:**
  - Tipo (Fornecedor, Cliente, Transportadora)
  - Código com dígito verificador
  - Nome/Razão social

- **Valores Financeiros:**
  - Valor do lançamento
  - Valor total da obrigação

- **Dados Operacionais:**
  - Número da nota fiscal
  - Número do borderô
  - Evento de contas a pagar
  - Tipo de lançamento
  - Usuário responsável
  - Origem do lançamento
  - Data de digitação

- **Status e Controles:**
  - Flag de liberação de pagamento (Bloqueado/Liberado)
  - Descrição do bloqueio (quando aplicável)
  - Observações
  - Número e série de contrato financeiro
  - Grupo e cota de consórcio (quando aplicável)
  - Tipo de negócio
  - Código da empresa
  - Percentual de comissão permanente

**Estados de Lançamento:**
- **Normal:** Lançamento ativo e pendente
- **Bloqueado (BLO):** Lançamento impedido de ser pago por alguma restrição
- **Liberado:** Lançamento aprovado para pagamento

#### Benefícios:
- Visão completa das obrigações financeiras
- Controle de fluxo de caixa
- Gerenciamento de bloqueios e liberações de pagamento
- Rastreamento da origem de cada compromisso financeiro
- Auditoria de responsabilidades por usuário
- Integração com módulos de compras e estoque

---

### 1.3. Prévia de Encontro de Contas

**Objetivo:** Realizar a simulação de compensação entre valores a pagar e a receber de um mesmo emitente ou grupo econômico, permitindo a otimização do fluxo de caixa através da compensação de saldos.

#### Funcionalidades de Negócio:

**Tipos de Consulta:**
1. **Por Emitente Individual:**
   - Consulta de saldos de um fornecedor/cliente específico
   - Permite encontro de contas quando a mesma pessoa/empresa é tanto fornecedora quanto cliente

2. **Por Grupo Econômico:**
   - Consulta consolidada de empresas de um mesmo grupo
   - Permite compensação entre diferentes empresas do mesmo grupo

**Filtros de Pesquisa:**
- **Tipo de Consulta:**
  - Contas a Pagar: Exibe apenas obrigações
  - Contas a Receber: Exibe apenas direitos

- **Critério de Seleção:**
  - Por Emitente: Busca individual por fornecedor/cliente
  - Por Grupo Econômico: Busca consolidada

- **Identificação:**
  - Tipo de Emitente (Fornecedor, Cliente, etc.)
  - Código do emitente
  - Grupo Econômico
  - CPF/CNPJ

- **Título:** Número específico do título e desdobro (parcela)
- **Período:** Data de vencimento dos títulos

**Visualizações Disponíveis:**

**Aba 1 - Consulta Consolidada:**
Apresenta uma visão resumida com:
- Nome do emitente ou grupo econômico
- Tipo (Fornecedor/Cliente)
- Grupo econômico (quando aplicável)
- Saldo total (positivo = a receber, negativo = a pagar)

**Aba 2 - Detalhamento de Títulos:**
Dividida em duas seções:

**Contas a Pagar (Débito):**
- Filial
- Número do título e desdobro
- Valor a pagar
- Origem do lançamento
- Data de vencimento
- Nome do fornecedor

**Contas a Receber (Crédito):**
- Filial
- Número do título e desdobro
- Valor a receber
- Origem do lançamento
- Data de vencimento
- Nome do cliente

#### Cenários de Uso:

1. **Fornecedor que também é Cliente:**
   - Empresa compra matéria-prima de um fornecedor
   - O mesmo fornecedor compra produtos acabados da empresa
   - Sistema identifica possibilidade de compensação

2. **Grupo Econômico:**
   - Empresa A do grupo deve R$ 10.000,00
   - Empresa B do mesmo grupo tem R$ 15.000,00 a receber
   - Sistema consolida e mostra saldo líquido de R$ 5.000,00 a receber

3. **Otimização de Caixa:**
   - Reduz necessidade de movimentação financeira
   - Economiza tarifas bancárias
   - Agiliza processos de pagamento e recebimento

#### Benefícios:
- Otimização do fluxo de caixa
- Redução de custos operacionais e bancários
- Simplificação de processos financeiros
- Melhor gestão de relacionamento com fornecedores/clientes
- Visão consolidada de operações com mesma contraparte
- Conformidade legal para compensações

**Observação Importante:** A prévia não efetiva a compensação automaticamente. Serve como ferramenta de análise para que o gestor financeiro tome a decisão de realizar ou não o encontro de contas através das funcionalidades específicas de movimentação.

---

## 2. Contas a Receber

### 2.1. Consulta Lançamentos

**Objetivo:** Consultar e analisar todos os lançamentos de valores a receber, proporcionando controle completo dos direitos financeiros da empresa.

#### Funcionalidades de Negócio:

**Filtros de Pesquisa:**
- **Tipo de Negócio:** Classificação da operação comercial
- **Filial:** Seleção da unidade de negócio
- **Tipo de Cliente:** Categoria do devedor (Cliente, Fornecedor - devolução, Transportadora, etc.)
- **Título e Desdobro:** Identificação única do recebível
- **Documento de Devolução:** Rastreamento de devoluções
- **Período de Vencimento:**
  - Data início
  - Data fim
- **Evento de Contas a Receber:** Tipo de operação (venda, financiamento, etc.)
- **Origem:** Módulo que gerou o lançamento
- **Contratos:** Opção para incluir ou excluir lançamentos vinculados a contratos

**Informações Detalhadas:**

**Identificação do Lançamento:**
- Número do lançamento
- Número do título e desdobro
- Filial
- Data contábil
- Data de vencimento
- Data de recebimento (quando quitado)

**Dados do Cliente:**
- Tipo de cliente
- Código do cliente
- Nome/Razão social do cliente
- Estado e cidade
- Código de descrição do título

**Valores Financeiros:**
- Valor do lançamento
- Tipo de lançamento (Normal, Financiamento, Devolução, etc.)

**Informações Bancárias:**
- Código do portador
- Descrição do portador
- Código da conta
- Número do banco
- Número da agência
- Número da conta

**Dados Contratuais:**
- Número do contrato financeiro
- Série do contrato
- Tipo de contrato
- Número da cota de consórcio
- Número do grupo de consórcio

**Controles e Restrições:**
- Código de restrição de crédito
- Flag de negativação no Serasa
- Número da nota fiscal
- Observações

**Dados Operacionais:**
- Usuário responsável
- Origem do lançamento
- Data de movimento
- Tipo de negócio
- Código da empresa
- Sequência e data do arquivo
- Código da filial de recebimento
- Flag de grupo flexível

#### Estados do Lançamento:
- **Pendente:** Aguardando vencimento ou recebimento
- **Recebido:** Quitado total ou parcialmente
- **Negativado:** Enviado para protesto ou serviços de proteção ao crédito
- **Com Restrição:** Bloqueado por alguma política de crédito

#### Benefícios:
- Gestão eficiente da carteira de recebíveis
- Controle de inadimplência
- Rastreamento de origem dos valores a receber
- Integração com módulo de vendas e contratos
- Visão completa da situação de crédito dos clientes
- Suporte à tomada de decisão em política de crédito
- Controle de prazos e vencimentos

---

### 2.2. Recebimentos Não Integrados

**Objetivo:** Gerenciar recebimentos realizados que ainda não foram integrados ao módulo de Contas a Receber, permitindo a regularização de lançamentos financeiros pendentes.

#### Funcionalidades de Negócio:

**Contexto de Uso:**
Esta funcionalidade é utilizada quando recebimentos são registrados em outros módulos (principalmente PDV, Frente de Loja ou TEF) mas, por alguma razão, não foram automaticamente integrados ao módulo financeiro. Exemplos incluem:
- Vendas realizadas no PDV com problemas de comunicação
- Recebimentos de cartões pendentes de integração
- Pagamentos via convênio aguardando processamento
- Transações TEF que falharam na integração

**Filtros de Consulta:**
- **Filial:** Seleção da unidade onde o recebimento foi realizado
- **Período:** 
  - Data inicial
  - Data final
- **Linhas Selecionadas:** Opção para visualizar apenas itens marcados

**Informações Apresentadas:**

**Dados da Transação:**
- **Checkbox:** Permite selecionar registros para integração em lote
- **Observação:** Campo para incluir notas sobre o recebimento
- **Filial:** Unidade que realizou o recebimento
- **Cliente:** Identificação do comprador
- **Pedido:** Número do pedido de venda
- **Cupom:** Número do cupom fiscal
- **Série:** Série do documento
- **Tipo de Nota:** Classificação do documento fiscal
- **Valor:** Montante do recebimento
- **Status:** Situação atual do recebimento

**Dados Financeiros Ajustáveis:**
- **Evento:** Tipo de evento de contas a receber
  - Sistema permite alterar o evento padrão
  - Ao alterar o evento para um grupo de registros, o sistema automaticamente replica para todos os recebimentos do mesmo evento

- **Portador:** Instituição/forma de pagamento
  - Pode ser ajustado conforme necessidade
  - Replicação automática por evento similar ao campo evento

- **Origem:** Sistema de origem do recebimento

**Informações de Convênio/Conveniada:**
- **Flag Convênio:** Indica se é recebimento via convênio
- **Flag Conveniada:** Indica se é administradora de cartão
- **Conveniada:** Nome da administradora de cartão (Cielo, Rede, etc.)
- **Convênio:** Código do convênio/acordo comercial
- **Taxa ADM:** Percentual de taxa administrativa cobrada
  - **Importante:** Ao selecionar conveniada ou convênio, o sistema busca automaticamente a taxa administrativa cadastrada

**Flags de Controle:**
- **FLGeraer:** Indica se deve gerar contas a receber
- **Integração CRC:** Situação da integração com Contas a Receber
- **Número de Autorização:** Código de autorização da transação (cartões, TEF)

**Dados Complementares:**
- Código do cliente
- Tipo de pedido
- Número do processo
- Número do lançamento
- Data de referência
- Natureza contábil
- Data de entrada
- Código do evento
- Data de vencimento
- Condição de pagamento
- Código da conveniada
- Código do convênio
- Desdobro do título
- Número do banco
- Indicador de convênio alterado

#### Processo de Integração:

1. **Consulta:** Usuário filtra recebimentos pendentes por período e filial
2. **Seleção:** Marca os registros que deseja integrar via checkbox
3. **Validação:** Sistema verifica se os campos obrigatórios estão preenchidos:
   - Evento de contas a receber
   - Portador
   - Origem
   - Taxa ADM (quando aplicável)
4. **Ajustes:** Se necessário, usuário corrige informações:
   - Altera evento
   - Define portador correto
   - Ajusta convênio/conveniada
   - Inclui observações
5. **Integração:** Após confirmação, sistema gera os lançamentos no módulo de Contas a Receber

#### Validações do Sistema:

**Eventos e Portadores:**
- Sistema identifica recebimentos com eventos inconsistentes
- Marca em observação quando evento não está associado a portador correto
- Permite correção em massa: ao corrigir evento/portador, replica para todos os registros similares

**Convênios e Taxas:**
- Valida existência de taxa administrativa para convênios
- Busca automaticamente a taxa cadastrada ao selecionar conveniada
- Alerta quando convênio foi alterado manualmente

**Status de Integração:**
- Identifica registros já integrados
- Previne duplicação de lançamentos
- Mantém histórico do número de autorização

#### Cenários Comuns:

**1. Problema de Comunicação PDV:**
- Venda realizada com cartão no PDV
- Queda de rede impede integração automática
- Operador financeiro consulta e integra manualmente

**2. Recebimento via Convênio:**
- Cliente paga via convênio empresarial
- Sistema aguarda confirmação da conveniada
- Após confirmação, operador integra com dados corretos

**3. Transação TEF Pendente:**
- Pagamento realizado via TEF
- Problema técnico impede integração
- Conciliação identifica pendência
- Financeiro integra com número de autorização

#### Benefícios:
- Evita perda de registros financeiros
- Permite correção de inconsistências antes da integração
- Facilita conciliação de recebimentos
- Mantém integridade entre módulos de venda e financeiro
- Reduz necessidade de lançamentos manuais
- Preserva rastreabilidade com número de autorização
- Suporta gestão de convênios e administradoras de cartão
- Controle de taxas administrativas

**Observação Crítica:** Esta funcionalidade é essencial para ambientes com vendas em PDV e múltiplas formas de pagamento. Deve ser consultada regularmente para garantir que todos os recebimentos sejam devidamente contabilizados.

---

## 3. Interface Bancária

### 3.1. Consulta Títulos - Contas a Pagar

**Objetivo:** Acompanhar e gerenciar títulos de contas a pagar que foram enviados ou retornados através da interface de comunicação bancária, permitindo o controle completo do ciclo de vida de pagamentos eletrônicos.

#### Funcionalidades de Negócio:

**Contexto de Uso:**
Esta funcionalidade é utilizada para gerenciar títulos que fazem parte do processo de integração bancária eletrônica (arquivos CNAB, API bancária, etc.). Permite acompanhar desde o envio da ordem de pagamento até o retorno com confirmação ou rejeição do banco.

**Filtros de Pesquisa:**

**Dados Bancários:**
- **Banco:** Instituição financeira
- **Convênio:** Acordo de cobrança/pagamento com o banco
- **Filial:** Unidade que originou o pagamento

**Ocorrências:**
- **Checkbox Envio:** Filtra por situação de envio
  - Combo de Envio: Status específicos de envio ao banco
- **Checkbox Retorno:** Filtra por situação de retorno
  - Combo de Retorno: Status de processamento pelo banco

**Dados do Título:**
- **Tipo de Emitente:** Categoria do credor (Fornecedor, Transportadora, etc.)
- **Título e Desdobro:** Identificação do compromisso financeiro
- **Lote:** Número do lote de envio ao banco
- **Nota Fiscal:** Número do documento fiscal
- **Série:** Série da nota fiscal

**Períodos:**
Opções de filtro por data:
- **Data Sequencial (Dt. Seq.):** Data de processamento no sistema bancário
- **Data de Vencimento (Dt. Venc.):** Prazo de pagamento do título
- **Data da Nota (Dt. Nota):** Data de emissão do documento fiscal

**Rejeições:**
- **Rejeitados pelo Banco:** Títulos recusados pela instituição financeira
- **Rejeitados pelo Gemco:** Títulos com inconsistências internas
- **Combo de Motivos:** Lista de razões específicas de rejeição

**Aba: Dados Gerais**

**Informações do Título:**
- **Checkbox:** Seleção para operações em lote
- **Flag Grupo Flexível:** Indicador de agrupamento
- **Lote:** Número do lote de envio
- **Número CPG:** Identificador interno de contas a pagar
- **Filial:** Unidade de origem
- **Título e Desdobro:** Identificação completa
- **Erro Interno:** Código de erro do sistema (quando aplicável)

**Datas e Ocorrências:**
- **Data Sequencial:** Data de processamento bancário
- **Data de Envio:** Quando foi transmitido ao banco
- **Ocorrência:** Status atual no processo bancário
- **Tipo de Documento:** Classificação do documento de pagamento
- **Data de Pagamento:** Quando foi efetivamente pago
- **Data de Vencimento:** Prazo original

**Valores Financeiros:**
- **Valor Original:** Montante inicial do título
- **Valor de Abatimento:** Descontos aplicados
- **Valor de Encargos:** Juros, multas ou taxas
- **Valor Autorizado:** Montante aprovado para pagamento

**Dados da Nota Fiscal:**
- **Filial da Nota:** Origem do documento
- **Tipo de Nota:** Classificação fiscal
- **Série:** Série do documento
- **Número do Borderô:** Agrupamento de títulos
- **Data da Nota:** Emissão do documento
- **Número da Nota Fiscal:** Identificação do documento

**Dados do Emitente:**
- **Código do Emitente:** Identificador do credor
- **Emitente:** Nome ou razão social
- **Tipo de Emitente:** Categoria (Fornecedor, etc.)
- **Razão Social:** Nome completo registrado

**Controles e Status:**
- **Usuário Gerou Título:** Responsável pela criação
- **Usuário Enviou Título:** Responsável pelo envio
- **Usuário Cancelou Título:** Responsável pelo cancelamento (se aplicável)
- **Data de Cancelamento:** Quando foi cancelado
- **Observação de Cancelamento:** Motivo do cancelamento
- **Código do Motivo:** Classificação da razão de cancelamento
- **Origem:** Sistema que gerou o título
- **Descrição do Produto:** Quando aplicável
- **Status:** Situação atual
- **Ordem:** Sequência de processamento
- **Número do Lote de Liberação de Pagamento:** Identificador de autorização

**Aba: Motivo de Rejeição**

Apresenta detalhes quando um título é rejeitado:
- Código do motivo
- Descrição detalhada da rejeição
- Origem da rejeição (Banco ou Sistema)
- Orientações para correção

**Aba: Histórico de Lançamento**

Registra toda a trajetória do título:
- Data e hora de cada movimentação
- Usuário responsável por cada ação
- Tipo de operação realizada
- Status antes e depois de cada alteração
- Observações de cada etapa

#### Fluxo Operacional:

**1. Preparação:**
- Sistema gera arquivo com títulos a pagar
- Agrupa por lote e convênio bancário
- Valida dados obrigatórios para transmissão

**2. Envio:**
- Arquivo é transmitido ao banco (CNAB, API, etc.)
- Sistema registra data e usuário do envio
- Título fica com status "Enviado"

**3. Processamento Bancário:**
- Banco recebe e processa o arquivo
- Valida dados bancários, saldo, limites
- Gera arquivo de retorno

**4. Retorno:**
- Sistema importa arquivo de retorno
- Atualiza status de cada título
- Registra ocorrências (pago, rejeitado, etc.)

**5. Tratamento:**
- **Títulos Pagos:** Sistema baixa automaticamente
- **Títulos Rejeitados:** Exige correção e reenvio
- **Títulos Pendentes:** Aguarda novo retorno

#### Situações de Rejeição:

**Rejeições pelo Banco:**
- Dados bancários incorretos
- Saldo insuficiente
- Limite de crédito excedido
- CPF/CNPJ inválido
- Conta beneficiária bloqueada

**Rejeições pelo Sistema (Gemco):**
- Título já pago anteriormente
- Valor divergente
- Beneficiário não cadastrado
- Dados fiscais inconsistentes
- Título cancelado

#### Cenários de Uso:

**1. Pagamento de Fornecedores via TED/DOC:**
- Empresa gera lote com 50 pagamentos
- Envia ao banco via arquivo CNAB
- Acompanha retorno: 48 pagos, 2 rejeitados
- Corrige os 2 rejeitados e reenvia

**2. Pagamento de Boletos:**
- Sistema envia códigos de barras ao banco
- Banco efetua pagamentos automaticamente
- Retorno confirma pagamentos realizados
- Sistema baixa títulos confirmados

**3. Débito Automático:**
- Títulos recorrentes (aluguel, seguros, etc.)
- Envio mensal automático
- Acompanhamento de autorizações
- Controle de débitos efetivados

#### Benefícios:
- Automação de processos de pagamento
- Redução de erros manuais
- Rastreabilidade completa de pagamentos
- Controle de rejeições e reenvios
- Integração com sistema bancário
- Otimização do tempo da equipe financeira
- Segurança nas transações
- Conformidade com padrões bancários (CNAB, FEBRABAN)
- Auditoria completa de operações

**Observação Importante:** Esta funcionalidade exige configuração prévia de convênios bancários, layouts de arquivo e parâmetros de integração. É essencial para empresas que realizam volume significativo de pagamentos eletrônicos.

---

### 3.2. Consulta Títulos - Contas a Receber

**Objetivo:** Gerenciar e acompanhar títulos de contas a receber que foram enviados ao banco para cobrança (boletos bancários, débito automático, etc.), permitindo o controle completo do ciclo de recebimento através de integração bancária.

#### Funcionalidades de Negócio:

**Contexto de Uso:**
Esta funcionalidade controla títulos que fazem parte do processo de cobrança bancária eletrônica. Permite acompanhar desde a emissão do boleto/autorização de débito até o efetivo recebimento ou identificação de problemas na cobrança.

**Filtros de Pesquisa:**

**Dados Bancários:**
- **Banco:** Instituição financeira responsável pela cobrança
- **Convênio:** Acordo de cobrança específico
- **Filial:** Unidade que originou o título

**Tipo de Cliente:**
- **Categoria:** Cliente, Fornecedor (devolução), Transportadora, etc.
- Permite identificar a natureza do recebível

**Dados do Título:**
- **Número do Título:** Identificação única
- **Número CRC:** Código interno de contas a receber
- **Origem:** Sistema/módulo que gerou o título

**Filtros de Ocorrência:**
Sistema permite filtrar por diversos eventos do ciclo de vida do título:
- Registro de título
- Baixa de título
- Entrada confirmada
- Pedido de baixa
- Liquidação de título
- Débito de tarifas
- Protestos
- Sustações
- Abatimentos
- Prorrogações
- Alterações cadastrais

**Aba: Dados Gerais**

**Informações do Título:**
- **Checkbox:** Seleção para operações em lote
- **Lote:** Número do lote de envio/retorno
- **Número CRC:** Identificador interno
- **Filial:** Unidade de origem
- **Título:** Número completo com desdobro
- **Código da Filial:** Identificador da unidade

**Dados do Cliente:**
- **Tipo de Cliente:** Categoria do devedor
- **Código do Cliente:** Identificador único
- **Cliente:** Nome ou razão social
- **Cidade e Estado:** Localização do cliente

**Valores e Datas:**
- **Valor Original:** Montante inicial do título
- **Valor de Abatimento:** Descontos autorizados
- **Valor de Encargos:** Juros e multas configurados
- **Valor Recebido:** Montante efetivamente pago
- **Valor Líquido:** Valor após deduções e encargos
- **Data de Vencimento:** Prazo de pagamento
- **Data de Recebimento:** Quando foi efetivamente pago
- **Data de Crédito:** Quando caiu na conta da empresa

**Dados Bancários:**
- **Nosso Número:** Identificação do banco para o título
- **Número do Documento:** Referência no boleto
- **Carteira:** Tipo de cobrança (simples, caucionada, etc.)
- **Espécie:** Classificação do título (duplicata, promissória, etc.)

**Status e Ocorrências:**
- **Código de Ocorrência de Envio:** Status da transmissão ao banco
- **Código de Ocorrência de Retorno:** Status do processamento bancário
- **Motivo:** Descrição da situação atual
- **Observação:** Notas adicionais
- **Data Sequencial:** Data de processamento bancário

**Dados Fiscais e Operacionais:**
- **Número da Nota Fiscal:** Documento fiscal relacionado
- **Série da Nota:** Série do documento
- **Tipo de Nota:** Classificação fiscal
- **Contrato e Série de Contrato:** Para títulos de financiamento
- **Origem:** Sistema que gerou o título

**Aba: Histórico de Lançamento**

Registra a linha do tempo completa:
- Data e hora de cada evento
- Usuário responsável
- Tipo de movimentação
- Status anterior e novo
- Valores em cada etapa
- Observações de cada operação

**Aba: Depósito Identificado**

Gerencia recebimentos que necessitam identificação:
- Valor depositado
- Data do depósito
- Banco de origem
- Agência e conta
- Status de identificação
- Títulos associados ao depósito

#### Fluxo Operacional:

**1. Geração da Cobrança:**
- Sistema gera arquivo de remessa
- Inclui dados do título e do sacado (cliente)
- Define instruções de cobrança (juros, multa, protesto)

**2. Envio ao Banco:**
- Transmissão do arquivo (CNAB 240/400, API, etc.)
- Banco registra títulos
- Emite boletos ou autoriza débitos

**3. Cliente Recebe Cobrança:**
- Boleto bancário (físico ou digital)
- Débito automático agendado
- Carnê de pagamento

**4. Pagamento:**
- Cliente paga no banco, app bancário, correspondente, etc.
- Banco registra o pagamento

**5. Retorno:**
- Banco envia arquivo de retorno
- Sistema identifica pagamentos realizados
- Baixa automática dos títulos
- Registro de liquidação

**6. Crédito:**
- Valor é creditado na conta da empresa
- Sistema concilia com o título
- Deduz tarifas bancárias (quando aplicável)

#### Ocorrências Comuns:

**Registro:**
- Título foi aceito e registrado pelo banco
- Boleto está disponível para pagamento
- Débito automático foi agendado

**Liquidação:**
- Título foi pago pelo cliente
- Valor será creditado conforme prazo do convênio
- Título pode ser baixado

**Baixa:**
- Título foi baixado por comando
- Não está mais em cobrança
- Pode ser por pagamento, acordo ou cancelamento

**Protestos:**
- Título foi protestado conforme instrução
- Cliente foi notificado oficialmente
- Registro em cartório realizado

**Prorrogação:**
- Vencimento foi alterado
- Nova data acordada com cliente
- Encargos podem ser recalculados

**Abatimento:**
- Desconto concedido ao cliente
- Valor original reduzido
- Condições especiais aplicadas

**Erros/Rejeições:**
- Dados cadastrais incorretos
- CPF/CNPJ inválido
- CEP não encontrado
- Título já existe
- Valor fora dos limites permitidos

#### Cenários de Uso:

**1. Cobrança Simples:**
- Venda a prazo gera título
- Sistema envia ao banco
- Banco emite boleto
- Cliente paga
- Sistema baixa automaticamente

**2. Débito Automático:**
- Cliente autoriza débito em conta
- Título é enviado mensalmente
- Banco debita na data
- Sistema recebe confirmação
- Título é baixado

**3. Inadimplência:**
- Título vence e não é pago
- Sistema envia instrução de protesto
- Banco inicia processo
- Cliente é notificado
- Negociação é realizada

**4. Renegociação:**
- Cliente solicita nova data
- Sistema envia instrução de prorrogação
- Banco atualiza vencimento
- Novo boleto é emitido (se necessário)

**5. Depósito Não Identificado:**
- Cliente deposita sem informar o título
- Banco credita o valor
- Sistema registra como não identificado
- Operador associa ao título correto
- Título é baixado

#### Benefícios:
- Automação completa do processo de cobrança
- Redução de inadimplência através de controles bancários
- Facilidade para o cliente (múltiplos canais de pagamento)
- Conciliação automática de recebimentos
- Controle de tarifas bancárias
- Gestão de acordos e renegociações
- Rastreabilidade completa de cada título
- Integração com sistemas de protesto
- Suporte a múltiplos bancos e convênios
- Conformidade com padrões FEBRABAN (CNAB)
- Redução de erros manuais
- Otimização do tempo da equipe financeira

**Observação Importante:** Esta funcionalidade é essencial para empresas com carteira de clientes significativa. Requer configuração prévia de convênios bancários, carteiras de cobrança e instruções padronizadas.

---

### 3.3. Consulta de Cheques

**Objetivo:** Gerenciar e acompanhar cheques recebidos de clientes que estão sob custódia bancária ou em processo de compensação através da interface bancária, garantindo controle e segurança no recebimento via cheque.

#### Funcionalidades de Negócio:

**Contexto de Uso:**
Esta funcionalidade controla cheques recebidos de clientes que são enviados ao banco para compensação ou custódia. Permite acompanhar todo o ciclo: desde o recebimento físico do cheque até sua compensação ou devolução, incluindo situações de cheques pré-datados mantidos em custódia bancária.

**Frame: Custódia**

**Filtros de Custódia:**
- **Banco da Custódia:** Instituição financeira onde os cheques estão custodiados
- **Status da Custódia:**
  - Em custódia: Cheques depositados aguardando data de apresentação
  - Liberados: Cheques já apresentados para compensação
  - Devolvidos: Cheques que retornaram sem compensar
  - Custodiados: Todos sob guarda do banco

**Período da Custódia:**
- **Data Inicial:** Início do período de análise
- **Data Final:** Fim do período de análise

**Frame: Tipo**

**Tipos de Cheque:**
- **Próprio:** Cheque emitido contra conta do banco onde foi depositado (mesmo banco)
- **Praça:** Cheque de outro banco da mesma praça (mesma cidade)

**Frame: Período**

**Filtros de Período:**
- **Período de Vencimento:** Data em que o cheque pode ser apresentado
  - Relevante para cheques pré-datados
  - Controla quando cheque sairá da custódia

**Frame: Dados do Cliente**

**Identificação Bancária do Cheque:**
- **Banco do Cliente:** Banco emissor do cheque (banco sacado)
- **Agência:** Número da agência do cliente
- **Conta:** Número da conta do cliente
- **Número do Cheque:** Identificação única do cheque
- **Valor:** Montante do cheque

**Cliente Sacado:**
- **Cliente:** Nome do cliente que emitiu o cheque
  - Permite busca por código ou nome
  - Pesquisa por parte do nome (funcionalidade inteligente)

**Código de Ocorrência:**
- **Ocorrência:** Status bancário do cheque
  - Exemplos: depositado, compensado, devolvido, custodiado, apresentado, etc.

#### Grade de Apresentação:

**Informações do Cheque:**
- **Banco:** Código e nome do banco sacado
- **Agência:** Número da agência
- **Conta:** Número da conta (com dígito)
- **Número do Cheque:** Identificação do cheque
- **Valor:** Montante nominal

**Datas Relevantes:**
- **Data de Emissão:** Quando o cheque foi emitido
- **Data de Custódia:** Quando foi depositado no banco
- **Data de Vencimento/Bom Para:** Data em que pode ser apresentado (cheques pré-datados)
- **Data de Compensação:** Quando foi efetivamente compensado

**Status e Situação:**
- **Status:** Situação atual (Em custódia, Compensado, Devolvido, etc.)
- **Ocorrência Bancária:** Código de retorno do banco
- **Motivo:** Descrição da situação (quando houver problema)

**Dados do Cliente:**
- **Cliente:** Nome do emitente do cheque
- **CPF/CNPJ:** Documento do emitente
- **Título Associado:** Lançamento de contas a receber relacionado

**Dados da Transação:**
- **Número da Venda/Pedido:** Origem do recebimento
- **Filial:** Unidade que recebeu o cheque
- **Usuário:** Responsável pelo recebimento

#### Fluxo Operacional:

**1. Recebimento do Cheque:**
- Cliente efetua pagamento com cheque
- Sistema registra dados do cheque
- Vincula ao título de contas a receber
- Registra se é cheque à vista ou pré-datado

**2. Depósito em Custódia:**
- Cheques são enviados fisicamente ao banco
- Sistema gera arquivo de remessa
- Banco confirma recebimento
- Cheques ficam "em custódia"

**3. Apresentação para Compensação:**
- **Cheque à Vista:** Apresentado imediatamente
- **Cheque Pré-Datado:** Apresentado na data do "bom para"
- Banco inicia processo de compensação

**4. Compensação:**
- **Sucesso:** 
  - Cheque é compensado
  - Valor é creditado
  - Sistema baixa título automaticamente

- **Devolução:**
  - Cheque retorna sem compensar
  - Sistema registra motivo da devolução
  - Título volta a ficar em aberto
  - Cliente é notificado

**5. Tratamento de Devoluções:**
- Sistema identifica motivo
- Gera pendência para cobrança
- Pode gerar novo título
- Permite renegociação

#### Motivos Comuns de Devolução:

**Alçada 11 (Primeira Apresentação):**
- 11 - Insuficiência de fundos
- 12 - Conta encerrada
- 13 - Prática espúria
- 14 - Furto ou roubo
- 20 - Folha de cheque cancelada
- 21 - Contra-ordem (sustação)
- 22 - Divergência de assinatura
- 23 - Irregularidade de endosso

**Alçada 12 (Segunda Apresentação):**
- Apenas motivo 11 pode ser reapresentado
- Demais motivos não permitem nova tentativa

#### Cenários de Uso:

**1. Cheque à Vista:**
- Cliente paga compra com cheque
- Loja deposita no mesmo dia
- Banco compensa em 1-2 dias úteis
- Sistema baixa título automaticamente

**2. Cheque Pré-Datado:**
- Cliente dá cheque para 30 dias
- Sistema envia para custódia
- Banco guarda até a data acordada
- Na data, apresenta para compensação
- Cliente já providenciou o fundo

**3. Cheque Devolvido - Sem Fundos:**
- Cheque é apresentado
- Retorna por insuficiência (motivo 11)
- Sistema registra devolução
- Permite segunda apresentação
- Cobrança extra-bancária inicia

**4. Cheque Devolvido - Sustação:**
- Cliente faz contra-ordem (motivo 21)
- Banco devolve o cheque
- Sistema notifica sobre sustação
- Requer tratamento jurídico ou renegociação
- Não pode ser reapresentado

**5. Cheques de Outros Bancos:**
- Cliente dá cheque de banco diferente
- Prazo de compensação é maior (3-5 dias)
- Acompanhamento via interface bancária
- Confirmação de crédito

#### Controles e Validações:

**Validações de Recebimento:**
- Conferência de dados do cheque
- Validação de CMC-7 (código magnético)
- Verificação de restrições do cliente
- Consulta de cheques anteriores devolvidos

**Controles de Custódia:**
- Conciliação de cheques enviados vs. recebidos pelo banco
- Acompanhamento de prazos
- Alerta para cheques próximos do vencimento
- Controle de tarifas bancárias

**Gestão de Devoluções:**
- Registro de motivos
- Histórico de devoluções por cliente
- Score de risco baseado em histórico
- Integração com restrição de crédito

#### Benefícios:
- Controle preciso de cheques recebidos
- Automação da compensação bancária
- Gestão eficiente de cheques pré-datados
- Identificação rápida de devoluções
- Conciliação automática com recebimentos
- Redução de perdas com cheques sem fundos
- Histórico de comportamento de clientes
- Integração com sistema de crédito
- Controle de tarifas bancárias
- Rastreabilidade completa
- Suporte a decisões de política de recebimento

**Observações Importantes:**

1. **Tendência de Mercado:** O uso de cheques está em declínio com o avanço do PIX e cartões, mas ainda é relevante em alguns segmentos (B2B, grandes valores).

2. **Custos:** Manter custódia de cheques gera tarifas bancárias que devem ser monitoradas.

3. **Risco:** Cheques representam risco maior que outras formas de pagamento, exigindo controles rigorosos.

4. **Configuração:** Requer convênio específico com banco para custódia e arquivo de remessa/retorno.

---

## 4. Resumo e Integração entre Módulos

### Visão Integrada do Financeiro

As funcionalidades do menu Consulta > Financeiro trabalham de forma integrada, formando um ecossistema completo de gestão financeira:

#### Fluxo de Contas a Pagar:

```
[Compra/Despesa] 
	↓
[Lançamento CPG] → [Consulta Lançamentos]
	↓
[Emissão Cheque] → [Consulta Cheques]
	↓
[Envio Banco] → [Interface Bancária - CPG]
	↓
[Pagamento Confirmado]
```

#### Fluxo de Contas a Receber:

```
[Venda/Serviço]
	↓
[Lançamento CRC] → [Consulta Lançamentos]
	↓
[Recebimento PDV] → [Recebimentos Não Integrados]
	↓
[Emissão Boleto/Cheque] → [Interface Bancária - CRC]
	↓
[Recebimento Confirmado]
```

#### Fluxo de Compensação:

```
[Fornecedor que é Cliente]
	↓
[Consulta CPG + CRC]
	↓
[Prévia de Encontro de Contas]
	↓
[Análise de Compensação]
	↓
[Efetivação do Encontro de Contas]
```

### Principais Indicadores Gerenciais

As consultas disponíveis permitem extrair indicadores importantes:

**Contas a Pagar:**
- Total de obrigações por período
- Obrigações por fornecedor
- Obrigações por evento (compras, despesas, etc.)
- Análise de bloqueios e liberações
- Controle de pagamentos via cheque
- Taxa de rejeição em pagamentos eletrônicos

**Contas a Receber:**
- Total de recebíveis por período
- Carteira de clientes
- Análise de inadimplência
- Títulos em cobrança bancária
- Taxa de sucesso em débitos automáticos
- Cheques devolvidos por cliente

**Interface Bancária:**
- Volume de transações bancárias
- Taxa de rejeição bancária
- Tempo médio de compensação
- Tarifas bancárias
- Eficiência de integração

### Benefícios Globais do Módulo

1. **Visibilidade Financeira:**
   - Posição completa de direitos e obrigações
   - Fluxo de caixa projetado e realizado
   - Rastreabilidade de todas as operações

2. **Automação:**
   - Redução de digitação manual
   - Integração bancária eletrônica
   - Baixas automáticas de títulos
   - Conciliação facilitada

3. **Controle:**
   - Gestão de bloqueios e liberações
   - Alçadas de aprovação
   - Auditoria completa
   - Segregação de funções

4. **Redução de Custos:**
   - Otimização via encontro de contas
   - Redução de tarifas bancárias
   - Menor inadimplência
   - Ganho de produtividade

5. **Conformidade:**
   - Padrões FEBRABAN
   - Controles internos
   - Rastreabilidade para auditoria
   - Segurança nas operações

---

## 5. Perfis de Usuário e Permissões

### Operador Financeiro

**Acesso Típico:**
- Consulta Lançamentos (CPG e CRC)
- Consulta Cheques (CPG)
- Recebimentos Não Integrados

**Responsabilidades:**
- Consultar títulos e situações
- Integrar recebimentos pendentes
- Verificar status de pagamentos
- Gerar relatórios operacionais

### Analista de Contas a Pagar

**Acesso Típico:**
- Consulta Lançamentos CPG
- Consulta Cheques CPG
- Interface Bancária - CPG
- Prévia de Encontro de Contas

**Responsabilidades:**
- Gerenciar pagamentos
- Acompanhar interface bancária
- Tratar rejeições
- Analisar compensações

### Analista de Contas a Receber

**Acesso Típico:**
- Consulta Lançamentos CRC
- Recebimentos Não Integrados
- Interface Bancária - CRC
- Consulta de Cheques (recebimento)

**Responsabilidades:**
- Gerenciar recebimentos
- Acompanhar cobranças bancárias
- Tratar inadimplência
- Conciliar recebimentos

### Gerente Financeiro

**Acesso Total:**
- Todas as consultas do módulo
- Análises gerenciais
- Indicadores consolidados

**Responsabilidades:**
- Visão estratégica do financeiro
- Análise de fluxo de caixa
- Decisões de compensação
- Gestão de relacionamento bancário

---

## 6. Boas Práticas de Utilização

### Rotinas Diárias

**Manhã:**
1. Consultar Interface Bancária - CPG (verificar pagamentos do dia anterior)
2. Consultar Interface Bancária - CRC (verificar recebimentos)
3. Verificar Recebimentos Não Integrados (integrar pendências)

**Tarde:**
4. Consultar Lançamentos CPG (vencimentos do dia)
5. Consultar Lançamentos CRC (títulos vencidos)
6. Processar devoluções de cheques

**Fim do Dia:**
7. Conciliação de pagamentos e recebimentos
8. Análise de rejeições e pendências
9. Preparação de lotes para o dia seguinte

### Rotinas Semanais

**Segunda-feira:**
- Análise de vencimentos da semana
- Prévia de Encontro de Contas

**Quarta-feira:**
- Revisão de títulos bloqueados
- Análise de inadimplência

**Sexta-feira:**
- Conciliação bancária da semana
- Análise de cheques em custódia
- Preparação para semana seguinte

### Rotinas Mensais

**Início do Mês:**
- Análise de títulos vencidos no mês anterior
- Revisão de políticas de crédito
- Consolidação de tarifas bancárias

**Final do Mês:**
- Fechamento contábil
- Conciliação completa
- Indicadores mensais
- Análise de aging (contas a receber)

### Dicas Operacionais

1. **Utilize os Filtros:**
   - Sempre trabalhe com períodos definidos
   - Use filtros por filial em ambientes multi-unidade
   - Salve consultas frequentes como favoritos

2. **Atenção a Pendências:**
   - Recebimentos Não Integrados devem ser zerados diariamente
   - Rejeições bancárias precisam tratamento imediato
   - Cheques devolvidos exigem ação rápida

3. **Aproveite a Integração:**
   - Deixe o sistema fazer baixas automáticas
   - Use encontro de contas quando possível
   - Mantenha cadastros bancários atualizados

4. **Documentação:**
   - Sempre inclua observações em situações especiais
   - Mantenha histórico de renegociações
   - Documente motivos de bloqueios

5. **Segurança:**
   - Utilize os controles de permissão
   - Ative auditoria em operações críticas
   - Segregue funções entre usuários

---

## 7. Integrações com Outros Módulos

### Módulo de Compras
- Gera lançamentos em Contas a Pagar
- Alimenta dados de fornecedores
- Vincula notas fiscais a títulos

### Módulo de Vendas/PDV
- Gera lançamentos em Contas a Receber
- Registra recebimentos
- Alimenta Recebimentos Não Integrados

### Módulo Contábil
- Recebe lançamentos contábeis
- Integração de plano de contas
- Conciliação contábil-financeira

### Módulo de Estoque
- Vinculação de notas a títulos
- Controle de devoluções
- Rastreabilidade de operações

### Módulo Fiscal
- Validação de documentos fiscais
- Controle de séries e numeração
- Conformidade tributária

---

## 8. Glossário de Termos

**Borderô:** Agrupamento de títulos enviados ao banco para cobrança ou pagamento

**CNAB:** Centro Nacional de Automação Bancária - padrão de arquivo para comunicação bancária

**CPG:** Contas a Pagar

**CRC:** Contas a Receber

**Custódia:** Guarda de cheques pelo banco até data de apresentação

**Desdobro:** Parcela de um título (exemplo: 3/5 = terceira de cinco parcelas)

**Emitente:** No contexto de CPG, é o fornecedor ou credor. Em CRC, é o cliente ou devedor

**Encontro de Contas:** Compensação de valores a pagar e a receber de mesma contraparte

**Evento:** Classificação do tipo de lançamento financeiro (compra, venda, despesa, etc.)

**Interface Bancária:** Módulo de comunicação eletrônica com bancos

**Lote:** Agrupamento de títulos processados em conjunto

**Nosso Número:** Identificação única dada pelo banco a cada título em cobrança

**Ocorrência:** Código de status retornado pelo banco (pago, devolvido, registrado, etc.)

**Origem:** Sistema ou módulo que gerou o lançamento financeiro

**Portador:** Banco ou instituição financeira que processa o recebimento

**Prévia:** Simulação que não efetiva operação, apenas apresenta resultados possíveis

**Rejeição:** Recusa de processamento de título pelo banco ou sistema

**Remessa:** Arquivo enviado ao banco com instruções

**Retorno:** Arquivo recebido do banco com resultados de processamento

**Sacado:** Cliente ou devedor em operação de cobrança

**Título:** Compromisso financeiro (a pagar ou a receber)

---

## 9. Considerações Finais

O módulo de Consulta Financeiro do Gemco Varejo oferece uma visão completa e integrada das operações financeiras da empresa. Através de suas funcionalidades, é possível:

- Manter controle rigoroso de compromissos financeiros
- Automatizar processos de cobrança e pagamento
- Integrar-se eletronicamente com instituições bancárias
- Otimizar fluxo de caixa
- Reduzir custos operacionais
- Garantir conformidade e auditabilidade

A efetiva utilização deste módulo depende de:
1. Treinamento adequado dos usuários
2. Configuração correta de parâmetros
3. Manutenção de cadastros atualizados
4. Acompanhamento de rotinas operacionais
5. Análise periódica de indicadores

Para suporte adicional, consulte a documentação técnica específica de cada funcionalidade ou entre em contato com a equipe de TI.

---

**Documento gerado através da análise do código-fonte VB6 do sistema Gemco Varejo**

**Versão:** 1.0  
**Data:** Dezembro 2024  
**Responsável pela Documentação:** Análise automatizada de código fonte
