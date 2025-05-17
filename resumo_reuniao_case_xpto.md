
# 📌 Resumo Inicial da Reunião – Case XPTO – Identificação de Risco de Atrasos em Pedidos

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
