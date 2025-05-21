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

1. **A expectativa da área solicitante inclui apenas uma análise exploratória dos motivos de atraso ou também a entrega de um modelo de classificação preditivo para identificar o risco de atraso?**
    - Atenção com a questão das séries temporais.
      - Para a criação de um modelo de classificação devemos considerar a série temporal?
    - É interessante avaliar a relação entre uma variável preditora com o target (atraso)?
      - Método da máxima verossimilhança. 
      - Teste de Hosmer & Lemeshow.
      - Qui-Quadrada

2. **Sugestão de divisão de tarefas:**
   - Análise Exploratório
   - Confecção Apresentação
   - Criação Modelo de Classificação
   - Outras sugestões?
   - Cada atividade deve ser feita pelas 4 pessoas? Sugestões de divisão?

# 📌 Resumo da 2ª Reunião – Case XPTO – Identificação de Risco de Atrasos em Pedidos

## 1. Entendimento do Problema (Refinado)

- Reforço do objetivo principal: **identificar fatores que influenciam o atraso nas entregas**.
- Discussão sobre **possibilidade de criar modelo de classificação** (atrasado ou não) ou apenas **solução exploratória com insights relevantes**.
- Debate sobre **ponto inicial da contagem de prazo de entrega**: data de pagamento x data de despacho.

## 2. Dicas e Direcionamentos do Professor

- **O case é aberto**, e o importante é **justificar a escolha metodológica** da solução proposta.
- A solução pode ser:
  - Um **modelo preditivo** (classificação ou regressão).
  - Uma **análise descritiva bem estruturada com sugestões de ações**.
  - Um **dashboard interativo que oriente decisões**.
- A entrega precisa **convencer o cliente de que resolve o problema**, mesmo que não envolva modelos.
- Incentivou o grupo a **trazer sugestões de uso real da solução**, como:
  - Monitoramento semanal/mensal.
  - Gatilhos de decisão a partir de determinadas métricas (ex: “probabilidade de atraso > 70% aciona área X”).
- Reforçou a importância de **documentar tecnicamente** o que foi feito (Jupyter, scripts, planilhas, etc).

## 3. Questões Técnicas Discutidas

- Avaliação de **testes de hipótese** como método para embasar decisões (ex: teste qui-quadrado, Mann-Whitney).
- Discussão sobre **modelagem com dados temporais**:
  - Se o grupo optar por séries temporais (ex: ARIMA), precisa garantir ordenação e consistência nos dados.
  - Alternativa: transformar datas em variáveis derivadas como diferença entre datas (ex: dias até entrega).
- Retomada de conceitos aprendidos com a professora Rita (teste de hipóteses, regressão logística).

## 4. Abordagens e Divisão de Tarefas (Atualização)

- **Rafael**: Tratamento dos dados e Análise Exploratória Inicial (EDA).
- **Leandra**: Formulação de perguntas analíticas e suporte nos testes estatísticos.
- **Vanessa**: Responsável pelo BIA e apoio na organização do material de apresentação.
- **Fernando**: Responsável por construir o **modelo de classificação**, possivelmente com regressão logística ou árvore de decisão.

## 5. Alinhamentos e Ações Definidas

- Rafael entregará EDA inicial até domingo à noite.
- Grupo discutirá melhores formas de apresentação e estrutura da entrega.
- Vanessa reforçou que um **bom EDA pode, por si só, entregar muito valor**.
- Leandra e Rafael reforçaram a importância de buscar insights sobre região, forma de pagamento e sazonalidade.
- Foi sugerida a **inspiração em projetos anteriores** (ex: modelo Honda para previsão com dados de data e hora).

## 6. Considerações Finais
- A professora orientou que o **modelo é a “cereja do bolo”** — o mais importante é **mostrar que a solução proposta pode ser útil na prática**.
- A documentação de tudo o que foi feito é obrigatória (scripts, apresentações, outputs).

