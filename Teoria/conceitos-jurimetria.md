# Resumo sobre Jurimetria e seus conceitos

Material de apoio para estudo avançado sobre Jurimetria.

_Resumo dos livro "Metodologia de Pesquisa Jurimétrica" - Autores: Ricardo Feliz Okamoto e Julio Trecenti. E do livro "Jurimetria" - Autor: Marcelo Guedes Nunes._

1. Caracterização Geral da Jurimetria:

A Jurimetria é um campo emergente no direito, ainda em processo de definição conceitual. A definição mais precisa é que a Jurimetria é organizada em três eixos principais:

- Taxonomia: Reconhecida como uma disciplina do conhecimento, a Jurimetria não se restringe a ser um conjunto de técnicas, mas sim uma área de conhecimento que visa compreender o Direito a partir de uma perspectiva quantitativa.

- Método: Fundamentada no uso da metodologia estatística.

- Objeto de Estudo: Voltada para a análise do funcionamento da ordem jurídica. O foco da Jurimetria está no estudo do “funcionamento da ordem jurídica”, considerando não apenas normas abstratas, mas sua aplicação e interpretação concreta.

["A Jurimetria não se posiciona de nenhum lado das discussões da Estatística; ela não designa nenhum método ou técnica em específico dentro da Estatística. A Jurimetria apenas significa a aplicação destes métodos, em suas mais variadas formas, em todas as suas vertentes."](https://livro.abj.org.br/01-intro.html)

2. Planejamento de Pesquisa:

O planejamento de pesquisa é a etapa inicial de qualquer investigação quantitativa e visa definir claramente como o objeto será investigado e como as conclusões serão obtidas.

Vai além da escolha de métodos e técnicas (como regressão ou estudo de caso), abordando os pressupostos teóricos e as justificativas para as escolhas metodológicas.

_2.1._ Teoria empírica no Direito:

A teoria orienta a formulação de perguntas para pesquisas e estabelece o contexto acadêmico e social da investigação.

["A abordagem deve ser outra quando falamos de estudos jurimétricos. A questão central não é mais como as normas devem ser, não é mais interpretá-las em um plano abstrato; a questão agora passa a ser descrever a incidência dessas normas no mundo **real**."](https://livro.abj.org.br/01-intro.html)

As perguntas de pesquisa em jurimetria diferem das normativas típicas do Direito:

- Perguntas normativas: focam no dever ser das normas e conceitos abstratos.
- Perguntas descritivas: buscam descrever a aplicação prática das normas no mundo real.

A jurimetria exige adaptação de perguntas normativas para perguntas que possam ser respondidas por métodos quantitativos.

3. Planejamento da Pesquisa:

- Escopo do estudo:

Dimensão temporal:
Estudos prospectivos: acompanham processos desde sua distribuição até o desfecho.
Estudos retrospectivos: analisam processos já encerrados.

Dimensão geográfica:
Define a jurisdição ou região a ser estudada.
A escolha pode ser prática (disponibilidade de dados) ou guiada por critérios de conveniência, desde que justificada e reportada.

- Dados, Tribunais e Processos de Geração de Dados

Conhecimento dos dados: É essencial conhecer como os dados foram gerados para identificar potenciais vieses ou inconsistências. Informações como classe e assunto processuais podem conter erros devido ao preenchimento humano.

Criação de dados: Pesquisadores frequentemente criam variáveis a partir de dados existentes, como “teve_sentenca”. Este processo deve ser documentado para garantir transparência e reprodutibilidade.

Implicações para IA:
A compreensão do processo de geração de dados é crucial para avaliar a eficácia de algoritmos de IA usados em análises jurídicas.

Amostragem e População

Amostragem probabilística: Utiliza randomização para garantir que a amostra reflita a distribuição da população. Evita vieses sistemáticos, como seleção enviesada por critérios subjetivos.

Erro e viés: Erros aleatórios são naturais em amostragens, mas vieses sistemáticos comprometem os resultados.

Tamanho da amostra: O aumento do tamanho da amostra reduz os erros, mas recursos e tempo limitados exigem equilíbrio entre precisão e viabilidade.

4. Amostragem e Randomização

Importância da Randomização:

- A randomização garante que os resultados obtidos na amostra sejam representativos da população.
- Evita vieses e confounding effects, promovendo maior confiabilidade nas inferências realizadas.

Exemplos de Falta de Randomização:

- Estudo sobre condenados no sistema penal: Amostrar apenas réus condenados gera vieses, pois exclui pessoas não detectadas ou processadas.
- Dados sobre violência doméstica: Bases geradas por boletins de ocorrência subestimam a prevalência devido à subnotificação por medo ou desconfiança.
- Distribuição de processos judiciais: A ausência de randomização na escolha de juízes pode favorecer partes mais influentes (forum shopping - "O forum shopping é um efeito que acontece no Direito internacional em decorrência do conflito positivo de competências entre as jurisdições de mais de um país. Neste caso, não é que o processo não será distribuído aleatoriamente para um juízo; o problema é com a jurisdição.").

Impacto da Randomização em IA: Bases enviesadas impactam o desempenho, como no caso de algoritmos incapazes de reconhecer rostos de pessoas negras devido à predominância de dados de rostos brancos.

5. Tipos de Amostragem

- Amostragem Aleatória Simples:

  - Processo básico que seleciona observações de forma totalmente aleatória, sem seguir padrões. Exemplo em jurimetria: análise de processos em determinada vara, selecionando casos de um conjunto populacional muito amplo (e.g., 10 mil processos) para uma análise viável.

- Viés e Erro na Amostragem:

  - Erro aleatório: Inerente ao processo, não compromete a validade desde que seja distribuído aleatoriamente.

  - Viés sistemático: Introduzido por critérios não aleatórios, como a estratificação inadequada, distorce resultados.

- Tamanho da Amostra:
  - Aumentar o tamanho reduz o erro, mas há limitações práticas de tempo e custo.
  - O ideal é balancear precisão e viabilidade, ajustando o tamanho da amostra para minimizar erros.

6. Viés de Seleção em Processos Judiciais

Definição: Diferença entre os dados observados e a população que se deseja estudar Relacionado ao mecanismo de seleção que determina quais casos entram na base de dados.

["Viés de seleção é um tipo de viés estatístico, indicando uma diferença entre os indivíduos que estamos estudando na base de dados de dados e a população que desejamos estudar. Coloquialmente, viés de seleção é uma forma de dizer que estamos tirando conclusões sobre bananas ao estudar maçãs."](https://livro.abj.org.br/02-planejamento.html)

Exemplos Clássicos:

- Covid-19: Dados hospitalares superestimam a letalidade devido à exclusão de casos leves.
- Aviação militar: Proteção nas asas foi priorizada devido ao foco em aviões que retornaram, ignorando os destruídos.

Viés em Litígios Judiciais: A escolha de litigar depende das expectativas das partes (ex.: probabilidade de ganho) e dos custos envolvidos. A condição LPG (Landes-Posner-Gould) determina que processos ocorrem apenas quando a diferença de expectativas supera os custos relativos.

7. Teorema de Priest e Klein (1984)

Conceitos Centrais: Em litígios, as partes possuem níveis assimétricos de informação sobre mérito e custos. Conflitos com maior simetria informacional têm maior probabilidade de resultar em acordos, deixando casos mais incertos para litígio.

Implicações:

- Taxa de vitórias em torno de 50%:
- Observada devido à seleção de casos com mérito limítrofe para litígios.
- Inferências sobre o judiciário:
- Taxas de vitória devem ser analisadas com cautela; valores muito altos ou baixos indicam potenciais distorções nos custos ou assimetrias de informação.

Relevância:

- Ajuda a compreender a dinâmica de seleção de litígios e os impactos na eficiência do sistema judiciário.
- Orienta estudos empíricos sobre proporções de vitória e efeitos de mudanças legislativas.
