# Documentação de Negócio - Relatórios Financeiro

**Sistema ERP Gemco - Módulo Financeiro**  
**Menu:** Informações > Relatórios > Financeiro

---

## Sumário Executivo

Este documento descreve as funcionalidades de negócio disponíveis no menu de Relatórios Financeiros do sistema ERP Gemco. O módulo está organizado em 4 categorias principais que abrangem todo o ciclo financeiro da empresa:

- **Contas a Pagar**: 6 relatórios para gestão de pagamentos e fornecedores
- **Contas a Receber**: 8 relatórios para gestão de recebimentos e clientes
- **Tesouraria**: 3 relatórios para controle de fluxo de caixa e bancos
- **Interface de Conveniadas**: 2 relatórios para conciliação com empresas conveniadas

**Total de Funcionalidades:** 19 relatórios gerenciais

---

## 1. CONTAS A PAGAR

### 1.1 Cheques Emitidos

**Objetivo:**  
Permite visualizar todos os cheques emitidos pela empresa em uma data específica, facilitando o controle dos pagamentos realizados através deste meio de pagamento.

**Informações Apresentadas:**
- Data de emissão dos cheques
- Informações dos cheques emitidos no dia
- Dados dos títulos pagos com cheque
- Valores dos pagamentos
- Resumo por filial de origem (opcional)

**Filtros Disponíveis:**
- **Data de Emissão**: Data específica para consulta dos cheques emitidos (campo obrigatório)
- **Resumo por Filial de Origem**: Opção para exibir totalização por filial

**Caso de Uso Típico:**  
O gestor financeiro precisa conferir todos os cheques que foram emitidos em um dia específico para realizar a conciliação bancária ou para verificar os pagamentos efetuados. Ao informar a data, o sistema gera um relatório completo com todos os cheques emitidos, possibilitando ainda visualizar um resumo consolidado por filial quando a empresa possui múltiplas unidades.

---

### 1.2 Diário Auxiliar de Fornecedor

**Objetivo:**  
Gera o livro diário auxiliar de fornecedores, documento contábil obrigatório que registra cronologicamente todas as movimentações financeiras com fornecedores, incluindo entradas de mercadorias e pagamentos efetuados.

**Informações Apresentadas:**
- Movimentação cronológica com fornecedores
- Entradas de mercadorias/serviços (notas fiscais)
- Pagamentos realizados
- Saldos em aberto
- Informações fiscais e contábeis
- Totalizações por fornecedor, filial ou período

**Filtros Disponíveis:**
- **Tipo de Relatório**: Analítico (detalhado) ou Sintético (resumido)
- **Período**: Data inicial e final para consulta
- **Filial**: Filtro por filial específica
- **Tipo de Emitente**: Fornecedor, Banco ou Transportadora
- **Fornecedor Específico**: Consulta de um fornecedor em particular
- **Quebra de Página**: Por data, fornecedor ou sem quebra
- **Tipo de Movimentação**: Entradas, Pagamentos ou ambos
- **Relatório Geral**: Opção para incluir todas as movimentações
- **Modo Definitivo**: Para impressão oficial do livro contábil com numeração
  - Mês de Referência
  - Número do Livro

**Caso de Uso Típico:**  
A área contábil precisa emitir mensalmente o diário auxiliar de fornecedores para atender às exigências fiscais e contábeis. O contador seleciona o mês de referência, marca a opção "Definitivo" e informa o número do livro para gerar o documento oficial. Para análises gerenciais, o gestor pode emitir relatórios analíticos de períodos específicos filtrados por fornecedor ou filial para acompanhar as transações realizadas.

---

### 1.3 Extrato de Fornecedor

**Objetivo:**  
Apresenta o histórico completo de movimentações financeiras com um fornecedor específico, mostrando entradas, pagamentos, saldo devedor e todas as transações realizadas em um período determinado.

**Informações Apresentadas:**
- Saldo anterior do fornecedor
- Entradas de mercadorias (notas fiscais) com valores
- Pagamentos realizados com detalhamento
- Abatimentos e descontos concedidos
- Juros e encargos calculados
- Saldo atual em aberto
- Dados do emitente (fornecedor, banco ou transportadora)
- Origem das transações (compras, devoluções, etc.)

**Filtros Disponíveis:**
- **Mês/Ano de Referência**: Período base para o extrato (utiliza data do último fechamento)
- **Período de Movimentação**: Data inicial e final das transações
- **Filial/Origem**: Filtro por filial ou origem das operações
- **Tipo de Emitente**: Fornecedor (padrão), Banco ou Transportadora
- **Emitente Específico**: Código ou nome do fornecedor/emitente
- **Modo de Visualização**: Detalhado ou consolidado

**Caso de Uso Típico:**  
O departamento de compras precisa verificar o histórico de transações com um fornecedor para negociar pagamentos em atraso ou confirmar o saldo devedor antes de realizar uma nova compra. Informa-se o período desejado e o código do fornecedor, gerando um extrato completo que mostra todas as notas fiscais de entrada, os pagamentos já efetuados e o saldo atual em aberto, facilitando a negociação e o controle financeiro com o fornecedor.

---

### 1.4 Pagamentos Efetuados

**Objetivo:**  
Lista todos os pagamentos realizados pela empresa em um determinado período, permitindo acompanhar o fluxo de saída de recursos, analisar os valores pagos por fornecedor e controlar a execução financeira.

**Informações Apresentadas:**
- Data do pagamento
- Fornecedor/emitente
- Número e descrição do título pago
- Filial responsável
- Origem do título (compra, serviço, despesa, etc.)
- Data de emissão e vencimento original
- Valor original do título
- Valor do lançamento (pagamento)
- Abatimentos aplicados
- Juros pagos
- Forma de pagamento (cheque, transferência, etc.)
- Dados bancários quando aplicável
- Nome do favorecido em pagamentos via cheque
- Totalizações por período e tipo

**Filtros Disponíveis:**
- **Período de Pagamento**: Data inicial e final (obrigatório)
- **Filial**: Filtro por filial específica ou todas
- **Tipo de Emitente**: Fornecedor, Banco ou Transportadora
- **Emitente Específico**: Consulta pagamentos de um fornecedor em particular
- **Agrupar por Conta Corrente**: Consolida pagamentos realizados na mesma conta bancária
- **Filtros Adicionais**: Possibilidade de aplicar outras condições de pesquisa

**Caso de Uso Típico:**  
O gerente financeiro precisa apresentar à diretoria um relatório de todos os pagamentos efetuados no mês para análise do fluxo de caixa. Selecionando o período desejado, o sistema gera uma lista completa de todos os pagamentos realizados, discriminando valores originais, juros pagos e abatimentos obtidos. Este relatório também é útil para auditorias internas e para identificar padrões de pagamento que podem ser otimizados.

---

### 1.5 Posição Retroativa de Contas a Pagar

**Objetivo:**  
Permite visualizar a posição histórica das contas a pagar em uma data passada específica, possibilitando análises retroativas do endividamento da empresa e comparações com períodos anteriores.

**Informações Apresentadas:**
- Títulos em aberto na data de referência
- Valores a vencer
- Valores vencidos
- Fornecedores credores
- Filiais com débitos
- Análise de vencimentos
- Comparativos de períodos

**Filtros Disponíveis:**
- **Data de Referência**: Data específica no passado para análise
- **Filial**: Visualização por filial ou consolidado
- **Tipo de Emitente**: Fornecedor, Banco ou Transportadora
- **Status dos Títulos**: Em aberto, vencidos ou todos
- **Forma de Apresentação**: Analítico ou sintético

**Caso de Uso Típico:**  
A controladoria precisa comparar a posição de endividamento atual com a de 6 meses atrás para avaliar a evolução do passivo da empresa. Informando a data retroativa desejada, o sistema apresenta qual era a real situação das contas a pagar naquele momento específico, permitindo análises precisas de tendências e auxiliando na tomada de decisões estratégicas sobre gestão de capital de giro.

---

### 1.6 Análise de Despesas x Faturamento

**Objetivo:**  
Compara as despesas realizadas pela empresa com o faturamento obtido no mesmo período, permitindo análise de rentabilidade, controle orçamentário e gestão de custos por centro de custo.

**Informações Apresentadas:**
- Despesas realizadas por centro de custo
- Faturamento do período
- Percentual de despesas sobre o faturamento
- Comparativo orçado x realizado
- Análise de desvios
- Evolução temporal das despesas
- Indicadores de rentabilidade

**Filtros Disponíveis:**
- **Período**: Data inicial e final para análise (obrigatório)
- **Centro de Custo**: Filtro por centro de custo específico ou todos
  - *Nota: Usuários podem ter restrição para visualizar apenas centros de custo autorizados*
- **Tipo de Relatório**: Analítico ou Sintético
- **Formato de Saída**: Tela, impressora ou PDF
- **Caminho para PDF**: Local para salvar o arquivo quando opção PDF selecionada

**Caso de Uso Típico:**  
O controller precisa avaliar se as despesas operacionais estão dentro do planejado e qual o impacto no resultado da empresa. Ao selecionar o período mensal e os centros de custo relevantes, o sistema gera uma análise comparativa mostrando quanto foi gasto em cada área versus o faturamento realizado. Isso permite identificar centros de custo com despesas acima do esperado e tomar ações corretivas imediatas para manter a rentabilidade da operação.

**Observação Importante:**  
Esta funcionalidade só é exibida no menu quando a empresa possui o módulo de orçamento de despesas ativado (configuração FLAUTDESP = "S").

---

## 2. CONTAS A RECEBER

### 2.1 Recebimentos Realizados por Período

**Objetivo:**  
Apresenta todos os recebimentos efetivamente realizados pela empresa em um determinado período, permitindo análise do fluxo de entrada de recursos, acompanhamento de metas de recebimento e gestão do contas a receber.

**Informações Apresentadas:**
- Data dos recebimentos
- Clientes que efetuaram pagamentos
- Valores recebidos
- Formas de recebimento (dinheiro, cheque, cartão, etc.)
- Filial responsável pelo recebimento
- Vendedor vinculado (quando aplicável)
- Origem do título (venda, prestação de serviço, etc.)
- Descontos concedidos
- Juros recebidos
- Total consolidado por período
- Opções de visualização: Analítico (detalhado) ou Sintético (resumido)

**Filtros Disponíveis:**
- **Período de Recebimento**: Data inicial e final (obrigatório)
- **Filial**: Filtro por filial do título ou filial do pedido
  - Filial específica ou todas as filiais
- **Tipo de Relatório**: 
  - Sintético: Totalizações e resumos
  - Analítico: Detalhamento completo de cada recebimento

**Caso de Uso Típico:**  
O gerente comercial precisa avaliar o desempenho de recebimentos do mês para verificar se as metas foram atingidas. Selecionando o período mensal e a opção de relatório sintético, obtém rapidamente os totais recebidos por filial e forma de pagamento. Para análises mais detalhadas ou investigação de divergências, pode gerar o relatório analítico que mostra cada transação individualmente, incluindo descontos concedidos e juros cobrados.

---

### 2.2 Acompanhamento de Inadimplência

**Objetivo:**  
Monitora e analisa a inadimplência da carteira de clientes através de diferentes visões gerenciais, permitindo identificar tendências, focos de problema e auxiliar na definição de estratégias de cobrança.

**Informações Apresentadas:**
- Valores em atraso por cliente
- Aging (antiguidade) dos títulos vencidos
- Taxa de inadimplência por período
- Análise comparativa mensal
- Distribuição da inadimplência por:
  - Consolidado geral
  - Portador/Forma de pagamento
  - Situação do título
  - Filial
  - Vendedor
- Evolução temporal da inadimplência
- Indicadores de risco

**Filtros Disponíveis:**
- **Período de Análise**: Data inicial e final para avaliação
- **Tipo de Visão** (múltiplas opções podem ser selecionadas):
  - Consolidado: Visão geral da inadimplência
  - Por Portador: Análise por forma de recebimento
  - Por Situação: Status dos títulos em atraso
  - Por Filial: Inadimplência por unidade
  - Por Vendedor: Análise por responsável comercial
- **Opções de Quebra**: Define agrupamentos no relatório
- **Período Secundário**: Permite comparações entre períodos diferentes

**Caso de Uso Típico:**  
O gerente financeiro realiza mensalmente uma análise da inadimplência para apresentar à diretoria. Primeiro, gera o relatório consolidado para ter uma visão macro do problema. Em seguida, analisa a inadimplência por vendedor para identificar quais profissionais precisam de apoio na gestão de crédito de seus clientes. Por fim, avalia a inadimplência por filial para direcionar esforços de cobrança nas unidades com maior concentração de atrasos, otimizando os recursos da equipe de cobrança.

---

### 2.3 Clientes Inadimplentes

**Objetivo:**  
Lista todos os clientes que possuem títulos vencidos e em aberto, fornecendo informações detalhadas para ações de cobrança e análise de risco de crédito.

**Informações Apresentadas:**
- Nome e código do cliente inadimplente
- Títulos vencidos (número, data de vencimento)
- Valor original dos títulos
- Valores atualizados com juros e correção
- Dias de atraso
- Total da dívida por cliente
- Filial responsável
- Forma de pagamento original
- Situação atual do título
- Dados de contato do cliente

**Filtros Disponíveis:**
- **Data de Referência**: Data base para considerar títulos vencidos
- **Filial**: Filtro por filial específica ou todas
- **Faixa de Atraso**: Filtrar por quantidade de dias em atraso
- **Valor Mínimo**: Considerar apenas débitos acima de determinado valor
- **Situação do Título**: Status específico ou todos
- **Ordenação**: Por nome do cliente, valor da dívida, dias de atraso, etc.

**Caso de Uso Típico:**  
A equipe de cobrança inicia o dia gerando a lista de clientes inadimplentes ordenada por valor de dívida decrescente, permitindo priorizar os casos de maior impacto financeiro. O sistema mostra para cada cliente o total devido, quantos dias está em atraso e seus dados de contato. Isso permite que a equipe organize sua rotina de cobrança de forma eficiente, entrando em contato primeiro com os maiores devedores e utilizando estratégias diferenciadas conforme o tempo de atraso.

---

### 2.4 Relatório de Cheques Devolvidos

**Objetivo:**  
Controla e registra todos os cheques devolvidos recebidos de clientes, permitindo acompanhamento dos motivos de devolução, gestão de reapresentação e análise de risco de recebimento por cheque.

**Informações Apresentadas:**
- Dados do cheque devolvido (banco, agência, conta, número)
- Cliente emissor do cheque
- Data da devolução
- Motivo da devolução (alínea)
- Valor do cheque
- Situação atual do título
- Histórico de reapresentações
- Data de vencimento original
- Data de emissão do cheque
- Filial responsável

**Filtros Disponíveis:**
- **Tipo de Período**: 
  - Data de movimentação (devolução)
  - Data de emissão do título
  - Data de vencimento do título
- **Período**: Data inicial e final
- **Filial**: Filtro por filial específica ou grupo de filiais
- **Alínea**: Motivo específico de devolução (11, 12, 13, etc.)
- **Situação do Cheque**: Status atual (devolvido, reapresentado, protestado, etc.)
- **Cliente**: Filtro por cliente específico

**Caso de Uso Típico:**  
O supervisor de tesouraria precisa fazer o controle semanal dos cheques devolvidos para definir as ações necessárias. Filtrando pela data de movimentação da última semana, obtém a lista completa de cheques devolvidos. Analisando as alíneas (motivos), identifica quais cheques podem ser reapresentados (alíneas 11 e 12 - falta de fundos) e quais precisam de contato imediato com o cliente por motivos mais graves. Este controle é essencial para minimizar perdas e manter a saúde financeira da operação.

---

### 2.5 Juros Cobrados

**Objetivo:**  
Apresenta o detalhamento de todos os juros efetivamente cobrados de clientes em pagamentos realizados após o vencimento, permitindo análise da receita financeira proveniente de atrasos e gestão da política de juros da empresa.

**Informações Apresentadas:**
- Cliente pagador
- Título original
- Data de vencimento original
- Data de pagamento efetivo
- Dias de atraso
- Valor principal do título
- Valor dos juros cobrados
- Taxa de juros aplicada
- Valor total recebido
- Filial responsável
- Forma de recebimento
- Totalização de juros por período

**Filtros Disponíveis:**
- **Período de Recebimento**: Data inicial e final dos pagamentos com juros
- **Filial**: Filtro por filial específica ou todas
- **Cliente**: Filtro por cliente específico (opcional)
- **Valor Mínimo de Juros**: Considerar apenas recebimentos acima de determinado valor de juros
- **Tipo de Título**: Filtro por origem do título (venda, duplicata, nota promissória, etc.)

**Caso de Uso Típico:**  
O controller financeiro precisa quantificar mensalmente a receita financeira obtida através da cobrança de juros por atrasos de clientes. Gerando o relatório do mês anterior, obtém o total de juros recebidos, que será contabilizado como receita financeira. Além disso, pode analisar quais clientes pagam sistematicamente com atraso e avaliar se a taxa de juros aplicada está adequada ao mercado, auxiliando na definição da política comercial e financeira da empresa.

---

### 2.6 Histórico de Recebimento

**Objetivo:**  
Registra o histórico completo de todos os recebimentos realizados, mantendo um log detalhado de transações para auditoria, análise de padrões de recebimento e rastreabilidade total dos valores que entraram no caixa da empresa.

**Informações Apresentadas:**
- Data e hora do recebimento
- Cliente pagador
- Valor recebido
- Forma de pagamento utilizada
- Título quitado
- Usuário que registrou o recebimento
- Caixa/terminal onde foi recebido
- Descontos concedidos
- Acréscimos cobrados
- Histórico de alterações
- Dados de conciliação bancária

**Filtros Disponíveis:**
- **Período**: Data inicial e final de recebimentos
- **Filial**: Filtro por filial específica
- **Cliente**: Filtro por cliente específico
- **Forma de Pagamento**: Tipo específico de recebimento
- **Usuário**: Filtro por operador que registrou
- **Valor**: Faixa de valores
- **Status de Conciliação**: Conciliados ou pendentes

**Caso de Uso Típico:**  
A auditoria interna está investigando uma divergência de caixa em uma data específica. Utilizando o histórico de recebimentos, consegue visualizar cronologicamente todas as transações do dia, identificando exatamente qual recebimento apresentou problema, quem foi o operador responsável e em que momento a transação foi registrada. Este relatório é fundamental para garantir a transparência das operações financeiras e resolver rapidamente qualquer divergência identificada.

**Observação Importante:**  
Esta funcionalidade só é exibida no menu quando o banco de dados utilizado é Oracle, devido à necessidade de recursos específicos de auditoria e histórico disponíveis neste sistema gerenciador.

---

### 2.7 Posição Retroativa de Contas a Receber

**Objetivo:**  
Permite consultar a posição histórica das contas a receber em qualquer data passada, possibilitando análises retroativas da carteira de clientes e comparações de evolução do saldo a receber.

**Informações Apresentadas:**
- Títulos em aberto na data de referência
- Valores a vencer naquela data
- Valores já vencidos naquela data
- Clientes devedores
- Análise de aging (antiguidade) histórica
- Previsão de recebimentos que existia
- Comparativo com posição atual

**Filtros Disponíveis:**
- **Data de Referência**: Data específica no passado para análise
- **Filial**: Visualização por filial ou consolidado
- **Cliente**: Filtro por cliente específico
- **Status dos Títulos**: Em aberto, vencidos ou todos
- **Forma de Apresentação**: Analítico ou sintético
- **Tipo de Título**: Filtro por origem (venda, duplicata, etc.)

**Caso de Uso Típico:**  
O diretor financeiro precisa apresentar ao conselho a evolução da carteira de clientes nos últimos 12 meses. Gerando relatórios de posição retroativa para o dia 1º de cada mês do último ano, consegue demonstrar como variou o saldo a receber, a inadimplência e o perfil de vencimentos ao longo do tempo. Esta análise histórica é essencial para identificar tendências sazonais, avaliar a efetividade das políticas de crédito e cobrança, e planejar ações futuras baseadas em padrões identificados.

---

### 2.8 Vendas por Associação

**Objetivo:**  
Analisa as vendas realizadas para clientes pertencentes a associações, clubes ou entidades conveniadas, permitindo acompanhamento de convênios, comissões a repassar e gestão de parcerias comerciais.

**Informações Apresentadas:**
- Associação/convênio
- Vendas realizadas para associados
- Valores totais por associação
- Quantidade de transações
- Período de vendas
- Clientes associados que compraram
- Comissões ou repasses devidos à associação
- Percentuais acordados
- Filiais que realizaram vendas
- Comparativo entre associações

**Filtros Disponíveis:**
- **Período**: Data inicial e final das vendas
- **Associação**: Filtro por associação específica ou todas
- **Filial**: Filtro por filial responsável
- **Tipo de Produto/Serviço**: Categoria de produtos vendidos
- **Status**: Vendas ativas, canceladas ou todas
- **Forma de Pagamento**: Meio utilizado para pagamento

**Caso de Uso Típico:**  
O gerente comercial mantém convênios com diversas associações (sindicatos, clubes, empresas) que concedem benefícios aos seus associados. Mensalmente, precisa apurar o volume de vendas realizadas para cada convênio para calcular os repasses devidos. Gerando o relatório do mês, obtém o total de vendas por associação, podendo calcular corretamente comissões ou bonificações acordadas. Este controle também permite avaliar quais convênios são mais rentáveis e quais devem ter suas condições renegociadas.

---

## 3. TESOURARIA

### 3.1 Centro de Custo

**Objetivo:**  
Apresenta relatório de movimentações financeiras organizadas por centro de custo, permitindo análise de despesas por departamento, projeto ou área, essencial para controle orçamentário e gestão de custos.

**Informações Apresentadas:**
- Despesas por centro de custo
- Período de apuração
- Tipos de despesas (pagamentos, provisões)
- Valores realizados
- Fornecedores por centro de custo
- Origem das despesas (compras, serviços, etc.)
- Totalizações e subtotais
- Comparativos entre centros de custo
- Análise: Analítica (detalhada) ou Sintética (resumida)
  - Sintético por Centro de Custo
  - Sintético por Origem

**Filtros Disponíveis:**
- **Período**: Data inicial e final das movimentações
- **Visualização**: 
  - Por Filial individual
  - Por Grupo de Filiais
- **Filial**: Filtro por filial específica ou grupo
- **Centro de Custo**: Específico ou todos
  - *Nota: Usuários podem ter restrição para visualizar apenas centros autorizados*
- **Tipo de Relatório**: 
  - Analítico: Detalhamento completo de cada lançamento
  - Sintético por Centro de Custo: Totais por departamento
  - Sintético por Origem: Totais por tipo de despesa
- **Origem**: Filtro por tipo de despesa (compras, serviços, etc.)

**Caso de Uso Típico:**  
O gerente de cada departamento recebe mensalmente o relatório de centro de custo referente à sua área para acompanhar se está dentro do orçamento aprovado. O sistema mostra todas as despesas lançadas no centro de custo do departamento, discriminadas por fornecedor e tipo de despesa. Quando identifica gastos acima do previsto, pode tomar ações corretivas imediatamente. Já a diretoria utiliza a visão sintética consolidada para avaliar o desempenho de todos os departamentos e identificar oportunidades de otimização de custos.

---

### 3.2 Disponibilidade Financeira

**Objetivo:**  
Apresenta a posição consolidada de caixa e bancos da empresa, mostrando o saldo disponível em cada conta corrente e o total de recursos financeiros imediatamente disponíveis para uso.

**Informações Apresentadas:**
- Saldo de cada conta corrente
- Banco, agência e número da conta
- Saldo anterior (início do período)
- Movimentações de crédito (entradas)
- Movimentações de débito (saídas)
- Saldo atual disponível
- Total consolidado de disponibilidades
- Filial responsável por cada conta
- Contas com saldo negativo (descoberto)
- Limite de crédito utilizado

**Filtros Disponíveis:**
- **Período de Análise**: Data inicial para cálculo dos saldos
  - Data final para considerar movimentações
- **Filial**: 
  - Filial específica: Mostra contas de uma unidade
  - Grupo de filiais: Consolida múltiplas unidades
  - Todas: Visão corporativa completa
- **Conta Corrente**: Filtro por conta específica (opcional)
- **Mostrar Contas sem Movimento**: Incluir ou não contas sem movimentação
- **Tipo de Conta**: Conta corrente, aplicações, poupança, etc.

**Caso de Uso Típico:**  
Toda manhã, o tesoureiro acessa este relatório para verificar a posição de caixa atualizada da empresa. Com esta informação, pode planejar os pagamentos do dia, identificar necessidade de transferências entre contas ou mesmo avaliar se há excesso de caixa que pode ser aplicado. Este é um dos relatórios mais críticos para a gestão financeira diária, pois mostra exatamente quanto a empresa tem disponível para honrar seus compromissos e realizar operações.

---

### 3.3 Totais de Recebimentos e Pagamentos

**Objetivo:**  
Fornece visão consolidada do fluxo de caixa através da comparação entre valores recebidos e pagos em um período, permitindo análise de geração de caixa e planejamento financeiro.

**Informações Apresentadas:**
- Total de recebimentos do período
- Total de pagamentos do período
- Saldo líquido (recebimentos - pagamentos)
- Detalhamento por dia
- Distribuição por forma de pagamento/recebimento
- Análise por filial
- Comparativo mensal/diário
- Evolução do fluxo de caixa
- Indicadores de liquidez

**Filtros Disponíveis:**
- **Período de Análise**: Data inicial e final (obrigatório)
- **Filial**: Filtro por filial específica ou consolidado
- **Tipo de Movimentação**: 
  - Apenas recebimentos
  - Apenas pagamentos
  - Ambos (comparativo)
- **Forma de Pagamento/Recebimento**: Filtro por meio específico
- **Nível de Detalhe**: 
  - Consolidado: Apenas totais
  - Por dia: Evolução diária
  - Por categoria: Agrupado por tipo

**Caso de Uso Típico:**  
No fechamento mensal, o controller precisa elaborar o relatório de fluxo de caixa realizado para a diretoria. Utilizando este relatório com o período do mês completo, obtém o total de entradas e saídas, podendo calcular a geração de caixa operacional do período. Comparando os saldos líquidos mês a mês, identifica tendências de melhora ou piora na capacidade de geração de caixa da empresa, informação crucial para planejamento financeiro e tomada de decisões estratégicas sobre investimentos e captação de recursos.

---

## 4. INTERFACE DE CONVENIADAS

### 4.1 Relatório de Divergências

**Objetivo:**  
Identifica e apresenta divergências encontradas no processo de conciliação entre os dados de vendas da empresa e os arquivos de retorno enviados pelas empresas conveniadas (administradoras de cartões, financeiras, etc.).

**Informações Apresentadas:**
- Transações com divergência
- Tipo de divergência encontrada
- Valores informados pela empresa
- Valores informados pela conveniada
- Diferença apurada
- Data da transação
- Cliente/associado envolvido
- Filial responsável
- Identificação da conveniada
- Status da pendência
- Código ou número da transação em ambos os sistemas

**Filtros Disponíveis:**
- **Empresa Conveniada**: Administradora ou parceiro específico
- **Filial**: Filtro por filial responsável pela venda
- **Período**: Data inicial e final das transações
- **Tipo de Pendência**: 
  - Todas
  - Pendências em aberto
  - Pendências resolvidas
- **Formato de Saída**: 
  - Visualizar em tela
  - Gerar arquivo PDF
- **Caminho do Arquivo**: Local para salvar quando opção PDF selecionada

**Caso de Uso Típico:**  
A equipe de conciliação recebe semanalmente os arquivos de retorno das administradoras de cartão e conveniadas. Ao processar esses arquivos no sistema, gera o relatório de divergências para identificar transações que não conferem. Por exemplo, uma venda pode constar no sistema da loja mas não no arquivo da administradora, ou os valores podem estar diferentes. A equipe então utiliza este relatório para entrar em contato com as conveniadas, solicitar correções e garantir que todos os valores a receber sejam corretamente apurados e recebidos.

---

### 4.2 Relatório de Valores a Associar

**Objetivo:**  
Lista os valores recebidos das empresas conveniadas que ainda não foram associados aos seus respectivos títulos ou transações de venda no sistema, permitindo identificar recebimentos pendentes de vinculação.

**Informações Apresentadas:**
- Valores recebidos não associados
- Data do recebimento
- Empresa conveniada que repassou o valor
- Identificação do repasse/lote
- Valor total não associado
- Possíveis títulos para associação
- Histórico de tentativas de associação
- Motivo da não associação automática
- Filial de origem
- Prazo para regularização

**Filtros Disponíveis:**
- **Empresa Conveniada**: Administradora ou parceiro específico
- **Filial**: Filtro por filial responsável
- **Período de Recebimento**: Data inicial e final dos repasses
- **Valor**: Faixa de valores não associados
- **Status**: Pendente, em análise ou todos
- **Idade da Pendência**: Filtro por tempo sem associação

**Caso de Uso Típico:**  
A analista de conciliação identifica que há valores em aberto não associados há mais de 15 dias. Gerando este relatório, visualiza todos os recebimentos das conveniadas que não foram automaticamente vinculados aos títulos de venda. Isso pode ocorrer por diversos motivos: número de autorização diferente, valor divergente, venda cancelada após transmissão, etc. Com essas informações em mãos, faz a associação manual correta ou identifica valores que devem ser devolvidos à administradora por se referirem a vendas canceladas. Este controle é essencial para manter o contas a receber em dia e evitar diferenças não justificadas.

---

## Observações Gerais Importantes

### Condições de Exibição de Funcionalidades

Algumas funcionalidades do menu Relatórios Financeiro só são exibidas quando determinadas condições estão ativas no sistema:

1. **Análise de Despesas x Faturamento**  
   - Requer: Módulo de Orçamento de Despesas ativado (FLAUTDESP = "S")
   - Quando não atender a condição, esta opção não aparecerá no menu

2. **Histórico de Recebimento**  
   - Requer: Banco de dados Oracle
   - Em instalações que utilizam outros bancos de dados, esta opção não é exibida

3. **Menu Completo de Financeiro**  
   - O submenu inteiro só é exibido se a empresa tiver o módulo financeiro ativado
   - Configuração: Empresa.FLFINANCEIRO <> "S"

### Controle de Acesso e Segurança

- Todas as funcionalidades estão protegidas pelo Sistema Gemco de Segurança (SGS)
- Cada relatório possui uma constante SGS específica que controla o acesso do usuário
- Usuários visualizam apenas os relatórios para os quais possuem permissão
- Em alguns relatórios, há restrições adicionais por:
  - Filial: Usuário pode ver apenas dados de suas filiais autorizadas
  - Centro de Custo: Usuário pode ter acesso limitado a centros específicos (requer permissão SGS_OP_RESTRICAO_USER_ORCAM)

### Formatos de Saída

A maioria dos relatórios oferece múltiplas opções de saída:
- **Visualização em Tela**: Pré-visualização antes de imprimir
- **Impressão Direta**: Envio para impressora configurada
- **Geração de PDF**: Arquivo para arquivo ou envio por e-mail
- **Exportação para Excel**: Para análises complementares (em alguns relatórios)

### Períodos e Datas

- Campos de período geralmente têm validação de data inicial menor ou igual à data final
- Alguns relatórios utilizam a data de processamento da filial como padrão
- Relatórios contábeis oficiais (como Diário Auxiliar em modo definitivo) utilizam datas de fechamento fiscal

### Performance e Volume de Dados

- Relatórios que abrangem períodos muito extensos podem demandar mais tempo de processamento
- Recomenda-se utilizar filtros específicos (filial, fornecedor, cliente) quando possível para otimizar o desempenho
- Relatórios sintéticos são mais rápidos que analíticos para visões gerenciais

---

## Arquitetura Técnica (Resumo)

O sistema utiliza arquitetura de 3 camadas:
- **Interface**: Formulários e telas (GemcoInterface)
- **Negócio**: Regras e processamento (GemcoDllsNegócio)
- **Dados**: Acesso ao banco de dados (GemcoDllsBD)

Todos os relatórios seguem padrão consistente de:
1. Seleção de filtros pelo usuário
2. Validação de dados informados
3. Consulta aos dados no banco
4. Processamento e cálculos de negócio
5. Apresentação formatada ao usuário

---

## Suporte e Manutenção

Para dúvidas sobre funcionalidades específicas ou problemas no uso dos relatórios:
- Consulte o Help do sistema (tecla F1)
- Entre em contato com o departamento de TI da empresa
- Verifique as permissões de acesso com o administrador do sistema

---

**Documento gerado em:** 2024  
**Versão do Sistema:** VB6 - Branch DEV  
**Localização:** C:\AzureDevOps\VD-Gemco-Varejo\Implement\branches\dev\

---

*Esta documentação descreve as funcionalidades sob perspectiva de negócio, focando no uso prático e nos benefícios para os usuários. Para informações técnicas sobre implementação, consulte a documentação técnica do sistema.*
