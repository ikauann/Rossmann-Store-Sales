
# Rossmann Store 

# 1. Entendendo o Problema de Negócio

## 1.1. Contexto
O CFO da empresa conduziu uma reunião com os Gerentes de Loja, solicitando uma previsão diária das vendas para as próximas 6 semanas. Após esta reunião, os Gerentes solicitaram uma previsão de vendas para suas respectivas lojas.

O problema apresentado pode ser caracterizado como um problema de aprendizado supervisionado, mais especificamente uma regressão envolvendo Time-Series.

## 1.2. Planejamento da Solução
Utilizei a metodologia CRISP-DM para desenvolver este projeto, que orienta uma série de passos para a exploração de dados, rápida entrega de valor e identificação precoce de obstáculos.

Defini o formato da solução, criei uma lista de passos e identifiquei os meios de coleta de dados.

# 2. Dicionário dos Dados

## Dados Brutos
Veja abaixo o dicionário dos dados brutos:

| Variável                 | Descrição                                                                                         |
|--------------------------|---------------------------------------------------------------------------------------------------|
| Id                       | Identificador para cada loja e data no conjunto de teste                                          |
| Store                    | Identificador único para cada loja                                                               |
| DayOfWeek                | Dia da semana da venda                                                                            |
| Date                     | Data da venda (diariamente)                                                                       |
| Sales                    | Volume de vendas para um determinado dia (variável a ser prevista)                                |
| Customers                | Número de clientes em um determinado dia                                                          |
| Open                     | Indicador se a loja estava aberta: 0 = fechada, 1 = aberta                                        |
| Promo                    | Indica se a loja estava com promoção no dia                                                      |
| StateHoliday             | Indica feriado estadual. Normalmente, todas as lojas estão fechadas nos feriados estaduais.       |
|                          | a = feriado estadual, b = feriado de Páscoa, c = Natal, 0 = Nenhum                                |
| SchoolHoliday            | Indica se a loja foi afetada pelo fechamento das escolas públicas                                 |
| StoreType                | Diferencia entre 4 modelos de loja diferentes: a, b, c, d                                         |
| Assortment               | Descreve o nível de variedade: a = básico, b = extra, c = estendido                                |
| CompetitionDistance      | Distância em metros para a loja concorrente mais próxima                                          |
| CompetitionOpenSinceMonth| Mês aproximado de abertura do concorrente mais próximo                                             |
| CompetitionOpenSinceYear | Ano aproximado de abertura do concorrente mais próximo                                             |
| Promo2                   | Promoção contínua e consecutiva para algumas lojas: 0 = loja não está participando, 1 = está     |
| Promo2SinceWeek          | Semana do calendário em que a loja começou a participar da Promo2                                  |
| Promo2SinceYear          | Ano em que a loja começou a participar da Promo2                                                   |
| PromoInterval            | Descreve os intervalos consecutivos em que a Promo2 é iniciada, nomeando os meses de início da    |
|                          | promoção.                                                                                         |

## Novas Features Criadas (Feature Engineering)
- year, month, day, week_of_year: informações extraídas da coluna Date.
- competition_since: ano e mês extraídos das colunas CompetitionOpenSinceYear e CompetitionOpenSinceMonth.
- competition_time_month: quantidade de meses que a loja competidora está aberta.
- promo_since: ano e semana de início da promoção.
- promo_time_week: quantidade de semanas em que a loja está em promoção.
- is_promo: indicação se a loja está em promoção.

# 3. Principais Insights
Aqui estão os principais insights obtidos durante a Análise Exploratória dos Dados:

H1) Lojas com maior variedade de produtos tendem a vender mais.
H2) Não há uma correlação significativa entre a proximidade dos competidores e o volume de vendas.
H3) Lojas com competidores por mais tempo tendem a vender menos.
H4) Lojas com promoções ativas por mais tempo tendem a vender mais.

# 4. Performance dos Algoritmos de Machine Learning
Testamos quatro algoritmos para resolver o problema de regressão. Aqui estão os resultados:

| Modelo                     | MAE     | MAPE   | RMSE    |
|----------------------------|---------|--------|---------|
| Average Model              | 1354.80 | 0.45   | 1835.13 |
| Linear Regression          | 2032.90 | 0.30   | 2885.37 |
| Lasso Regression           | 2388.68 | 0.34   | 3369.37 |
| Random Forest Regression   | 822.48  | 0.11   | 1228.25 |
| XGBoost Regression         | 987.44  | 0.14   | 1417.54 |

Optamos por utilizar o XGBoost devido à sua eficiência na geração de modelos mais compactos.

# 5. Resultado de Negócio
Com o modelo XGBoost finalizado, podemos comparar as vendas previstas com os valores reais e com o modelo de Baseline (média):

| Modelo         | Vendas Previstas  | Pior Cenário      | Melhor Cenário     |
|----------------|-------------------|-------------------|--------------------|
| Vendas Reais   | $289.571.750,00   | $289.571.750,00   | $289.571.750,00    |
| Baseline       | $324.608.344,00   | $324.608.344,00   | $324.608.344,00    |
| Minha Solução  | $286.828.352,00   | $285.804.949,65   | $287.516.602,94    |

Este modelo proporciona uma previsão mais precisa, permitindo uma tomada de decisão mais acertada para o CEO da empresa.


## Documentation

[Kaggle](https://www.kaggle.com/c/rossmann-store-sales)


## Authors

- [@ikauann](https://www.linkedin.com/in/kauan-souza-913518213/)


