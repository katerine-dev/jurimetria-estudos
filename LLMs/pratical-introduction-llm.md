# Pratical introduction to LLMs

3 levels of using LLMs:

### Level 1: Prompt Engineering

Using an LLM out-of0the-box (not changing any model parameters)

- Easy Way: chatgpt
- Less Easy way: OpenAI API, Hugging Face - open source, (request, response)

### Level 2: Model Fine-tuning

Adjusting at least 1 (internal) model parameter (but not all) for a particular task

Step 1 "Pre-trained": Obtem um modelo de linguagem pré treinado, (talvez de IA aberta ou talvez de um modelo de código aberto da biblioteca de transformadores) - modelo auto-supervisionado, \* can also be "pre-fine-tuned"

Step 2 "Fine-tuned": Atualiza os parâmetros do modelo, dados exemplos específicos de tarefas. Ajustar os parâmetros do modelo para um caso de uso específico.

Step 3: você implementará um modelo de linguagem grande e ajustado. (Profit?)

### Level 3: Build your own

Come up with all model parameters.

- Book corpus, wikipedio corpus, python corpus...

Documetation: https://platform.openai.com/docs/api-reference/chat

## Introdution & Example code

### What's an API?

_Application Programming Interface (API)_ = way to interact with a remote application programmatically.

1. Customizable System Message
2. Adjust Input Parameters (ex: Max response length, number of responses, and temperature)
3. Process images and other file types
4. Extract helpful word embeddingds for down stream tasks
5. Model fin-tuning functionality

### Tokens & Pricing

Tokens = a set of words and characters represented by a set of numbers

(Isso é relevante para a precificação, pois a precificação com a API do openai é baseada no número de tokens enviados para a API e o número de token retornados: https://openai.com/api/pricing/)

### Comentários sobre o código:

Para projetos que podem conter mais aletoriedade

```python
for i in range(len(response.choices)):
    print(response.choices[i].message.content)
```

#### Temperature parameters:

Para projejtos que precisam de dados muito determinísticos ou que precisam que a saída seja muito previsível e idêntica toda vez que for chamada, usamos um parâmetro chamada `temperature`, assim podemos controlar esse grau de aletoriedade ou previsibilidade.

Ela pode receber valores entre 0 e 2, um valor de temperatura igual a 0, tornará as respostas muito determinísticas, muito previsiveis, enquanto no outro extromo (2), tornará as respostas muito aleatórias.

#### For example:

Temperature 2:

```python
response = openai.ChatCompletion.create(
    model="gpt-3.5-turbo",
    messages=[
        {"role": "user", "content": "Listen to your"}
    ],
    max_tokens = 2, # ajusta o número máximo de tokjens permitidos na response.
    n = 5 , # controla o número de respostas enviadas de volta no modelo
    temperature = 2
)
```

Out:

```python
instinct
thought by
inner voice
instinct
intuition
```

Temperature 0 :

```python
response = openai.ChatCompletion.create(
    model="gpt-3.5-turbo",
    messages=[
        {"role": "user", "content": "Listen to your"}
    ],
    max_tokens = 2, # ajusta o número máximo de tokjens permitidos na response.
    n = 5 , # controla o número de respostas enviadas de volta no modelo
    temperature = 0
)
```

Out:

```python
heart,
heart,
heart,
heart,
heart,
```
