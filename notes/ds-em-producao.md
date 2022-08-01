# Analise Descritvas dos Dados

----

Antes de começar a trabalhar nos dados é bom de inicio começarmos com a Analise Descritivas dos Dados. Com ela conseguimos ter uma visão geral dos dados.

Saber o valor maximo ou minimo, a media, mediana e o desvio-padrão, a kurtosis e a skew pode nos dar um viés para qual caminho seguir com os dados.

# Feature Engineering

---

Deveriar variaveis pode ser importante para quase todo tipo de fenomeno que você estiver modelando. Ela ajuda tanto em Analise Exploratoria de Dados quanto em aumento de acuracia, porém, é preciso ter cuidado quanto a isso. Em relação a modelo, quantos mais features você derivar mais o modelo tende a um viés.

**Como fazer o mapa?**

Existe sites para criar e você pode jogar no seu notebook.

# Analise Exploratoria de Dados

---

Analise Exploratoria de Dados pode ser feita em 3 maneiras: Univariada, Bivariada e Multivarida. Univariada é analisar apenas o impacto da variavel resposta, Bivariada é analisar a varaivel resposta junto com outra variavel do dataset e Multivariada é analisar a varaivel resposta junto com duas ou mais variaveis do dataset. Fazer isso nos da uma noção do impacto da nossa variavel respostas além de quebrar certas crenças sobre tal fenomeno.

Falando sobre modelos, quando seu modelo não performar bem é possivel descobrir essa causa usando a Analise Exploratoria de Dados. 

- Ganhar experiência de negócio.

- Validar Hipóteses de negócio. (Insights)

- Perceber variaveis importantes para o Modelo.

# Preparação dos Dados

---

Em machine learning, o peso de cada variavel importa e os modelos vê apenas a variação dos dados (range). Alguns modelos baseados em Otimizadores e Distância (NN, SVM, K-NN...) são afetados por diferentes escalas. E modelos baseados em arvores (RF, ET, XGB, LGBM, ...) não são afetados por diferentes escalas, porém, por ser considerada uma boa pratica mesmo que não vá usar os modelos afetados, é bom realizar a preparação.

Tipos de preparação dos dados:

- Normalização:
  
  Rescala o centro da Distribuição dos Dados para a média 0 com o desvio padrão igual a 1.

- Rescaling:
  
  Rescala o Intervalo dos dados entre 0 e 1

- Encoding:
  
  Transformar variaveis categoricas para númericas sem perder o valor que essa variavel trás.

- Transformação:
  
  Transformar a distruição em uma distruição normal.

> Ao fazer rescaling você tras os dados para uma escala de 0 a 1 mas sem perder a Distribuição original.

Tecnica para Normalização de Dados:

$$
\mathrm{X}_{1}^{new} = \frac {\mathrm{X}_{i}^{old} - \mu} {\sigma}
$$



$$
\sigma = \text{desvio-padrão} \\
\mu = \text{média}
$$



Tecnica para Rescaling dos Dados:

$$
\mathrm{X}_{i}^{new} = \frac{\mathrm{X}_{i}^{old} - {X \small min\ }}{X \small max\ - X \small min\ }
$$



Essa tecnica é chamada de MinMaxScaler. Obs: Para variaveis que não tenha uma Distruição normal é melhor aplicar o MinMaxScaler, ele usa a tecnica dos quartis para evitar Outiliers.



Tecnicas para Encoding:

- One-Hot Encoding

- Target Encoding

- Binary Encoding

- Ordinal Encoding
  
  
  
  
  
  [Category Encoders &mdash; Category Encoders 2.5.0 documentation](https://contrib.scikit-learn.org/category_encoders/)



Tecnicas para Transformações:

- Logarithm Transformation

- Box-Cox Transformation,

- Cube-Root Transformation

- Squere-Root Transformation

- Sine and Cosine Transformation)











Como sabemos, os modelos de machine learning precisam fazer calculos e ter uma variavel categorica não é possivel realizar os calculos. Com isso, temos tecnicas para transformar variaveis categoricas para númerica para assim nosso modelo realizar os calculos. As tecnicas mais famosas são:

- 


