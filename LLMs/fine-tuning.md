# Fine-tuning LLMs

## What is Fine tuning?

Taking a pre-trained model and training at least one model parameter.

Why fine-tune? A smaller (fine-tuned) model can outperform a lager base model.

1. self supervised: Meio de aprendizado auto-supervisionado, você obtém seu corpus de texto de treinamento e treina o modelo de forma auto-supervisionada em outras palavras, você pega uma sequência de texto, like: "listen to your" e alimenta no modelo e faz com que ele preveja uma conclusão.

2. Supervised: Meio de aprendizado supervisionado, aqui temos um conjunto de dados de treinamento que consiste entradas (inputs) e saídas (outputs).

3. Reinforcement learning: Meio de aprendizado por reforço.

- supersived FT
- train reward model
- RL with PPO (otimização de política proximal - an algorithm in the field of reinforcement learning that trains a computer agent's decision function to accomplish difficult task)

## Pratice:

### Supervised Fine-Tuning (in 5 steps)

1. Choose fine-tuning task: text summarization, text generation, binary classification, text classification

2. Prepare training dataset

3. Choose a base model

4. **Fine-tune model via supervised learning**

5. Evaluate model performace

### 3 Opitions for parameter training

1. Retrain all parameters: treinar novamente todos os parâmetros. (expensive)
2. Transfer Learning: congelamos a maioria dos parâmetros e ajustamos a cabeça, ou seja ajustamos o último poucas camadas do modelo onde os embeddings do modelo ou representações internas traduzidos no target ou na camada de saída e - aprendizagem por transferência muito mais barata do que treinar novamente todos os parâmetro
3. Parameter efficient Fine-tuning (PEFT): congelamos todos os pesos, não alteramos nenhum parâmetro interno do modelo, em vez disso, o que fazemos é aumentar o modelo com parâmetros adicionais que são treináveis e a razão pela qual isso é vantajoso é podemos ajustar um modelo com um conjunto relativamente pequeno de novos parâmetros. (Low-Rank adaptationn (LoRA) - fine-tunes models by adding new tranable parameters).
