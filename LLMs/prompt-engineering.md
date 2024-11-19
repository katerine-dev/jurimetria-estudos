# Prompt Engineering

## What's is prompt engineering?

Any use of on LLM out-of-the-box.

1. The means by which LLMs are programmed with prompts, uma nova forma de programar.
2. is "an empirical art of composing and formatting the prompt to maximize a model's performance on a desired task.

Two levels of prompt engineering:

- The easy way: Chatgpt, Bard, bing chat. (interage com LLM)
- The Less easy way: Programmatically (python, javascript)

Formas de lidar melhor com gpt:

- Be descriptive
- Give examples
- Use Structure text
- Split on steps
- Ask for gpt made questions
- Ask for gpt review, and refine the answers

### LangChain

A classe LLM foi projetada para fornecer uma interface padrão para todos os modelos.

_Prompts_ são as instruções fornecidas a um grande modelo de linguagem e a classe de modelo de prompt em LangChain formaliza a composição dos prompts sem a necessidade de codificar manualmente o contexto e as consultas.

_Cadeias (Chain)_, como o nome indica são o núcleo dos fluxos de trabalho do LangChain, eles combinam LLMs com outros componentes, criando aplicações através da execução de uma sequência de funções.

_Indexs_:

- (docu. loader) carregador de documentos: funcionam com aplicativos de terceiros para importar fontes de dados como serviço de armazenamento de arquivos (dropbox, google drive...)
- (vector DataBase) banco de dados vetoriais: diferentemento dos banco de dados estruturados tradicionais, os bancos de dados vetoriais representam pontos de dados convertendo-os em algo chamado incorporação vetorial, que são representações numéricas na forma de vetores com um número fixo de dimensões. E você pode armazenar muitas informaçÕes neste formato, pois é um meio de recuperação muito eficiente.

- (text splitter) divisores de texto: pode dividir o texto em pequenos pedaços semanticamente significativos que podem ser combinados usando os métodos e parâmetros de sua escolha.

_Memory_: memória imbutida no app.

_Agents_: os agentes podem usar um determinado modelo de linguagem como mecanismo de raciocínio para determinar quais ações tomar.

_Usos do langchain_: Chatbots, summarization, question/answering, data augmentation, virtual agents
