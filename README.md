# especializacao_ux_ciencia_dados
Repositório para a resolução do trabalho final matéria de User Expirience Ciência de Dados

# Descricão do case

A área de logística extraiu dados com base no histórico de pedidos da empresa xpto, referentes ao segundo semestre de 2023. 

O time de logística quer avaliar possibilidades de se ter uma solução que possibilite identificar risco de atraso nestes pedidos a partir da base histórica. O formato de apresentação, análises e metodologias utilizadas ficam a critério do grupo.

# Dicionário de dados

- cod_pedido: Identificador único do pedido.
- cidade_destinatario: Cidade de destino do pedido.
- uf: Estado da cidade destino.
- dt_despacho_pedido: Data de saída do centro de distribuição.
- hr_despacho_pedido: Hora de saída do centro de distribuição.
- dt_entrega_pedido: Data de entrega ao destinatário.
- hr_entrega_pedido: Hora de entrega ao destinatário.
- dt_previsao_entrega_cliente: Data prometida de entrega.
- dt_criacao: Data de criação do pedido.
- dt_pagamento_pedido: Data de pagamento do pedido.
- flg_existem_ocorrencias: Indicador de ocorrências de entrega.
- tp_praca: Tipo de praça de entrega (Capital, Interior, Região Metropolitana).
- des_unidade_negocio: Classificação da unidade de negócio.
- des_cd_origem: Centro de distribuição de origem.
- qtd_dias_tat: Dias até a entrega.
- tp_performance_entrega: Status de entrega (dentro ou fora do prazo).

# 📌 Reunião Entendimento do Problema (data de 15/05/2025) 

## 1. Entendimento do Problema

- A área de logística da empresa XPTO disponibilizou uma base histórica de pedidos do **2º semestre de 2023**, com cerca de **meio milhão de registros**.
- O objetivo do case é desenvolver uma **solução que identifique riscos de atraso na entrega de pedidos**, com base em dados históricos.
- A equipe terá liberdade para propor o **formato das análises, abordagens metodológicas e apresentação dos resultados**.

## 2. Questões a Serem Respondidas

- Quais **fatores influenciam os atrasos**? (ex: cidade de destino, forma de pagamento, prazos entre etapas)
- Existe uma **relação entre a data de criação do pedido, pagamento e despacho**?
- Há **diferença no desempenho logístico** entre capitais, interiores e regiões metropolitanas?
- O tipo de **praça** impacta a taxa de atraso?
- Quais cidades, centros de distribuição ou **transportadoras** apresentam **maior recorrência de atraso**?
- A sazonalidade (**datas festivas**) impacta o cumprimento de prazos?

## 3. Abordagens Iniciais

- **Análise exploratória (EDA)** será a primeira etapa: verificação de dados ausentes, estatísticas descritivas e visualizações para entender o comportamento das variáveis.
- A variável `tp_performance_entrega` será usada como **indicador principal de atraso**.
- A hipótese inicial é que o prazo de entrega deve ser considerado **a partir da data de pagamento**.
- Serão avaliadas **relações entre variáveis**, como despacho x pagamento, origem x destino, e a existência de ocorrências.
- Análises de correlação e regressão (simples e múltipla) serão consideradas para **identificar padrões**.

## 4. Divisão Inicial das Tarefas (Equipe de 4 pessoas)

- **Pessoa 1 (Rafael)**: Análise exploratória inicial (carregamento da base, verificação de campos, análises básicas de distribuição).
- **Pessoa 2 (Leandra)**: Revisar conteúdo das aulas de estatística para aplicar métodos de correlação entre variáveis e propor variáveis derivadas.
- **Pessoa 3** (a definir): **A DEFINIR**.
- **Pessoa 4** (a definir): **A DEFINIR**.

---

## ❓ Perguntas Críticas para Refinamento

1. **Há interesse da área solicitante em entender apenas o risco (classificação)** ou também o **motivo do atraso** (ex: análise causal)?

2. **Existe algum critério de recorte geográfico ou por tipo de praça que a empresa gostaria de ver detalhado?**

3. **A expectativa da área solicitante inclui apenas uma análise exploratória dos motivos de atraso ou também a entrega de um modelo de classificação preditivo para identificar o risco de atraso?**
    - Atenção com a questão das séries temporais.
