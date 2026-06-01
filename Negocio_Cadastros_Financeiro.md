# Documentação de Negócio - Cadastros Financeiros
## Sistema Gemco Varejo

---

## Introdução

Este documento descreve as funcionalidades de negócio disponíveis no menu **Cadastros > Financeiro** do sistema Gemco Varejo. O objetivo é fornecer uma visão clara e objetiva sobre o que cada funcionalidade faz, para que serve e quais informações podem ser gerenciadas, voltada para usuários de negócio e gestores.

---

## 1. Cadastros de Caixa

As funcionalidades de caixa permitem configurar e gerenciar todos os aspectos relacionados às operações de frente de loja, incluindo terminais de pagamento, formas de recebimento e condições comerciais.

### 1.1 Caixa

**O que é:** Cadastro dos terminais de caixa (PDV - Ponto de Venda) utilizados na loja para realização de vendas e operações financeiras.

**Para que serve:**
- Registrar cada terminal de caixa da loja com suas características e configurações
- Vincular o caixa a uma filial específica
- Configurar integrações com equipamentos fiscais (ECF, SAT, NFC-e)
- Definir parâmetros operacionais do terminal

**Informações gerenciadas:**
- Número identificador do caixa
- Descrição do terminal
- Filial à qual o caixa pertence
- Data de inclusão no sistema
- Controle de integração com Contas a Receber
- Controle de saldo do caixa
- Informações de equipamento fiscal:
  - Número de autorização PDV
  - Número de lacre atual e anterior
  - Modelo de ECF (Emissor de Cupom Fiscal)
  - Modelo fiscal (NFC-e, SAT, etc.)
  - Série de NFC-e para contingência
- Nome do computador na rede (identificação da máquina)
- Operador responsável (para modelos específicos como Totem ou Pagamento Digital)

**Situações de uso:**
- Abertura de um novo ponto de venda na loja
- Troca ou manutenção de equipamento fiscal
- Reconfiguração de parâmetros do caixa
- Controle de lacres de equipamentos fiscais

---

### 1.2 Condição de Pagamento

**O que é:** Cadastro das condições comerciais oferecidas aos clientes para pagamento de suas compras, definindo prazos, parcelas e encargos financeiros.

**Para que serve:**
- Criar e gerenciar planos de pagamento oferecidos pela loja
- Definir número de parcelas e intervalos de vencimento
- Configurar descontos, acréscimos e taxas
- Estabelecer regras de financiamento e tabelas de juros
- Definir quais formas de pagamento podem ser utilizadas em cada condição

**Informações gerenciadas:**
- Código e descrição da condição de pagamento
- Descrição resumida para uso no PDV
- Número de parcelas permitidas
- Intervalos entre vencimentos
- Regras de vencimento (dias fixos, prazos corridos, etc.)
- Formas de pagamento vinculadas (dinheiro, cartão, cheque, etc.)
- Tabelas de taxas de juros por quantidade de parcelas
- Configuração de desconto ou acréscimo
- Tipo de cobrança (à vista, parcelado, etc.)
- Parâmetros operacionais:
  - Permite calcular comissão
  - É devolução
  - Exige documentos específicos
  - Integração contábil
  - Utilização em campanhas promocionais
- Plano de venda associado (para empresas com múltiplas operações)
- Vinculação com árvore de produtos (condições específicas por categoria)
- Parâmetros de Pix Cobrança:
  - Dias de vencimento
  - Dias após vencimento para cobrança
  - Multa e juros aplicáveis

**Situações de uso:**
- Criação de novos planos de pagamento promocionais
- Ajuste de taxas de juros conforme políticas comerciais
- Configuração de condições diferenciadas por tipo de produto
- Definição de regras de parcelamento

---

### 1.3 Formas de Pagamento

**O que é:** Cadastro dos meios de pagamento aceitos pela loja, representando como o cliente pode efetuar o pagamento de suas compras.

**Para que serve:**
- Registrar todos os tipos de pagamento disponíveis no estabelecimento
- Configurar características e comportamentos de cada meio de pagamento
- Estabelecer regras para movimentação financeira
- Integrar com operadoras de cartão e instituições financeiras

**Informações gerenciadas:**
- Código identificador da forma de pagamento
- Descrição completa
- Descrição resumida (usada no PDV)
- Tipo de movimento: Recebimento ou Retirada
- Parâmetros operacionais:
  - Tipo de meio de pagamento (dinheiro, cartão, cheque, vale, etc.)
  - Requer autenticação
  - Permite troco
  - Exige identificação do cliente
  - Integração bancária
  - Controle de limites
- Configurações específicas por tipo:
  - Para cartões: bandeira, tipo (débito/crédito), instituição financeira
  - Para cheques: prazo de compensação, política de aceite
  - Para convênios: empresa conveniada, prazos de repasse
- Taxas e encargos administrativos
- Contas contábeis de lançamento

**Situações de uso:**
- Inclusão de novas bandeiras de cartão
- Configuração de convênios com empresas
- Ajuste de parâmetros de aceite de cheques
- Cadastro de vales e gift cards

---

### 1.4 Movimentos de Caixa

**O que é:** Cadastro dos tipos de movimentações financeiras que podem ocorrer no caixa além das vendas, como sangrias, reforços, pagamentos e recebimentos diversos.

**Para que serve:**
- Definir categorias para entrada e saída de valores no caixa
- Padronizar a classificação de movimentos financeiros
- Facilitar a conciliação e o controle do fluxo de caixa
- Gerar informações gerenciais sobre movimentações

**Informações gerenciadas:**
- Código do tipo de movimento
- Descrição completa
- Descrição resumida
- Classificação do movimento:
  - Recebimento (entrada de valores)
  - Retirada (saída de valores)
- Finalidade do movimento:
  - Sangria (retirada de excesso de numerário)
  - Reforço de troco
  - Pagamento de despesas pequenas
  - Recebimento de valores diversos
  - Devolução de troco
  - Ajustes de caixa

**Situações de uso:**
- Registro de sangria quando há muito dinheiro no caixa
- Reforço de troco no início do dia
- Pagamento de pequenas despesas emergenciais
- Recebimento de valores de outros setores
- Correção de diferenças de caixa

---

### 1.5 Operadores de Caixa

**O que é:** Cadastro dos funcionários autorizados a operar os terminais de caixa, com suas credenciais e permissões.

**Para que serve:**
- Registrar todos os operadores de caixa da empresa
- Controlar acesso aos terminais através de senhas
- Estabelecer limites de desconto por operador
- Vincular operadores a gerentes responsáveis
- Gerenciar cartões de acesso (quando utilizados)

**Informações gerenciadas:**
- Código do operador
- Nome completo
- Login e senha de acesso ao sistema
- Filial de lotação
- Status (ativo/inativo)
- Limite de desconto autorizado (percentual)
- Gerente responsável pela aprovação de operações
- Vínculo com funcionário no sistema de RH
- Informações de cartão de acesso:
  - Utiliza cartão para autenticação
  - Número do cartão

**Situações de uso:**
- Cadastro de novo operador de caixa
- Alteração de senha de acesso
- Ajuste de limite de desconto
- Bloqueio de acesso por desligamento ou afastamento
- Vinculação de cartão de acesso ao operador

---

### 1.6 Plano de Venda

**O que é:** Cadastro de diferentes planos ou modalidades de venda utilizados por empresas que operam em múltiplos segmentos ou formatos comerciais.

**Para que serve:**
- Segregar operações de venda por tipo de negócio
- Permitir análises gerenciais por plano de venda
- Aplicar regras específicas por modalidade de operação
- Facilitar apuração de resultados por linha de negócio

**Informações gerenciadas:**
- Código do plano de venda
- Descrição
- Parâmetros operacionais específicos
- Regras de comissão diferenciadas
- Integrações contábeis específicas

**Observação:** Esta funcionalidade é visível apenas quando a empresa está configurada para trabalhar com múltiplos modelos de negócio (parâmetro FLMULTIEMPRESA = "T").

**Situações de uso:**
- Empresa que opera com loja física e e-commerce
- Negócios com atacado e varejo
- Diferentes formatos de loja (conveniência, supermercado, hipermercado)
- Segregação de vendas para franqueados

---

### 1.7 Cadastro de BIN Gift Card

**O que é:** Cadastro dos códigos BIN (Bank Identification Number) dos cartões gift card (vale-presente) aceitos ou emitidos pela empresa.

**Para que serve:**
- Identificar e validar cartões gift card no momento da venda
- Configurar eventos contábeis e financeiros para movimentação de gift cards
- Estabelecer limites de valores para recarga
- Integrar com sistemas de gestão de vale-presente

**Informações gerenciadas:**
- Código identificador do produto gift card
- Descrição do tipo de gift card
- Número BIN (primeiros 6 dígitos do cartão)
- Evento de Contas a Receber para emissão
- Evento de Contas a Receber para baixa/utilização
- Valor mínimo para recarga
- Valor máximo para recarga

**Observação:** Esta funcionalidade é visível apenas para usuários com permissão específica (código de segurança 1741).

**Situações de uso:**
- Inclusão de novo fornecedor de gift cards
- Cadastro de cartões próprios da rede
- Configuração de limites para recarga
- Ajuste de eventos contábeis para gift cards

---

## 2. Cadastros de Contas a Pagar

Funcionalidades visíveis quando a empresa não utiliza módulo financeiro externo (parâmetro Empresa.FLFINANCEIRO ≠ "S"). Permitem configurar e classificar todas as obrigações financeiras da empresa.

### 2.1 Auxiliares Contas a Pagar

**O que é:** Cadastro de categorias auxiliares para classificação detalhada das contas a pagar, permitindo análises gerenciais mais refinadas.

**Para que serve:**
- Criar subcategorias para organização de despesas
- Facilitar relatórios gerenciais por tipo de gasto
- Permitir análises de custos por departamento ou projeto
- Melhorar a rastreabilidade das despesas

**Informações gerenciadas:**
- Código do auxiliar
- Descrição
- Tipo de classificação
- Vinculação com centros de custo
- Agrupadores para relatórios

**Situações de uso:**
- Classificação de despesas por departamento
- Separação de custos fixos e variáveis
- Categorização por projeto ou obra
- Análise de despesas por natureza

---

### 2.2 Eventos de Contas a Pagar

**O que é:** Cadastro dos tipos de eventos que geram obrigações financeiras a pagar, representando as diferentes naturezas de despesas da empresa.

**Para que serve:**
- Classificar as contas a pagar por natureza da despesa
- Estabelecer tratamento contábil para cada tipo de obrigação
- Definir regras de pagamento e integração bancária
- Facilitar análises de gastos por categoria

**Informações gerenciadas:**
- Código do evento
- Descrição completa
- Tipo de evento (despesa operacional, fiscal, financeira, etc.)
- Configurações contábeis:
  - Conta contábil de lançamento
  - Centro de custo padrão
  - Histórico contábil
- Parâmetros operacionais:
  - Exige nota fiscal
  - Permite rateio por centro de custo
  - Gera retenção de impostos
  - Integração com livros fiscais
- Regras de pagamento:
  - Forma de pagamento padrão
  - Necessidade de autorização
  - Limites de alçada

**Situações de uso:**
- Cadastro de nova categoria de despesa
- Configuração de eventos para impostos específicos
- Definição de tratamento para pagamentos a fornecedores
- Criação de evento para despesas especiais (ex: obras, campanhas)

---

### 2.3 Origem Contas a Pagar

**O que é:** Cadastro das origens ou fontes geradoras das contas a pagar, identificando de onde surgem as obrigações financeiras.

**Para que serve:**
- Identificar a origem de cada título a pagar
- Permitir rastreamento desde a origem até a quitação
- Segregar análises por tipo de operação geradora
- Controlar integrações com outros módulos do sistema

**Informações gerenciadas:**
- Código da origem
- Descrição
- Tipo de operação:
  - Compra de mercadorias
  - Compra de ativos
  - Despesas operacionais
  - Impostos e taxas
  - Empréstimos e financiamentos
  - Devoluções a clientes
- Parâmetros de integração:
  - É contábil (gera lançamento contábil)
  - É devolução
  - Exige documento fiscal
  - Gera diário auxiliar
  - Calcula comissão (para devoluções)
- Empresa vinculada (para controle em grupos empresariais)
- Indica se é mercadoria para revenda

**Situações de uso:**
- Entrada de nota fiscal de compra
- Registro de despesas administrativas
- Lançamento de impostos a recolher
- Devolução de mercadorias a fornecedores
- Registro de parcelas de financiamentos

---

### 2.4 Autorização - Gerenciamento de Orçamento e Despesas

Submenu visível quando a empresa utiliza controle de autorização de despesas (parâmetro Empresa.FLAUTDESP = "S").

#### 2.4.1 Usuário Orçamento

**O que é:** Cadastro de usuários autorizados a gerenciar orçamentos de despesas, com definição de alçadas e responsabilidades.

**Para que serve:**
- Estabelecer hierarquia de aprovação de despesas
- Definir limites orçamentários por usuário
- Controlar acesso ao sistema de autorização
- Gerenciar responsáveis por centros de custo

**Informações gerenciadas:**
- Identificação do usuário
- Centros de custo sob sua responsabilidade
- Limites de aprovação de despesas
- Níveis de alçada
- Substitutos em caso de ausência

**Situações de uso:**
- Cadastro de novo gestor de orçamento
- Definição de alçadas de aprovação
- Reorganização de responsabilidades
- Configuração de fluxo de aprovação

---

#### 2.4.2 Usuário Credenciado

**O que é:** Cadastro de usuários autorizados a solicitar despesas dentro do sistema de controle orçamentário.

**Para que serve:**
- Registrar colaboradores que podem solicitar gastos
- Vincular solicitantes a centros de custo
- Estabelecer limites de solicitação
- Controlar quem pode gerar requisições de compra

**Informações gerenciadas:**
- Identificação do solicitante
- Departamento/setor
- Centro de custo de origem
- Limites de solicitação
- Tipos de despesa autorizados
- Aprovadores responsáveis

**Situações de uso:**
- Habilitação de colaborador para solicitar compras
- Definição de limites de gastos por solicitante
- Vínculo de funcionário a departamento
- Controle de autorizações de despesa

---

#### 2.4.3 Verbas de Despesas

**O que é:** Cadastro de verbas orçamentárias disponíveis para despesas, com controle de saldos e consumo.

**Para que serve:**
- Estabelecer orçamentos por natureza de despesa
- Controlar saldo disponível de cada verba
- Bloquear despesas sem saldo orçamentário
- Gerar informações gerenciais de consumo de orçamento

**Informações gerenciadas:**
- Código e descrição da verba
- Valor orçado (anual, mensal, por período)
- Saldo disponível
- Valor consumido
- Valor comprometido (solicitações pendentes)
- Período de vigência
- Centro de custo associado
- Responsável pela verba

**Situações de uso:**
- Definição de orçamento anual por categoria de despesa
- Acompanhamento de consumo de verba
- Aprovação de despesas dentro do orçamento disponível
- Bloqueio de gastos sem cobertura orçamentária
- Análise de realizado versus orçado

---

## 3. Cadastros de Contas a Receber

Funcionalidades visíveis quando a empresa não utiliza módulo financeiro externo (parâmetro Empresa.FLFINANCEIRO ≠ "S"). Permitem configurar e classificar todos os direitos e recebíveis da empresa.

### 3.1 Origem Contas a Receber

**O que é:** Cadastro das origens ou fontes geradoras das contas a receber, identificando de onde surgem os créditos da empresa.

**Para que serve:**
- Identificar a origem de cada título a receber
- Permitir rastreamento desde a geração até o recebimento
- Segregar análises por tipo de operação
- Controlar integrações com outros módulos

**Informações gerenciadas:**
- Código da origem
- Descrição
- Tipo de operação:
  - Venda de mercadorias
  - Prestação de serviços
  - Venda de ativos
  - Juros e multas
  - Outras receitas
- Parâmetros de integração:
  - É contábil (gera lançamento contábil)
  - Gera diário auxiliar
  - Permite cobrança bancária
  - Calcula comissão sobre recebimento
- Regras de cobrança:
  - Envia para protesto
  - Gera carta de cobrança
  - Permite renegociação
  - Aceita desconto
- Eventos contábeis associados

**Situações de uso:**
- Venda a prazo no PDV
- Faturamento de pedidos
- Prestação de serviços
- Cobrança de juros de mora
- Receitas diversas

---

### 3.2 Eventos de Contas a Receber

**O que é:** Cadastro dos tipos de eventos relacionados ao ciclo de vida dos títulos a receber, desde a geração até a baixa.

**Para que serve:**
- Classificar movimentações nos títulos a receber
- Estabelecer tratamento contábil para cada evento
- Definir comportamento do sistema em cada situação
- Facilitar análises de inadimplência e recuperação

**Informações gerenciadas:**
- Código do evento
- Descrição
- Tipo de evento:
  - Emissão de título
  - Baixa por recebimento
  - Baixa por desconto
  - Baixa por devolução
  - Protesto
  - Renegociação
  - Ajustes diversos
- Configurações contábeis:
  - Contas contábeis envolvidas
  - Centro de custo
  - Histórico padrão
- Parâmetros operacionais:
  - Altera situação do título
  - Gera multa e juros
  - Permite desconto
  - Integra com cobrança bancária
  - Atualiza saldo devedor do cliente

**Situações de uso:**
- Recebimento de duplicatas
- Baixa de títulos com desconto
- Registro de protestos
- Renegociação de dívidas
- Ajustes por erro de lançamento
- Devolução de mercadorias com estorno de título

---

### 3.3 Auxiliares

**O que é:** Cadastro de classificações auxiliares para títulos a receber, permitindo análises complementares além da classificação padrão.

**Para que serve:**
- Criar subcategorias para organização de recebíveis
- Facilitar relatórios gerenciais específicos
- Permitir análises por vendedor, região, campanha, etc.
- Melhorar a rastreabilidade dos créditos

**Informações gerenciadas:**
- Código do auxiliar
- Descrição
- Tipo de classificação:
  - Por vendedor
  - Por região
  - Por campanha promocional
  - Por tipo de cliente
  - Por produto/serviço
- Agrupadores para relatórios
- Regras de comissionamento associadas

**Situações de uso:**
- Análise de recebimentos por vendedor
- Segregação de títulos por campanha
- Classificação por região geográfica
- Agrupamento por linha de produto
- Análise de performance de canais de venda

---

## 4. Cadastros Gerais Financeiros

Funcionalidades gerais do módulo financeiro, visíveis quando a empresa não utiliza sistema financeiro externo (parâmetro Empresa.FLFINANCEIRO ≠ "S").

### 4.1 Cadastro de Grupo Econômico

**O que é:** Cadastro de grupos empresariais ou econômicos, permitindo vincular empresas relacionadas para análises consolidadas e controles de crédito integrados.

**Para que serve:**
- Agrupar empresas do mesmo grupo empresarial
- Consolidar análises de crédito do grupo
- Compartilhar limites de crédito entre empresas relacionadas
- Gerar relatórios consolidados
- Controlar garantias cruzadas

**Informações gerenciadas:**
- Código do grupo econômico
- Razão social do grupo
- CNPJ da controladora
- Empresas participantes do grupo
- Limite de crédito consolidado
- Saldo devedor total do grupo
- Responsáveis legais
- Dados de contato do grupo

**Situações de uso:**
- Cliente com múltiplas empresas
- Análise de crédito consolidada
- Controle de limite compartilhado
- Garantias entre empresas do grupo
- Relatórios consolidados de inadimplência

---

### 4.2 Convênios

**O que é:** Cadastro de convênios e acordos comerciais com empresas para vendas com pagamento diferenciado através de descontos em folha ou repasse posterior.

**Para que serve:**
- Registrar empresas conveniadas
- Estabelecer regras de pagamento e repasse
- Configurar prazos e condições especiais
- Controlar limites por convênio
- Gerenciar autorização de compras

**Informações gerenciadas:**
- Código e razão social da empresa conveniada
- CNPJ e dados cadastrais
- Tipo de convênio (desconto em folha, crédito rotativo, etc.)
- Regras de pagamento:
  - Prazo de repasse
  - Percentual de desconto administrativo
  - Limite global de crédito
  - Limite individual por funcionário
- Dados bancários para repasse
- Contato responsável pelo convênio
- Documentação exigida para autorização
- Validade do convênio

**Situações de uso:**
- Vendas a funcionários de empresas conveniadas
- Autorização de compras com desconto em folha
- Geração de arquivo para repasse ao convênio
- Controle de limites individuais e globais
- Renovação de contratos de convênio

---

### 4.3 Convênio Bancário

**O que é:** Cadastro de convênios estabelecidos com instituições bancárias para operações específicas como cobrança bancária, boletos e integração de pagamentos/recebimentos.

**Para que serve:**
- Registrar convênios bancários para cobrança
- Configurar parâmetros para geração de boletos
- Estabelecer regras de remessa e retorno bancário
- Definir códigos e instruções específicas do banco
- Gerenciar múltiplos convênios por banco

**Informações gerenciadas:**
- Banco e agência
- Número do convênio/código do cedente
- Conta corrente vinculada
- Tipo de cobrança (simples, registrada, etc.)
- Carteira de cobrança
- Instruções bancárias padrão (protesto, juros, multa)
- Sequencial de remessa
- Dados do cedente (empresa):
  - Razão social
  - CNPJ
  - Endereço completo
- Configurações de arquivo de remessa/retorno:
  - Layout (CNAB 240, CNAB 400, etc.)
  - Diretórios de arquivo
- Parâmetros de boleto:
  - Dados para impressão
  - Instruções padrão
  - Mensagens

**Situações de uso:**
- Configuração de novo convênio bancário
- Geração de boletos bancários
- Envio de arquivo de remessa ao banco
- Processamento de arquivo de retorno
- Alteração de instruções de cobrança
- Gestão de múltiplas carteiras de cobrança

---

### 4.4 Empresas Conveniadas

**O que é:** Cadastro complementar de empresas que mantém convênio comercial com a loja, com informações específicas para controle de vendas conveniadas.

**Para que serve:**
- Detalhar informações operacionais de empresas conveniadas
- Controlar autorização de compras de funcionários
- Gerenciar limites e condições específicas
- Facilitar o processo de validação no PDV

**Informações gerenciadas:**
- Identificação da empresa conveniada
- Lista de funcionários autorizados
- Limites individuais de crédito
- Limites por período (mensal, quinzenal)
- Dados para autorização:
  - Matrícula do funcionário
  - CPF
  - Margem consignável
- Status do convênio (ativo, suspenso, cancelado)
- Histórico de compras

**Situações de uso:**
- Consulta de funcionário autorizado no PDV
- Verificação de limite disponível
- Inclusão de novos funcionários autorizados
- Suspensão temporária de autorização
- Atualização de limites de crédito

---

### 4.5 Índice Econômico

**O que é:** Cadastro de índices econômicos e financeiros utilizados para correção monetária, reajustes e cálculos financeiros.

**Para que serve:**
- Registrar índices oficiais (IGPM, IPCA, SELIC, etc.)
- Manter histórico de valores dos índices
- Permitir cálculos de correção monetária
- Apoiar reajustes contratuais
- Facilitar cálculos de juros e multas

**Informações gerenciadas:**
- Código e nome do índice (IGPM, IPCA, INPC, CDI, SELIC, etc.)
- Sigla e descrição
- Periodicidade (mensal, anual, diário)
- Histórico de valores:
  - Data de referência
  - Valor do índice
  - Variação percentual
- Fonte de publicação
- Utilização padrão no sistema

**Situações de uso:**
- Correção de valores em contratos
- Cálculo de juros de mora
- Atualização de títulos em atraso
- Reajuste de preços
- Cálculos financeiros diversos
- Análises econômicas e projeções

---

### 4.6 Portadores

**O que é:** Cadastro de instituições financeiras, bancos, administradoras de cartão e outros portadores de títulos com os quais a empresa mantém relacionamento.

**Para que serve:**
- Registrar bancos e instituições financeiras
- Gerenciar contas correntes da empresa
- Configurar integração bancária
- Controlar recebimentos via cartão
- Estabelecer regras de liquidação financeira

**Informações gerenciadas:**
- Código e nome do portador
- Tipo de portador:
  - Banco comercial
  - Administradora de cartão
  - Cooperativa de crédito
  - Financeira
  - Outros
- Dados cadastrais:
  - CNPJ
  - Endereço completo
  - Contatos
- Dados bancários:
  - Código do banco (FEBRABAN)
  - Agência e dígito
  - Conta corrente e dígito
  - Tipo de conta
- Parâmetros operacionais:
  - Taxa de administração (para cartões)
  - Prazo de repasse
  - Valor mínimo para solicitação de transferência
  - Obriga CPF/Nome no recebimento
- Configurações de integração:
  - Interface bancária (remessa/retorno)
  - Conciliação automática
- Informações para cobrança:
  - Dados para emissão de boletos
  - Convênios vinculados
- Juros e multas configuráveis
- Rotas de cobrança (para títulos físicos)

**Situações de uso:**
- Abertura de nova conta bancária
- Cadastro de nova administradora de cartão
- Configuração de taxas e prazos de repasse
- Integração para conciliação bancária
- Emissão de boletos
- Controle de recebimentos por portador
- Análise de custos financeiros por instituição

---

### 4.7 Cadastro de Rateio por Centro de Custo

**O que é:** Cadastro de modelos de rateio pré-definidos para distribuição automática de despesas entre diferentes centros de custo.

**Para que serve:**
- Criar regras de rateio de despesas comuns
- Automatizar distribuição de custos fixos
- Facilitar alocação de despesas compartilhadas
- Manter consistência na apropriação de custos
- Agilizar o processo de lançamento contábil

**Informações gerenciadas:**
- Código e descrição do rateio
- Tipo de rateio (fixo, percentual, por valor)
- Centros de custo envolvidos
- Percentuais ou valores de distribuição
- Validade do rateio
- Natureza de despesas aplicável
- Regras de aplicação automática

**Situações de uso:**
- Rateio de aluguel entre departamentos
- Distribuição de custos de energia e água
- Alocação de despesas administrativas
- Rateio de depreciação de ativos compartilhados
- Distribuição proporcional de custos comuns

---

### 4.8 Situação de Títulos

**O que é:** Cadastro dos possíveis status ou situações em que um título financeiro (a pagar ou receber) pode se encontrar durante seu ciclo de vida.

**Para que serve:**
- Classificar a situação atual de cada título
- Controlar o fluxo de tratamento de títulos
- Permitir filtros e relatórios por situação
- Estabelecer regras de transição entre situações
- Facilitar gestão de cobranças e pagamentos

**Informações gerenciadas:**
- Código da situação
- Descrição
- Tipo (situação de pagar ou receber)
- Categoria:
  - Em aberto
  - Vencido
  - Em cobrança
  - Protestado
  - Em negociação
  - Quitado
  - Cancelado
  - Suspenso
- Comportamento no sistema:
  - Conta no saldo devedor/credor
  - Permite baixa
  - Gera juros e multa
  - Aparece em relatórios de pendências
  - Bloqueia novas operações
- Próximas situações possíveis (fluxo)
- Exige justificativa para alteração

**Situações de uso:**
- Controle de títulos em aberto
- Identificação de títulos vencidos
- Gestão de títulos em cobrança
- Rastreamento de títulos protestados
- Análise de inadimplência
- Relatórios de aging (títulos por período de vencimento)
- Bloqueio de clientes com títulos em atraso

---

## 5. Cadastros de Tesouraria

Funcionalidades de tesouraria, visíveis quando a empresa não utiliza sistema financeiro externo (parâmetro Empresa.FLFINANCEIRO ≠ "S").

### 5.1 Cadastro Bancário

**O que é:** Cadastro centralizado e integrado das informações bancárias da empresa, incluindo bancos, agências e contas correntes.

**Para que serve:**
- Gerenciar de forma integrada todas as informações bancárias
- Cadastrar e manter bancos, agências e contas em um único local
- Configurar parâmetros para integração bancária
- Estabelecer relacionamento entre filiais e contas bancárias
- Facilitar operações de tesouraria e conciliação

**Informações gerenciadas:**

**Nível Banco:**
- Código do banco (FEBRABAN)
- Nome da instituição
- CNPJ
- Dados de contato
- Site/URL para acesso

**Nível Agência:**
- Código da agência
- Dígito verificador
- Endereço completo
- Telefones
- Gerente responsável
- E-mail

**Nível Conta Corrente:**
- Número da conta
- Dígito verificador
- Tipo de conta (corrente, poupança, aplicação)
- Filial titular da conta
- Saldo atual
- Limites de crédito
- Conta contábil vinculada
- Status (ativa, bloqueada, encerrada)
- Finalidade da conta (operacional, investimentos, folha de pagamento)
- Dados para integração bancária
- Convênios vinculados
- Sequencial de documentos (cheques, ordens de pagamento)

**Observação:** Acesso disponível apenas para usuários com permissão de consulta em Banco, Agência ou Conta Corrente.

**Situações de uso:**
- Abertura de nova conta bancária
- Cadastro de banco não existente no sistema
- Atualização de dados de agências
- Configuração de contas por filial
- Definição de contas para finalidades específicas
- Integração para conciliação bancária automática
- Gestão de múltiplas contas por filial
- Controle de saldos e limites bancários

---

## 6. Impressoras Fiscais (ECF)

### 6.1 Impressoras Fiscais (ECF)

**O que é:** Cadastro e gerenciamento das impressoras fiscais ECF (Emissor de Cupom Fiscal) utilizadas nos pontos de venda.

**Para que serve:**
- Registrar todas as impressoras fiscais da empresa
- Controlar credenciamento e situação fiscal dos equipamentos
- Gerenciar parâmetros técnicos das impressoras
- Facilitar manutenção e substituição de equipamentos
- Atender exigências fiscais de controle de ECF

**Informações gerenciadas:**
- Número do caixa associado
- CNPJ da empresa (estabelecimento)
- Modelo da impressora fiscal
- Tipo/fabricante da impressora
- Número de série do equipamento
- Código Nacional de Identificação do ECF
- Número de credenciamento junto à SEFAZ
- Status da impressora:
  - Ativa
  - Inativa
  - Em manutenção
  - Lacrada
- Parâmetros de impressão:
  - Configurações de DAV (Documento Auxiliar de Venda)
  - Habilitação de impressão de DAV
- Data de instalação
- Data de lacração
- Versão do software básico
- GT (Grande Total) atual
- Contador de reduções Z
- Histórico de intervenções técnicas

**Situações de uso:**
- Instalação de nova impressora fiscal
- Registro de credenciamento junto à SEFAZ
- Controle de manutenções e intervenções técnicas
- Substituição de equipamento
- Lacração após manutenção
- Desativação de equipamento
- Consulta para obrigações fiscais (EFD, SPED Fiscal)
- Atendimento a fiscalização
- Habilitação/desabilitação de impressão de DAV

---

## Considerações Finais

### Integração entre Módulos

As funcionalidades descritas neste documento são altamente integradas entre si e com outros módulos do sistema:

- **Caixa** integra-se com **Vendas**, **NFC-e**, **Contas a Receber** e **Estoque**
- **Condições e Formas de Pagamento** são utilizadas em todo o ciclo comercial
- **Contas a Pagar** integra-se com **Compras**, **Contabilidade** e **Tesouraria**
- **Contas a Receber** integra-se com **Vendas**, **Cobrança** e **Tesouraria**
- **Cadastros Gerais** servem de base para todos os módulos financeiros
- **Tesouraria** consolida informações de recebimentos e pagamentos

### Segurança e Permissões

Diversas funcionalidades possuem controles de segurança específicos:
- Códigos de segurança controlam acesso a cada menu
- Algumas funcionalidades exigem permissões especiais
- Certos cadastros são visíveis apenas sob condições específicas (parâmetros do sistema)
- Alçadas de aprovação limitam ações por perfil de usuário

### Parametrizações

Muitas funcionalidades dependem de parâmetros gerais do sistema:
- **FLFINANCEIRO**: controla uso de módulo financeiro integrado ou externo
- **FLMULTIEMPRESA**: habilita recursos para grupos empresariais
- **FLAUTDESP**: ativa controle de autorização de despesas
- **FLCONTROLASLDCXA**: habilita controle de saldo de caixa

### Manutenção dos Cadastros

Para garantir o bom funcionamento do sistema:
- Mantenha os cadastros sempre atualizados
- Revise periodicamente parâmetros e configurações
- Não exclua registros vinculados a movimentações
- Faça backup antes de alterações em massa
- Documente customizações e regras específicas do negócio

---

## Glossário de Termos

**BIN**: Bank Identification Number - primeiros 6 dígitos de um cartão que identificam a instituição emissora

**ECF**: Emissor de Cupom Fiscal - equipamento fiscal homologado para emissão de cupons fiscais

**NFC-e**: Nota Fiscal de Consumidor Eletrônica - documento fiscal eletrônico que substitui o cupom fiscal

**SAT**: Sistema Autenticador e Transmissor - equipamento fiscal para emissão de CF-e-SAT

**PDV**: Ponto de Venda - terminal de caixa utilizado para vendas

**Gift Card**: Cartão presente ou vale-presente que pode ser adquirido e utilizado como meio de pagamento

**Aging**: Relatório que classifica títulos por período de vencimento/atraso

**Cedente**: Empresa que emite boletos bancários (credor)

**Convênio**: Acordo comercial para vendas com pagamento diferenciado

**Centro de Custo**: Unidade organizacional para apropriação e controle de custos

**Lacre**: Selo de segurança aplicado em equipamento fiscal após intervenção técnica

---

**Documento gerado em:** 2024  
**Versão:** 1.0  
**Sistema:** Gemco Varejo  
**Tipo:** Documentação de Negócio - Cadastros Financeiros
