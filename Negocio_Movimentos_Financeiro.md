# Documentação de Negócio - Menu Movimentos > Financeiro

## Sumário Executivo

Este documento descreve as funcionalidades de negócio disponíveis no menu **Movimentos > Financeiro** do sistema Gemco Varejo. O módulo financeiro é responsável por gerenciar todas as operações relacionadas a contas a pagar, contas a receber, cobrança, tesouraria e controles bancários da empresa.

**Sistema:** Gemco Varejo - ERP  
**Arquitetura:** 3 Camadas (Interface, Negócio, Banco de Dados)  
**Tecnologia:** Visual Basic 6  
**Base de Análise:** Código-fonte em `C:\AzureDevOps\VD-Gemco-Varejo\Implement\branches\dev\`

---

## 1. CONTAS A PAGAR

### 1.1 Propósito
Gerenciar todos os compromissos financeiros da empresa com fornecedores, prestadores de serviços e demais credores. Permite o controle completo desde a inclusão do título até sua liquidação.

### 1.2 Funcionalidades Principais

#### Consulta e Gestão de Títulos
- **Consulta de Títulos:** Pesquisa avançada de títulos a pagar por diversos filtros (favorecido, data de vencimento, origem, situação, portador, filial, grupo econômico, orçamento)
- **Filtros de Situação:** Visualização de títulos por status (a pagar, atrasados, a vencer, pagos, previstos, confirmados)
- **Visualização Agrupada:** Resumo de títulos vencidos, a vencer, pagos totalmente, pagos parcialmente e total geral
- **Detalhamento:** Acesso completo aos dados do título incluindo informações complementares, origem, nota fiscal, pedido e contrato

#### Operações sobre Títulos
- **Inclusão de Títulos:** Cadastro manual de compromissos financeiros com definição de:
  - Favorecido (fornecedor/credor)
  - Valor e data de vencimento
  - Forma de pagamento (dinheiro, cheque, transferência bancária, boleto, etc.)
  - Origem do compromisso
  - Centro de custo
  - Portador
  - Observações

- **Alteração de Títulos:** Modificação de dados de títulos ainda não pagos, incluindo:
  - Alteração de valor
  - Prorrogação de vencimento
  - Mudança de forma de pagamento
  - Atualização de dados bancários
  - Vinculação a orçamentos

- **Exclusão/Cancelamento:** Cancelamento de títulos mediante validação de permissões e regras de negócio

#### Lançamentos Financeiros
- **Baixa de Títulos:** Registro do pagamento efetivo com:
  - Data de pagamento
  - Valor pago
  - Descontos aplicados
  - Juros e multas
  - Abatimentos
  - Forma de pagamento utilizada
  - Dados da conta corrente (para pagamentos via banco)

- **Lançamentos Parciais:** Possibilidade de efetuar múltiplos pagamentos parciais sobre um mesmo título

- **Histórico de Movimentos:** Registro completo de todas as operações realizadas sobre cada título

#### Gestão de Cheques
- **Emissão de Cheques:** Controle de emissão de cheques para pagamento com:
  - Seleção de conta corrente
  - Numeração sequencial automática
  - Impressão de cheques
  - Cópia de cheque emitido

- **Cancelamento de Cheques:** Anulação de cheques emitidos com justificativa

#### Borderôs e Remessa Bancária
- **Geração de Borderôs:** Agrupamento de títulos para remessa bancária
- **Envio ao Banco:** Preparação de arquivos para pagamento em lote via sistema bancário
- **Controle de Borderôs:** Acompanhamento de borderôs enviados e processados

#### Controles Especiais
- **Adiantamento a Fornecedores:** Registro e controle de valores pagos antecipadamente
- **Encontro de Contas:** Compensação de valores a pagar com valores a receber do mesmo fornecedor/cliente
- **Ordem de Pagamento:** Geração de autorização formal para efetivação de pagamentos
- **Substituição de Títulos:** Troca de títulos por renegociação ou refinanciamento
- **Múltiplas Alterações:** Alteração em lote de vários títulos simultaneamente
- **Liberação/Bloqueio de Pagamento:** Controle de alçadas para aprovação de pagamentos
- **Validação de Pagamento de Representantes:** Gestão específica para pagamentos a representantes comerciais

#### Integrações
- **Vínculos com Orçamento de Despesas:** Amarração dos títulos com o orçamento previsto
- **Competência:** Classificação de despesas por período de competência
- **Centro de Custo:** Alocação de despesas por departamento/projeto
- **Contabilização:** Integração com módulo contábil

### 1.3 Relatórios e Consultas
- Consulta de contratos de compra/fornecimento
- Consulta de lançamentos realizados
- Diário auxiliar de fornecedores
- Consulta de previsões de pagamento
- Relatório de cheques emitidos
- Prévia de encontro de contas

---

## 2. CONTAS A RECEBER

### 2.1 Propósito
Gerenciar todos os valores a receber de clientes, originados de vendas, prestação de serviços ou outras operações comerciais. Controla desde a geração do título até seu recebimento efetivo.

### 2.2 Funcionalidades Principais

#### Consulta e Gestão de Títulos
- **Consulta de Títulos:** Pesquisa avançada por cliente, data de vencimento/emissão, origem, situação, vendedor, portador, filial, avalista, grupo econômico
- **Filtros Específicos:** Visualização por status de recebimento, títulos vencidos, títulos faturados, carnês agrupados
- **Posição Financeira do Cliente:** Visão consolidada de todos os títulos de um cliente
- **Visualização Detalhada:** Acesso a informações de pedido, nota fiscal, contrato de financiamento, vendedor, depositante identificado

#### Operações sobre Títulos
- **Inclusão de Títulos:** Cadastro manual de recebíveis com:
  - Dados do cliente
  - Valor e vencimento
  - Origem (venda, serviço, etc.)
  - Alinea (classificação do título)
  - Situação de contato
  - Portador (banco de recebimento)
  - Avalista (quando aplicável)

- **Alteração de Títulos:** Modificação de títulos não recebidos incluindo:
  - Alteração de valor e vencimento
  - Mudança de portador
  - Inclusão/alteração de avalista
  - Atualização de alinea e situação
  - Vínculo com vendedor

- **Cancelamento:** Cancelamento de títulos conforme regras e permissões

#### Recebimentos
- **Baixa de Títulos:** Registro de recebimento com:
  - Data de recebimento
  - Valor recebido
  - Descontos concedidos
  - Juros e multas recebidos
  - Forma de recebimento (dinheiro, cheque, cartão, depósito, etc.)
  - Dados bancários (quando aplicável)

- **Recebimentos Parciais:** Múltiplos recebimentos sobre um mesmo título

- **Recebimentos Não Integrados:** Tratamento de recebimentos realizados mas não integrados ao sistema

- **Estorno de Recebimentos:** Cancelamento de baixas efetuadas indevidamente

#### Gestão de Cheques Recebidos
- **Controle de Cheques:** Registro de cheques recebidos de clientes
- **Situação de Cheques:** Controle de cheques bons, devolvidos, depositados, reapresentados
- **Estatística de Cheques Devolvidos:** Análise de inadimplência por cheques

#### Boletos e Cobrança Bancária
- **Geração de Lotes:** Criação de lotes de boletos para remessa ao banco
- **Lotes Automáticos:** Geração automática de lotes baseada em regras
- **Impressão de Boletos:** Emissão de boletos bancários para envio ao cliente
- **Reimpressão:** Nova impressão de boletos já emitidos
- **Extrato de Boletos:** Consulta de situação de boletos emitidos

#### Carnês
- **Carnês Agrupados:** Emissão de carnês com múltiplas parcelas
- **Consulta de Slips:** Visualização de carnês emitidos
- **Consulta de Carnês Agrupados:** Controle de carnês com múltiplos vencimentos

#### Gestão de Crédito e Cobrança
- **Reanálise de Crédito:** Reavaliação de limite de crédito de clientes
- **Confirmação de Reanálise:** Aprovação de novas análises de crédito
- **Negativação de Clientes:** Inclusão de clientes inadimplentes em órgãos de proteção ao crédito
- **Troca de Arquivo de Crédito:** Retorno de informações de bureaus de crédito
- **Restrição de Crédito:** Bloqueio preventivo de crédito

#### Contratos e Financiamentos
- **Avaliação de Financiamento:** Análise de propostas de financiamento
- **Avalista de Contratos:** Gestão de avalistas em contratos de crédito
- **Cancelamento de Contratos:** Cancelamento de contratos de financiamento
- **Consulta de Contratos:** Acompanhamento de contratos ativos e cancelados
- **Associação de Avalistas:** Vinculação de garantidores aos contratos
- **Associação de Depositantes Identificados:** Controle de depósitos identificados

#### Controles Especiais
- **Renegociação de Títulos:** Reestruturação de dívidas com:
  - Novos prazos e valores
  - Descontos para quitação
  - Geração de novos títulos
  - Histórico de renegociações

- **Múltiplas Alterações:** Alteração em lote de títulos selecionados
- **Liberação/Bloqueio de Recebimento:** Controle de alçadas para recebimentos
- **Estorno de Múltiplos Lançamentos:** Cancelamento de várias baixas simultaneamente

#### Integrações
- **Depósitos Identificados:** Controle de depósitos bancários identificados
- **Conciliação com Vendas:** Amarração com pedidos e notas fiscais
- **Comissões:** Base para cálculo de comissões de vendedores
- **Contabilização:** Integração com módulo contábil

### 2.3 Relatórios e Consultas
- Consulta de lançamentos realizados
- Consulta de lotes de cobrança
- Posição financeira por cliente
- Relatório de clientes inadimplentes
- Histórico de movimentação de títulos
- Consulta de conciliação de recebimentos

---

## 3. COBRANÇA

### 3.1 Propósito
Gerenciar o processo de cobrança de clientes inadimplentes, com acompanhamento de ações, histórico de contatos e estratégias de recuperação de crédito. Permite o trabalho organizado de equipes de cobrança.

### 3.2 Funcionalidades Principais

#### Gestão de Cobrança
- **Tela de Cobrança:** Interface centralizada para atividades de cobrança com:
  - Visualização de títulos vencidos por cliente
  - Histórico completo de ações de cobrança
  - Dados cadastrais do cliente
  - Posição consolidada de débitos
  - Outros títulos do cliente (vencidos e a vencer)

#### Ações de Cobrança
- **Registro de Ações:** Documentação de todas as tentativas de cobrança:
  - Tipo de contato (telefone, e-mail, carta, visita)
  - Data e hora da ação
  - Cobrador responsável
  - Resultado da ação
  - Observações detalhadas
  - Próxima ação agendada

- **Situação de Contato:** Classificação do resultado do contato:
  - Promessa de pagamento
  - Cliente ausente
  - Telefone não atende
  - Negociação em andamento
  - Recusa de pagamento
  - Outras situações

- **Ocorrências:** Registro de eventos importantes durante a cobrança

#### Políticas de Cobrança
- **Regras de Cobrança:** Definição de estratégias automatizadas:
  - Período de carência antes da cobrança
  - Ações progressivas por dias de atraso
  - Escalonamento de cobranças
  - Tipos de ação por faixa de valor

#### Ferramentas de Cobrança
- **Cartas de Cobrança:** Geração e envio de cartas de cobrança:
  - Modelos personalizáveis
  - Impressão em lote
  - Controle de envio

- **Negativação de Clientes:** Processo de inclusão em órgãos de proteção ao crédito:
  - SPC (Serviço de Proteção ao Crédito)
  - SERASA
  - Controle de títulos negativados

- **Protestos:** Gestão de títulos protestados e quitações de protesto

#### Comissões
- **Apuração de Comissão de Cobrança:** Cálculo de comissões para equipe de cobrança baseado em:
  - Valores recuperados
  - Metas atingidas
  - Período de apuração
  - Regras de comissionamento

#### Renegociação
- **Renegociação de Títulos:** Reestruturação de dívidas com:
  - Proposta de novos prazos
  - Descontos para quitação
  - Parcelamento de débitos
  - Geração de novos títulos
  - Histórico de renegociações
  - Termo de renegociação

#### Consultas e Análises
- **Histórico de Cobrança:** Consulta completa de todas as ações realizadas
- **Ficha de Cobrança:** Documento consolidado com histórico do cliente
- **Relatórios de Renegociação:** Análise de renegociações realizadas

### 3.3 Integrações
- **Contas a Receber:** Sincronização automática com títulos a receber
- **Cadastro de Clientes:** Acesso aos dados cadastrais completos
- **Reanálise de Crédito:** Processo de liberação após quitação
- **Interface Bancária:** Retorno de arquivos de negativação

---

## 4. CONCILIAÇÃO BANCÁRIA

### 4.1 Propósito
Realizar a conciliação entre os lançamentos contábeis da empresa e os extratos bancários, identificando diferenças, lançamentos pendentes e garantindo a consistência entre os saldos.

### 4.2 Funcionalidades Principais

#### Conciliação
- **Importação de Extratos:** Carga de extratos bancários em diversos formatos (OFX, CNAB, etc.)
- **Conciliação Manual:** Associação manual de lançamentos bancários com lançamentos contábeis
- **Conciliação Automática:** Sugestão automática de associações baseada em:
  - Valores
  - Datas
  - Documentos
  - Históricos

- **Lançamentos Pendentes:** Identificação de:
  - Lançamentos no banco não contabilizados
  - Lançamentos contábeis não compensados no banco
  - Diferenças de valores

#### Controles
- **Saldo Conciliado:** Cálculo do saldo real considerando:
  - Saldo bancário
  - Lançamentos contábeis pendentes
  - Cheques emitidos não compensados
  - Depósitos em trânsito

- **Histórico de Conciliações:** Registro de todas as conciliações realizadas

### 4.3 Relatórios
- Extratos conciliados
- Lançamentos pendentes de conciliação
- Diferenças identificadas

---

## 5. INTERFACE BANCÁRIA

### 5.1 Propósito
Realizar a integração eletrônica com instituições bancárias através de arquivos padronizados, automatizando processos de cobrança, pagamento e recebimento de informações.

### 5.2 Funcionalidades Principais

#### Cobrança Bancária
- **Geração de Arquivos de Remessa:** Criação de arquivos para envio ao banco contendo:
  - Registro de boletos
  - Baixas de títulos
  - Alterações de vencimento
  - Protestos
  - Cancelamentos

- **Processamento de Arquivos de Retorno:** Leitura de arquivos retornados pelo banco com:
  - Confirmação de registros
  - Liquidação de boletos
  - Baixas efetivadas
  - Ocorrências (rejeições, alterações)
  - Tarifas bancárias

- **Instrução Bancária Automática:** Comandos automáticos ao banco:
  - Protesto após X dias de atraso
  - Baixa automática após Y dias
  - Alteração de valor
  - Alteração de vencimento

- **Consulta de Lotes:** Acompanhamento de arquivos enviados e processados
- **Consulta de Liberação:** Controle de remessas autorizadas

#### Empresas Conveniadas
- **Importação de Movimentos:** Carga de arquivos de operadoras de cartão:
  - Vendas realizadas
  - Valores a receber
  - Descontos e tarifas
  - Cancelamentos e estornos

- **Movimentos de Vendas:** Consulta e conferência de vendas registradas pelas operadoras
- **Movimentos Financeiros:** Acompanhamento de repasses financeiros programados
- **Requisição de Ajustes:** Solicitação de correções junto às operadoras

#### Extrato Bancário
- **Importação de Extratos:** Carga automática de extratos em formato eletrônico:
  - Arquivos OFX
  - Arquivos CNAB
  - Formatos específicos de cada banco

- **Cadastro Manual:** Registro manual de movimentos bancários

#### Integração de Serviços
- **Integração de Garantias:** Processamento de operações de seguro e garantias estendidas vinculadas a vendas

### 5.3 Padrões Suportados
- CNAB 240 posições
- CNAB 400 posições
- Layouts específicos de operadoras de cartão (Visa, Mastercard, Elo, Amex, Hipercard, etc.)

---

## 6. EMPRESAS CONVENIADAS

### 6.1 Propósito
Gerenciar operações com empresas conveniadas, principalmente operadoras de cartão de crédito e débito, controlando vendas realizadas, valores a receber e conciliações.

### 6.2 Funcionalidades Principais

#### Importação de Dados
- **Importação de Movimentos:** Carga de arquivos das operadoras contendo:
  - Transações realizadas (vendas e débitos)
  - Valores brutos e líquidos
  - Tarifas aplicadas
  - Datas de crédito
  - Informações de parcelamento

- **Formatos Suportados:** 
  - Redecard
  - Cielo
  - Losango
  - Hipercard
  - Cetelem
  - Tecban
  - Padrão Gemco
  - Outros padrões customizados

#### Movimentos de Vendas
- **Consulta de Vendas:** Visualização de transações importadas:
  - Vendas à vista
  - Vendas parceladas
  - Débitos
  - Cancelamentos

- **Conciliação de Vendas:** Associação das vendas importadas com vendas registradas no sistema

#### Movimentos Financeiros
- **Previsão de Recebimentos:** Controle de valores a receber das operadoras:
  - Agenda de repasses
  - Valores líquidos (após descontos)
  - Parcelas a receber

- **Liberação de Movimentos:** Autorização de movimentos financeiros para baixa em contas a receber

- **Consulta de Movimentos:** Acompanhamento detalhado de repasses programados

#### Requisição de Ajustes
- **Solicitação de Ajustes:** Registro de divergências para correção:
  - Valores incorretos
  - Transações não identificadas
  - Cancelamentos não processados
  - Tarifas indevidas

- **Acompanhamento de Requisições:** Controle de ajustes solicitados e processados

#### Controles Especiais
- **Associação de Parcelas:** Vinculação de parcelas das operadoras com títulos a receber
- **Inversão de Títulos:** Correção de associações incorretas
- **Relatórios de Divergências:** Identificação de inconsistências entre sistema e operadora
- **Relatórios de Pendências:** Acompanhamento de itens não conciliados

### 6.3 Integrações
- **Contas a Receber:** Geração automática de títulos a receber
- **Cadastro de Clientes:** Vinculação com vendas realizadas
- **PDV/Frente de Caixa:** Importação de vendas realizadas no ponto de venda

---

## 7. TESOURARIA

### 7.1 Propósito
Gerenciar o caixa da empresa através do controle de contas correntes, fluxo de caixa e previsões financeiras, garantindo liquidez e otimização dos recursos financeiros.

### 7.2 Funcionalidades Principais

#### Conta Corrente
- **Movimentação de Conta Corrente:** Registro de todas as operações bancárias:
  - Depósitos
  - Saques
  - Transferências entre contas
  - Tarifas bancárias
  - Rendimentos de aplicações
  - IOF e impostos
  - Pagamentos diversos
  - Recebimentos diversos

- **Tipos de Lançamento:**
  - Entrada de recursos
  - Saída de recursos
  - Transferências internas
  - Aplicações financeiras
  - Resgates de aplicações

- **Consulta de Saldo:** Visualização de:
  - Saldo atual
  - Saldo disponível
  - Saldo projetado
  - Cheques pendentes
  - Depósitos em trânsito

- **Histórico de Movimentos:** Extrato completo de movimentações por conta corrente

- **Múltiplas Alterações:** Correção em lote de lançamentos

#### Fluxo de Caixa
- **Fluxo de Caixa Realizado:** Visualização de entradas e saídas efetivas:
  - Por período
  - Por conta corrente
  - Por centro de custo
  - Por tipo de operação
  - Saldo acumulado

- **Análise Comparativa:** Comparação entre períodos

- **Gráficos e Indicadores:** Visualização gráfica do fluxo financeiro

#### Previsão de Fluxo de Caixa
- **Previsões Manuais:** Registro de entradas e saídas previstas:
  - Descrição da operação
  - Valor previsto
  - Data prevista
  - Recorrência (quando aplicável)
  - Status (previsto, confirmado, realizado)

- **Previsões Automáticas:** Geração automática baseada em:
  - Contas a pagar não liquidadas
  - Contas a receber em aberto
  - Parcelas de contratos
  - Operações recorrentes

- **Vencimentos:** Controle de datas previstas para pagamentos e recebimentos:
  - Vencimento original
  - Vencimento efetivo
  - Valores confirmados

- **Consolidação:** Visão consolidada de todas as previsões por período

- **Acompanhamento:** Comparação entre previsto x realizado

#### Extrato Bancário
- **Cadastro de Extratos:** Registro manual ou importação eletrônica de movimentos bancários

- **Conciliação:** Associação de extratos com lançamentos contábeis (ver item 4 - Conciliação Bancária)

#### Integração de Serviços
- **Integração de Garantias:** Processamento de operações de seguros e garantias estendidas vinculadas a vendas com reflexo financeiro

### 7.3 Controles Gerenciais
- Saldo disponível por conta
- Posição consolidada de caixa
- Projeção de necessidade de caixa
- Otimização de aplicações financeiras

### 7.4 Integrações
- **Contas a Pagar:** Alimentação automática do fluxo de caixa
- **Contas a Receber:** Previsão de recebimentos
- **Contabilidade:** Conciliação de lançamentos
- **Orçamento:** Comparativo orçado x realizado

---

## 8. ORÇAMENTO DE DESPESA

### 8.1 Propósito
Planejar e controlar despesas da empresa através de orçamentos por centro de custo, permitindo o acompanhamento da execução orçamentária e análise de desvios.

### 8.2 Funcionalidades Principais

#### Gestão de Orçamentos
- **Cadastro de Orçamentos:** Criação de orçamentos com:
  - Período de vigência
  - Centro de custo
  - Valores orçados por categoria de despesa
  - Distribuição mensal
  - Responsável pelo orçamento

- **Consulta de Orçamentos:** Visualização de orçamentos cadastrados:
  - Por centro de custo
  - Por período
  - Por status (ativo, concluído, cancelado)

- **Alteração de Orçamentos:** Ajuste de valores orçados conforme necessidade

#### Controle de Execução
- **Acompanhamento de Despesas:** Monitoramento de valores executados x orçados:
  - Valor orçado
  - Valor empenhado (comprometido)
  - Valor realizado
  - Saldo disponível

- **Vinculação com Contas a Pagar:** Amarração de títulos a pagar com orçamentos:
  - Reserva automática de saldo
  - Bloqueio de pagamentos sem orçamento (quando parametrizado)
  - Histórico de utilizações

- **Requisições de Pagamento:** Solicitação formal de pagamentos com:
  - Vinculação ao orçamento
  - Aprovação de alçadas
  - Justificativa

#### Centro de Custo
- **Alocação por Centro de Custo:** Distribuição de despesas por:
  - Departamento
  - Projeto
  - Filial
  - Outras dimensões de custo

- **Rateio de Despesas:** Divisão proporcional de despesas entre centros de custo

#### Análises
- **Análise de Despesas por Faturamento:** Comparação entre despesas realizadas e receita obtida:
  - Por período
  - Por centro de custo
  - Percentual sobre faturamento

- **Análise de Faturamento:** Acompanhamento de receitas e despesas conjuntamente

- **Relatórios Gerenciais:**
  - Orçado x Realizado
  - Desvios orçamentários
  - Projeções de consumo
  - Tendências

### 8.3 Controles
- **Alçadas de Aprovação:** Definição de limites e aprovadores por nível
- **Bloqueios:** Impedimento de pagamentos sem orçamento disponível
- **Alertas:** Notificações de consumo próximo ao limite

### 8.4 Integrações
- **Contas a Pagar:** Vinculação automática de títulos
- **Centro de Custo:** Classificação contábil
- **Tesouraria:** Impacto no fluxo de caixa
- **Contabilidade:** Consolidação de despesas realizadas

---

## 9. REGRAS DE NEGÓCIO GERAIS

### 9.1 Segurança e Permissões
- Todas as funcionalidades possuem controle de acesso por perfil de usuário
- Operações críticas (cancelamentos, estornos, alterações de valores) exigem autorizações especiais
- Registro de auditoria para todas as operações (quem fez, quando e o que)

### 9.2 Multi-Filial
- Sistema preparado para operação multi-filial
- Controle de operações por filial
- Consolidação de informações entre filiais
- Opção de visualização consolidada ou por filial específica

### 9.3 Multi-Empresa
- Suporte a múltiplas empresas do grupo
- Controle independente por empresa
- Consolidação por grupo econômico

### 9.4 Parametrizações
O sistema possui diversos parâmetros que alteram o comportamento das funcionalidades:
- Geração automática de previsão de fluxo de caixa
- Bloqueio de pagamentos sem orçamento
- Geração automática de borderôs
- Dias de carência para cobrança
- Cálculo automático de juros e multa
- Entre outros

### 9.5 Integrações Contábeis
- Geração automática de lançamentos contábeis para todas as operações financeiras
- Vinculação com plano de contas
- Rateio contábil por centro de custo
- Fechamento mensal integrado

---

## 10. BENEFÍCIOS DO MÓDULO FINANCEIRO

### 10.1 Controle Financeiro
- Visibilidade completa da posição financeira da empresa
- Controle rigoroso de contas a pagar e receber
- Redução de inadimplência através de gestão ativa de cobrança
- Otimização do capital de giro

### 10.2 Integração Bancária
- Redução de trabalho manual através de arquivos eletrônicos
- Agilidade no processamento de pagamentos e recebimentos
- Conciliação bancária facilitada
- Redução de erros operacionais

### 10.3 Gestão de Caixa
- Previsibilidade através do fluxo de caixa
- Planejamento financeiro de curto e médio prazo
- Otimização de aplicações financeiras
- Controle de liquidez

### 10.4 Controle Orçamentário
- Planejamento e controle de despesas
- Alinhamento entre despesas e capacidade financeira
- Análise de desvios e correção de rumos
- Transparência na gestão de recursos

### 10.5 Auditoria e Compliance
- Rastreabilidade completa de operações
- Segregação de funções
- Controles de alçada
- Conformidade com normas contábeis e fiscais

---

## 11. CONDIÇÕES DE USO

### 11.1 Visibilidade do Menu
O menu **Movimentos > Financeiro** é exibido quando:
- O parâmetro `Empresa.FLFINANCEIRO` for diferente de "S"

### 11.2 Funcionalidades Condicionais
- **Orçamento de Despesa:** Disponível apenas quando `Empresa.FLAUTDESP = "S"`

### 11.3 Funcionalidades em Favoritos
As seguintes telas podem ser marcadas como favoritas pelo usuário:
- Contas a Pagar
- Contas a Receber
- Apuração de Comissão de Cobrança
- Cobrança
- Reanálise de Crédito
- Troca de Arquivo
- Troca de Arquivo de Crédito
- Conta Corrente
- Fluxo de Caixa
- Previsão de Fluxo de Caixa
- Orçamento de Despesa

---

## 12. PROJETOS TÉCNICOS ENVOLVIDOS

Para referência técnica, os seguintes projetos compõem o módulo:

| Funcionalidade | Projeto Interface | Observação |
|----------------|------------------|------------|
| Contas a Pagar | GEMCOUIFINCPG | Interface de gestão de contas a pagar |
| Contas a Receber | GEMCOUIFINCRC | Interface de gestão de contas a receber |
| Cobrança | GemcoCobranca | Módulo de cobrança e recuperação |
| Conciliação Bancária | GemcoExtratoBancario | Conciliação e extratos |
| Interface Bancária - Cobrança | GemcoInterBanc | Troca de arquivos com bancos |
| Interface Bancária - Conveniadas | GemcoBaixaConv | Integração com operadoras de cartão |
| Tesouraria | GemcoUITesouraria | Gestão de tesouraria e fluxo de caixa |
| Orçamento de Despesa | GemcoOrcDespesa | Controle orçamentário |

---

## 13. FLUXOS DE PROCESSO PRINCIPAIS

### 13.1 Fluxo de Contas a Pagar
1. **Origem:** Entrada de mercadorias, prestação de serviços, contratos
2. **Geração:** Criação manual ou automática do título a pagar
3. **Aprovação:** Validação e aprovação conforme alçadas
4. **Programação:** Inclusão na agenda de pagamentos
5. **Pagamento:** Efetivação do pagamento (cheque, transferência, boleto)
6. **Conciliação:** Confirmação do débito no extrato bancário
7. **Contabilização:** Registro contábil da operação

### 13.2 Fluxo de Contas a Receber
1. **Origem:** Venda realizada, prestação de serviços
2. **Geração:** Criação automática de títulos (nota fiscal) ou manual
3. **Cobrança:** Emissão de boleto/carnê quando aplicável
4. **Acompanhamento:** Monitoramento de vencimentos
5. **Recebimento:** Baixa do título no recebimento
6. **Conciliação:** Confirmação do crédito bancário
7. **Cobrança (se inadimplente):** Encaminhamento para processo de cobrança
8. **Contabilização:** Registro contábil

### 13.3 Fluxo de Cobrança
1. **Identificação:** Títulos vencidos são identificados automaticamente
2. **Classificação:** Definição de prioridades conforme política de cobrança
3. **Ação:** Execução de ações de cobrança (ligação, e-mail, carta)
4. **Registro:** Documentação da ação e resultado
5. **Negociação:** Proposta de renegociação quando necessário
6. **Escalação:** Medidas progressivas (negativação, protesto)
7. **Recebimento:** Baixa após pagamento
8. **Reabilitação:** Liberação de crédito após quitação

### 13.4 Fluxo de Conciliação Bancária
1. **Importação:** Carga do extrato bancário
2. **Conciliação Automática:** Sistema sugere associações
3. **Conciliação Manual:** Ajustes de lançamentos não identificados
4. **Lançamentos Complementares:** Registro de tarifas e outras operações
5. **Fechamento:** Confirmação da conciliação
6. **Análise de Pendências:** Tratamento de diferenças

---

## 14. CONSIDERAÇÕES FINAIS

O módulo **Movimentos > Financeiro** do sistema Gemco Varejo oferece um conjunto completo e integrado de funcionalidades para a gestão financeira empresarial. Através dele, a empresa consegue:

- **Controlar** todas as suas obrigações e direitos financeiros
- **Planejar** seu fluxo de caixa e necessidades de recursos
- **Otimizar** seus processos através de automações e integrações bancárias
- **Analisar** sua performance financeira através de relatórios gerenciais
- **Garantir** compliance e auditabilidade de todas as operações

A arquitetura modular permite que cada funcionalidade opere de forma independente, mas totalmente integrada com as demais, garantindo consistência e confiabilidade das informações.

---

**Documento elaborado a partir da análise do código-fonte do sistema**  
**Base:** `C:\AzureDevOps\VD-Gemco-Varejo\Implement\branches\dev\`  
**Data de Análise:** 2025  
**Versão:** 1.0
