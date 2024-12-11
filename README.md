# Classificação de obesidade utilizando RandomForest

Projeto acadêmico desenvolvido como parte do curso de Ciência da Computação na UNISOCIESC, com foco em análise preditiva utilizando aprendizado de máquina para identificar e classificar níveis de obesidade em indivíduos.

Autor: Henrique Correia de Sales

O objetivo principal do projeto é analisar os dados de saúde e hábitos alimentares de indivíduos para classificar seus níveis de obesidade, auxiliando na identificação precoce de riscos relacionados ao peso.

Os níveis de obesidade previstos são:
- Peso Insuficiente
- Peso Normal
- Sobrepeso Grau I
- Sobrepeso Grau II
- Obesidade Tipo I
- Obesidade Tipo II
- Obesidade Tipo III

O modelo de aprendizado de máquina escolhido foi o Random Forest, devido à sua robustez e capacidade de lidar com dados complexos.

# Conjunto de Dados

Origem
O conjunto de dados utilizado foi extraído do [Kaggle](https://www.kaggle.com/datasets/ankurbajaj9/obesity-levels) e é composto por 18 atributos, incluindo hábitos alimentares, nível de atividade física e outros fatores de saúde.
77% dos dados foram gerados sinteticamente usando a ferramenta Weka e o filtro SMOTE, enquanto 23% foram coletados diretamente de usuários por meio de uma plataforma web. Mais informações podem ser encontradas no artigo "[Software de Estimativa de Nível de Obesidade baseado em Árvores de Decisão](https://www.sciencedirect.com/science/article/pii/S2352340919306985)".

# Análise Inicial
Estatísticas Descritivas
Foi realizada uma análise descritiva dos dados, incluindo inspeção das primeiras linhas, informações gerais e estatísticas básicas.

Análise das Variáveis Categóricas
Foram avaliadas as distribuições das variáveis categóricas em relação ao nível de obesidade.

Análise de Correlação
Uma matriz de correlação foi gerada para identificar relações entre as variáveis do conjunto de dados.

# Resolução do Problema

Pré-processamento
Limpeza dos Dados: Remoção de colunas irrelevantes (e.g., ID).

Transformação de Variáveis Categóricas:
One-hot encoding em colunas binárias como Gender e family_history_with_overweight.

Label encoding para colunas categóricas restantes como CAEC, CALC e MTRANS.
Tratamento de Outliers: Utilização da regra do IQR (Interquartile Range) para identificação e remoção.

Divisão dos Dados: Separação em conjuntos de treino e teste.

Treinamento Inicial
O modelo Random Forest foi treinado inicialmente, alcançando uma acurácia de 89,76%.

# Otimização e Avaliação do Agente Inteligente

Ajuste de Hiperparâmetros
Utilizou-se a técnica RandomizedSearchCV para ajustar os hiperparâmetros do modelo Random Forest. Configurações importantes:
- n_iter=30: 30 combinações aleatórias testadas.
- cv=3: Validação cruzada com 3 divisões.
- scoring='accuracy': Métrica de avaliação baseada em acurácia.
- random_state=42: Reprodutibilidade dos resultados.

# Resultados Após Ajuste

Acurácia final: 96,24%

Comparação com Outros Modelos
Árvore de Decisão: Acurácia de 94,29%
KNN: Acurácia de 91,44%

# Resultados Obtidos
Alta Acurácia: O modelo final Random Forest obteve 96,24% de acurácia.

# Desempenho por Classe:
Excelente em classes como Obesity Type III (precisão e recall de 1.00).
Desempenho moderado em classes como Overweight Level I e Normal Weight.

# Limitações e Possíveis Melhorias Futuras

Limitações
Desequilíbrio de Classes: Algumas classes possuem menos exemplos, impactando o desempenho do modelo.
Dados Sintéticos: O uso de dados gerados pode não refletir perfeitamente a variabilidade do mundo real.
Interpretação Limitada: Faltam explicações detalhadas sobre as características que influenciam as decisões do modelo.

# Melhorias Futuras
Testar algoritmos avançados como XGBoost, LightGBM e CatBoost.
Implementar um sistema de monitoramento contínuo para ajustar o modelo conforme novos dados chegam.
Melhorar a análise das classes com baixo desempenho, ajustando pesos ou utilizando técnicas de amostragem.

# Conclusão

O projeto demonstrou a eficácia de técnicas de aprendizado de máquina para prever níveis de obesidade. O modelo Random Forest apresentou resultados sólidos, destacando-se pelo processo robusto de pré-processamento e treinamento.
Embora já mostre bom desempenho, há espaço para melhorias que podem tornar o agente ainda mais eficaz e generalizável.
