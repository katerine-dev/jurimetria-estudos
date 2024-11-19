# Regressão

Histórico

A regressão foi introduzida por Sir Francis Galton no final do século XIX enquanto estudava a hereditariedade, ele percebeu que os filhos apresentavam as mesmas características dos seus pais, porém em uma intensidade menor, por exemplo: alturas dos descendentes tendiam a "regredir" para a média da população, o que levou ao termo "regressão".
Os algoritmos de regressão são importantes para extração de informação de dados, bastante utilizada quando se deseja prever valores a partir de uma ou mais variáveis explicativas.
A regressão, em termos gerais, refere-se a qualquer método que tenta modelar e compreender a relação entre uma variável dependente (ou resposta) e uma ou mais variáveis independentes (ou preditoras). Pode ser linear ou não-linear, paramétrica ou não-paramétrica, etc.

![Tópicos](/docs/topicos.png)[^imagem_1].

## Principais técnicas de algoritmos de regressão:

Existem várias técnicas de regressão, como regressão linear, regressão logística, regressão polinomial, regressão de Ridge, Lasso, Elastic Net, e regressão de árvore (incluindo Random Forest), cada uma com suas próprias aplicações e vantagens. Iremos comentar sobre algumas das principais técnicas abaixo:

### Regressão Linear:

Regressão linear é uma técnica que assume que a relação entre a variável dependente e as variáveis independentes é linear. Sendo também um tipo de algoritmo supervisionado, portanto, antes de entender como funciona o algoritmo é importante conhecer o que seria aprendizado supervisionado.

1. Regressão linear Simples: temos somente uma variável independente (X) para fazermos a predição. Consiste em achar uma reta que relacione duas variáveis quantitativas.

![Regressão Simples](/docs/regressao-simples.png)

Veja a seguir um exemplo gráfico de um modelo de uma regressão linear simples (quando temos duas variáveis e a relação entre elas pode ser representada por uma linha reta):

![Gráfico regressão linear simples](/docs/grafico-simples.png)[^imagem_2].

Podemos analisar o resultado da regressão avaliando os valores reais e os valores preditos através da reta de regressão.

2. Regressão Linear Múltipla: várias variáveis independentes (X) usadas para fazer a predição (envolve três ou mais variáveis). Essa abordagem mais abrangente permite modelar relações mais complexas entre as variáveis, capturando o efeito combinado e interativo de múltiplos fatores na variável dependente.

Na Regressão Linear Múltipla, a fórmula é bem parecida, só vamos acrescentar outras variáveis preditoras:

![Fórmula Regressão Linear Múltipla](/docs/formula-regressao-multipla.png)

Na fórmula acima temos duas variáveis preditoras e seus betas. Dando continuidade a este modelo, podemos ter quantas variáveis preditoras quanto quisermos:

![Fórmula Regressão Linear Múltipla - Multiplas variáveis](/docs/formula-regressao-multipla-2.png)

Na figura abaixo conseguimos comparar o algoritmo da regressão linear Simples para Regressão Linear Múltipla:

![Comparação entre Regressão Linear Simples e Múltipla](/docs/comparacao-multipla-simples.png)[^imagem_3].

## Regressão com Random Forest

Consiste em uma técnica de aprendizado de máquina que utiliza a construção de múltiplas árvores de decisão (Geralmente treinados com o método de Bagging)[^comentario_1]. para modelar e prever uma variável contínua. A ideia principal do método é criar combinações de modelos que aumentem o resultado do sinal. Um dos principais benefícios de se trabalhar com esse algoritmo é a possibilidade de se trabalhar com um grande conjunto de dados de maior dimensão.

![Random Forest Simplified](/docs/random-forest-simplified.png)[^imagem_4].

O Random Forest é um modelo versátil, semelhante às árvores de decisão, adequado tanto para tarefas de classificação quanto de regressão. Ele possui viés e variância reduzidos, resultando em melhores e mais consistentes resultados, além de oferecer robustez ao modelo. 

## Regressão com XGBoost

O “Extreme Gradient Boosting” (XGBoost) , é uma técnica avançada de aprendizado de máquina baseada em árvores de decisão que utiliza a estrutura de Gradient boosting[^comentario_2]. Ele combina técnicas de otimização do uso do software e hardware, como, por exemplo, técnicas que ajudam a evitar *overfitting* (ajuste excessivo)  e produz resultados superiores usando menos recursos de computação.

![Regressão com XGBoost](/docs/regressao-xgboost.png)[^imagem_5].

### Descrição do funcionamento do algoritmo:

Como comentamos acima, a regressão é um conjunto de métodos estatísticos que permitem prever ou estimar um valor dependente (variável dependente) com base em um ou mais valores independentes (variáveis independentes). O objetivo principal é encontrar a relação entre as variáveis, geralmente expressa por uma função matemática.

Base de dados: Recolher dados históricos que contenham variáveis de interesse. A análise de dados pode ser feita por ferramentas estatísticas que possibilitam correlacionar de diversas maneiras as variáveis envolvidas.
	
Análise Exploratória: Analisar os dados para entender as relações e identificar padrões.

Modelagem: Escolher o tipo de regressão apropriado (linear, múltipla, radom forest, etc.) e ajustar o modelo aos dados. Isso envolve a determinação dos coeficientes que minimizam a diferença entre os valores observados e os valores previstos.

Previsão: Usar o modelo para prever valores futuros ou desconhecidos da variável dependente com base nos valores das variáveis independentes.


### Características:

Além das características de comentamos, podemos concluir que regressão são modelos que visam predizer o comportamento de uma variável dependente (Y) com uma função de uma ou mais variáveis independentes (X) e que existem diferentes tipos de técnicas de regressão, cada uma adequada a diferentes tipos de dados e relações entre variáveis.

- Previsão e estimativa: modelos de regressão são usados para prever valores futuros ou desconhecidos da variável dependente com base em variáveis independentes conhecidas.
- Coeficientes: os coeficientes estimados representam a magnitude e a direção do impacto das variáveis independentes sobre a variável dependente.
- Avaliação do Modelo:  a qualidade do ajuste do modelo é frequentemente avaliada por métricas como o coeficiente de determinação (R²), erro quadrático médio (MSE), erro absoluto médio (MAE) e outros.
- Resíduos: Os resíduos (diferença entre os valores observados e os valores previstos) são analisados para verificar a adequação do modelo e a conformidade com as suposições de regressão.

As suposições de regressão linear incluem a existência de uma relação linear entre variáveis independentes e dependentes, a ausência de outliers[^comentario_3], e a distribuição normal dos termos de erro, homocedasticidade[^comentario_4], independência dos erros e multicolinearidade[^comentario_5].


### Áreas de aplicação:

Os modelos de regressão são ferramentas poderosas e flexíveis para análise preditiva e descritiva, permitindo a compreensão e previsão de relações complexas entre variáveis. 

Esse algoritmo pode ser utilizado em qualquer problema, onde as variáveis de entrada e saída são valores contínuos, como, por exemplo:

- Economia: Previsão de tendências de mercado, análise de investimentos, modelagem de crescimento econômico, analisar a relação entre variáveis macroeconômicas, como taxa de juros, inflação e investimento.
- Ciências Sociais: Estudos de relações sociais, previsão de comportamentos humanos.
- Saúde: Modelagem de risco, análise de sobrevivência, predição de resultados de tratamentos, análise de eficácia de tratamentos, na relação entre fatores de risco e doenças, ou na previsão de resultados médicos com base em múltiplas variáveis. 
- Marketing: Previsão de vendas, análise de comportamento do consumidor, otimização de campanhas publicitárias.
- Engenharia: Modelagem de falhas, previsão de desempenho de sistemas.
- Ciências Ambientais: Previsão de mudanças climáticas, modelagem de poluição, análise de recursos naturais.
- Finanças: Precificação de ativos, análise de risco, previsão de retornos financeiros.
- Direito:
    - Análise preditiva de decisões judiciais com base em características dos casos.
    - Modelagem da probabilidade de sucesso de ações judiciais.
    - Identificação de padrões em decisões judiciais para otimizar estratégias processuais.
    - Previsão de tempos de tramitação de processos judiciais.
    - Análise de impacto de mudanças legislativas ou normativas sobre o comportamento das partes ou das decisões dos tribunais.
    - Estudo de correlações entre variáveis jurídicas, como o perfil das partes e os resultados das decisões, para compreensão de tendências e possíveis desigualdades no sistema jurídico.

## Referências:

[^imagem_1]: Fonte: OLIVEIRA, A.; ARAUJO, C.; JANAILDA, I. Análise de Regressão Tópicos em Avaliação de Desempenho de Sistemas. [s.l: s.n.]. Disponível em:
<https://www.modcs.org/wp-content/uploads/2015/12/Analise%20de%20Regressao.pdf>.

[^imagem_2]: Fonte: FAGNA, M. 6 Machine Learning - Regressão | Tutorial Shiny com Machine Learning usando Tidymodels (em desenvolvimento). Disponível em:
<https://bookdown.org/fagna/_machine_learning_shiny_tutorial/machine-learning---regress%C3%A3ohtml#regress%C3%A3o-linear>. Acesso em: 20 maio. 2024.

[^imagem_3]: Fonte: GORI, E. Regressão Linear Múltipla Ementa: • Definição; • Estimadores Mínimos de Mínimos Ordinários; • Teorema de Gauss-Markov. [s.l: s.n.]. Disponível em:
<https://www4.eco.unicamp.br/docentes/gori/images/arquivos/EconometriaIEconometria_RegressaoMultipla.pdf>.

[^comentario_1]: "A técnica de bootstrap que vimos anteriormente pode ser extremamente útil para o cálculo de desvio-padrão em situações onde isso pode não ser possível. Já aqui, vamos ver o emprego dessa técnica com o intuito de aumentar a performance de métodos de aprendizado como as árvores de decisão." FILHO, L. H. B. Bagging, Random Forests e Boosting. Disponível em:
<https://analisemacro.com.br/economia/macroeconometria/bagging-random-forests-e-boosting/>. Acesso em: 20 maio. 2024.

[^imagem_4]: Fonte: ESTATSITE.COM.BR. Disponível em:
<https://estatsite.com.br/>. Acesso em: 20 maio. 2024.

[^comentario_2]: "O gradient boosting é uma técnica de aprendizado de máquina para problemas de regressão e classificação, que produz um modelo de previsão na forma de um ensemble de modelos de previsão fracos, geralmente árvores de decisão. Ela constrói o modelo em etapas, como outros métodos de boosting, e os generaliza, permitindo a otimização de uma função de perda diferenciável arbitrária." Gradient boosting. Disponível em:
<https://pt.wikipedia.org/wiki/Gradient_boosting>. Acesso em: 20 maio. 2024.

[^imagem_5]: Fonte: FAGNA, M. 6 Machine Learning - Regressão | Tutorial Shiny com Machine Learning usando Tidymodels (em desenvolvimento). Disponível em:
<https://bookdown.org/fagna/_machine_learning_shiny_tutorial/machine-learning---regress%C3%A3o.html#regress%C3%A3o-linear>. Acesso em: 20 maio. 2024.

[^comentario_3]: "Os outliers são dados que se diferenciam drasticamente de todos os outros. Em outras palavras, um outlier é um valor que foge da normalidade e que pode (e provavelmente irá) causar anomalias nos resultados obtidos por meio de algoritmos e sistemas de análise." ANALYTICS, A. A. Outliers, o que são e como tratá-los em uma análise de dados? Disponível em:
<https://aquare.la/o-que-sao-outliers-e-como-trata-los-em-uma-analise-de-dados/>.

[^comentario_4]: "Homocedasticidade refere-se à variância constante dos resíduos." HOMOCEDASTICIDADE NA ANÁLISE DE REGRESSÃO EM AVALIAÇÕES IMOBILIÁRIAS: A IMPORTÂNCIA DA VARIÂNCIA CONSTANTE DOS RESÍDUOS – Escola do Avaliador – Cursos e Treinamentos de Avaliação de Imóveis. Disponível em: <https://escoladoavaliador.com.br/2024/02/01/homocedasticidade-na-analise-de-regressao-em-avaliacoes-imobiliarias-a-importancia-da-variancia-constante-dos-residuos/#:~:text=Import%C3%A2ncia%20da%20Vari%C3%A2ncia%20Constante%3A%20Homocedasticidade>. Acesso em: 20 maio. 2024.

[^comentario_5]: "Multicolinearidade consiste em um problema comum em regressões, no qual as variáveis independentes possuem relações lineares exatas ou aproximadamente exatas." Multicolinearidade. Disponível em: <https://pt.wikipedia.org/wiki/Multicolinearidade>.
