# Prática de análise de dados com Python

Para exemplificar o funcionamento do algoritmo iremos focar técnica de regressão linear simples em Python. Portanto, para implementação é necessário:
- Utilizar as bibliotecas como: numpy, matplotlib e pandas em Python e o método dos mínimos quadrados. 
- Base de dados (csv ou xlsx, por exemplo)

Em uma pesquisa existem alguns passos importantes:

## Tratamento de dados (Faxina de dados):
O tratamento de dados é uma das etapas mais cruciais em projetos de ciência de dados. A qualidade dos dados impacta diretamente a confiabilidade, precisão e utilidade das análises realizadas. Abaixo estão as principais razões pelas quais o tratamento de dados é essencial:

Qualidade e Confiabilidade dos Resultados:

- Dados Brutos Contêm Erros: Dados coletados frequentemente apresentam inconsistências, como valores ausentes, duplicados, ou informações irrelevantes. Sem tratamento, esses problemas podem comprometer os resultados.
- Impacto na Precisão: Modelos de aprendizado de máquina e análises estatísticas são sensíveis a dados ruidosos ou incorretos. Um bom tratamento garante que as conclusões sejam confiáveis.

Redução de Viés e Prevenção de Distorções:

- Normalização e Padronização: Dados provenientes de diferentes fontes podem ter formatos distintos. Exemplo: datas em diferentes sistemas (DD/MM/AAAA vs. MM/DD/AAAA). A padronização garante que os dados sejam interpretados corretamente.
- Remoção de Outliers: Valores extremos podem distorcer medidas estatísticas, como média ou desvio padrão. O tratamento analisa se esses outliers devem ser excluídos, corrigidos ou destacados.

Preparação para Modelagem

- Transformação de Dados: Variáveis categóricas frequentemente precisam ser convertidas para números (ex.: one-hot encoding). Dados não escalados podem prejudicar modelos baseados em distância, como SVM ou KNN, tornando necessário escaloná-los.
- Criação de Variáveis Derivadas: Dados tratados podem ser usados para criar novas variáveis, aumentando a capacidade preditiva do modelo.

Melhor Uso de Recursos Computacionais:

- Eliminação de Redundância: Reduz o volume de dados processados, diminuindo o custo computacional.
- Foco em Informações Relevantes: Remove informações desnecessárias, permitindo análises mais eficientes.

Conformidade Legal e Ética

- Proteção de Dados Sensíveis: Garante que informações pessoais sejam anonimizadas ou tratadas de acordo com regulamentações, como a LGPD (Lei Geral de Proteção de Dados) ou GDPR (General Data Protection Regulation).
- Redução de Riscos Éticos: Dados mal tratados podem levar a decisões enviesadas, afetando grupos específicos de forma injusta.

Melhoria da Interpretação e Comunicação

- Facilita a Visualização: Dados tratados são mais fáceis de visualizar e interpretar por equipes técnicas e não técnicas.
- Apoia a Tomada de Decisão: Resultados claros e bem fundamentados ajudam gestores a tomarem decisões baseadas em evidências.

#### Exemplo em Python:

```python
# TRATAMENTO DOS DADOS
# Função para renomear as colunas
def rename_columns(col):
    return col.strip().replace(' ', '_').lower()


# Existem celulas em branco, iremos preencher essas celulas em brancos com NaN 
def tratamento_dados(df):
    # Aplicar a função em todos os nomes das colunas
    df.columns = [rename_columns(col) for col in df.columns]
    print(df.columns) 

    df = df.replace(" ", np.NaN)

    df['life_expectancy'] = df['life_expectancy'].fillna(df['life_expectancy'].mean())
    df['adult_mortality'] = df['adult_mortality'].fillna(df['adult_mortality'].mean())
    df['alcohol'] = df['alcohol'].fillna(df['alcohol'].mean())
    df['hepatitis_b'] = df['hepatitis_b'].fillna(df['hepatitis_b'].mean())
    df['bmi'] = df['bmi'].fillna(df['bmi'].mean())
    df['polio'] = df['polio'].fillna(df['polio'].mean())
    df['total_expenditure'] = df['total_expenditure'].fillna(df['total_expenditure'].mean())
    df['diphtheria'] = df['diphtheria'].fillna(df['diphtheria'].mean())
    df['gdp'] = df['gdp'].fillna(df['gdp'].mean())
    df['population'] = df['population'].fillna(df['population'].mean())
    df['thinness__1-19_years'] = df['thinness__1-19_years'].fillna(df['thinness__1-19_years'].mean())
    df['thinness_5-9_years'] = df['thinness_5-9_years'].fillna(df['thinness_5-9_years'].mean())
    df['income_composition_of_resources'] = df['income_composition_of_resources'].fillna(df['income_composition_of_resources'].mean())
    df['schooling'] = df['schooling'].fillna(df['schooling'].mean())

    # Criar uma instância de LabelEncoder
    label_encoder = LabelEncoder()

    df['country'] = label_encoder.fit_transform(df['country']).astype(int) # transformação de string em int
    df['status'] = label_encoder.fit_transform(df['status']).astype(int) # transformação de string em int

    return df

```


A normalização (ou padronização) de dados é uma etapa crucial no pré-processamento de dados para muitos algoritmos de aprendizado de máquina, para isso fazemos um método de  divisão de teste de treinamento (Train Test Split), permitindo uma validação de modelos e simulação do desempenho do modelo com novos dados. 

Isso consiste em amostragem aleatória sem substituição de cerca de 70% das linhas (isso pode variar) e colocá-las em seu conjunto de treinamento. Os 30% restantes são colocados em seu conjunto de teste.  (“X_train,” “X_test,” “y_train,” “y_test”)[^comentario_1].

Esse tipo de teste possui vários benefícios, promover a convergência mais rápida dos modelos, evitar problemas numéricos, melhorar a interpretabilidade e a comparação entre features, e reduzir a sensibilidade a outliers. Além de evitar modelos excessivamente complexos que não generalizam bem para novos dados. 


## Exemplo de gráfico de Regressão Linear em Python:

```Python
# REGRESSÃO LINEAR 

def regressao_linear(df):
    # TRAIN TEST SPLIT 
    # Para a regressão as variáveis serão x (como um conjunto de todas as colunas menos o recurso alvo a ser observado) e Y (life_expectancy)
    X = df.drop(['life_expectancy'], axis =1)
    y = df['life_expectancy']

    # . Dividir os dados em conjuntos de treinamento e teste permite avaliar o desempenho do modelo em dados não vistos, ajudando a identificar se o 
    # modelo está superestimando (overfitting) ou subestimando (underfitting) os dados. No nosso caso, 30% dos dados serão utilizados para teste e 70% para treinamento.

    X_train_org, X_test_org, y_train, y_test = train_test_split(X, y, test_size = 0.3, random_state = 0)

    # Criando uma instância MinMaxScaler (método de normalização que transforma os dados de um intervalo específico, geralmente entre 0 e 1.)

    scaler = MinMaxScaler()
    X_train = scaler.fit_transform(X_train_org)
    X_test = scaler.transform(X_test_org)

    print("X_train shape: ",X_train.shape)
    print("y_train shape: ",y_train.shape)
    print("X_test shape: ",X_test.shape)
    print("y_test shape",y_test.shape)

    # Em resultado vimos que 2056 são X_train e 882 são X_test 

    # Criando uma Instância do Modelo de Regressão Linear
    lreg = LinearRegression()
    # Ajusta o modelo de regressão linear (lreg) aos dados de treinamento normalizados (X_train e y_train)
    lreg.fit(X_train, y_train)

    print('Train Score: {:.4f}'.format(lreg.score(X_train, y_train)))
    print('Test Score:{:.4f}'.format(lreg.score(X_test, y_test)))

    ylinear_predicted = lreg.predict(X_test)

    print('MSE:', metrics.mean_squared_error(y_test,ylinear_predicted))
    print('R2_score: {:.4f}'.format(metrics.r2_score(y_test,ylinear_predicted)))

    # Plotando os valores reais versus os valores previstos pelo modelo
    plt.scatter(ylinear_predicted, y_test, color = 'blue')
    plt.plot(y_test, y_test, color='red', label='Linha de Regressão')

    # Adicionando legenda
    plt.legend()

    plt.show()
```

### Implementação da regressão em Python:

A partir dos materiais disponibilizados pelo professor e pesquisas complementarem realizamos um projeto em Python para aplicar os conceitos abordados acima. 
Esse projeto está disponível no github - [Repositório de análises de regressão](https://github.com/katerine-dev/regressao) e falaremos melhor sobre os gráficos gerados nos tópicos abaixo.

Banco de dados utilizado:

A base utilizada foi encontrada no site Kaggle Datasets, ela é composta por 22 colunas, e 2938 linhas. Para realizar as análises foi necessário uma "faxina dos dados". Limpando nomes de colunas, tirando informações de `Null` e vazios. Abaixo Você pode visualizar as informações das colunas e types:

![Colunas Life Expectancy](/docs/informacoes-colunas.png)

## Referências:

[^comentario_1]: Fonte:  GALARNYK, M. Train Test Split: What it Means and How to Use It | Built In. Disponível em: <https://builtin.com/data-science/train-test-split>. Acesso em 25 de Maio de 2023.