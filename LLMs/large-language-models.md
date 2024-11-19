# LLM - Large Language Models

## What is LLM?

É um tipo de rede neural treinada em grandes quantidades de dados de texto,
geralmente treinada em dados que podem ser encontrados online (Web scraping, books, transcripts, anything text-based).

Instância de algo chamado "fundation model" (são modelos básicos pré-treinados em grande quantidades de dados não totulados e auto-supervisionados, o que significa que o modelo aprende com os padrões dos dados de uma forma que produz resultados generalizáveis e adaptáveis).

![History LLMs](/Docs/history_llm.png)

## How do they work?

São aplicados especificamente a texto e coisas semelhantes a texto (código).
3 steps:

- Tokenization (redes neurais treinadas para dividir texto longo em tokens individuais.)

- Embedding: (Vectors 1D, os grandes modelos de linguagem transformam esses tokens em vetores de incorporação, transformando esses tokens em essencialmente um monte de números representação desses números de tokens e isso torna significamente mais fácil para o computador ler e entender cada palavra e como as diferentes palavras se relacionam entre si e todos esses números correspondem à posição em um banco de dados de vetores de incorporação)

  - Banco de dados vetoriais: são mecanismos de armazenamento e recuperação que são altamento otimizados para vetores e novamente esses são apenas números

- Tranformers: (input matriz - output matriz) isso é feito extraindo algumas informações dos números e colocando todas as inforamções em uma matriz através de um algoritimo chamato "multi-head attention"))

### LLM = 3 things

- Data (texto)
- Arquitetura (transformador)
- Treinamento (prever a próxima palavra, bug)

## Business applications

Empresas podem usar LLMs para:

- criar chatbots inteligentes que podem lidar com uma variedade de dúvidas dos clientes.
- Criação de conteúdo.
- Gerar e revisar código,.

-> Langchain \*\* continuar...
