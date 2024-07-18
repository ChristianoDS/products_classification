# 🛍️ Protótipo de Classificação de Produtos com IA
![image](https://github.com/user-attachments/assets/33609c73-4af5-4d50-ab81-4ee65e7e39a0)

# 📝 1.0 Descrição do Projeto
Este projeto visa criar um protótipo de modelo de Inteligência Artificial (IA) para classificar produtos da Amazon usando um Large Language Model (LLM). O modelo foi treinado utilizando um conjunto de dados público do Amazon Brazil 2023 e emprega a técnica de "few-shot prompting" para categorizar novos produtos. 

# 📈 2.0 Problema de Negócios
## 🌐 2.1 Contexto da Amazon
A Amazon, como líder global no comércio eletrônico, enfrenta desafios significativos na classificação manual de milhões de produtos que são adicionados à sua plataforma diariamente. Este processo manual é:

Ineficiente: Demanda muito tempo e recursos humanos.
Caro: Envolve custos elevados devido à necessidade de uma grande equipe para a categorização manual.
Propenso a Erros: A natureza manual do processo aumenta a probabilidade de erros de classificação, o que pode afetar negativamente a experiência do cliente.

## ⚠️ 2.2 Impactos Negativos da Classificação Manual
Aumento de Custos Operacionais: A manutenção de uma grande equipe para classificação manual implica em altos custos trabalhistas.
Ineficiências Operacionais: A lentidão do processo manual pode atrasar a disponibilidade dos produtos para venda, impactando negativamente a experiência do cliente e as vendas.
Erros de Categorização: Produtos mal categorizados dificultam a busca pelos clientes, prejudicando a navegação na plataforma e a satisfação do cliente.

# 💡 3.0 Solução Proposta
🤖 3.1 Modelo de Classificação Automática
Implementação de um modelo de classificação automática utilizando IA, especificamente um LLM, para resolver os desafios mencionados:

Redução de Custos: Automatizar a classificação elimina a necessidade de mão de obra manual, reduzindo significativamente os custos operacionais.
Aumento da Eficiência: O processo automático é rápido e preciso, permitindo que novos produtos sejam categorizados e disponibilizados para venda rapidamente.
Melhoria da Experiência do Cliente: Categorização precisa facilita a busca pelos produtos, aumentando a satisfação dos clientes e impulsionando as vendas.
Minimização de Erros: A IA reduz drasticamente a ocorrência de erros de categorização, garantindo uma melhor organização e confiabilidade da plataforma.

# 🔍 4.0 Contexto do Negócio
O objetivo principal do projeto é automatizar o processo de classificação de produtos na Amazon, otimizando a organização e o gerenciamento do estoque. Isso permitirá:

Redução de Custos Operacionais: Menor necessidade de recursos humanos para categorização.
Aumento da Eficiência Operacional: Produtos disponíveis para venda mais rapidamente.
Melhoria na Experiência do Cliente: Navegação mais eficiente e precisa na plataforma.

# 📊 5.0 Aquisição dos Dados
Foram utilizados dados públicos do dataset da Amazon Brazil 2023 ([fonte dos dados](https://www.kaggle.com/datasets/asaniczka/amazon-brazil-products-2023-1-3m-products)) para o desenvolvimento do protótipo. Com mais de 1.3 milhões de produtos únicos, o dataset oferece uma ampla visão dos produtos disponíveis no website da Amazon Brasil, uma das maiores revendedoras online do país. Coletados através de um vasto processo de web scrapping em 2023, esse conjunto de dados traz informações como nome do produto, preço, avaliações e mais.

## 🧩 5.1 Premissas Adotadas
Para este protótipo, foram feitas algumas considerações importantes:

- Credenciais Pagas para IA: Modelos de Inteligência Artificial, como o ChatGPT (usado neste caso), para serem utilizados em maior escala, requerem credenciais pagas (com cerca de U$ 5,00 você já consegue fazer muita coisa), como uma API_KEY, ou uma chave de acesso ao modelo. Diante dessa limitação, optou-se por trabalhar em pequena escala.
- Escopo Reduzido: Foram consideradas apenas duas colunas do conjunto de dados original (dataframe): 'title' e 'categoryName' e uma amostragem aleatória de 50 linhas. A coluna 'title' traz os nomes dos produtos e a coluna alvo será a 'categoryName', a qual traz a categoria do produto classificado. Como a amostragem dos dados foi feita de forma aleatória, variações nas métricas do modelo são esperadas.
- Divisão de Dados: Foram separados 40 linhas para os dados de treino e 10 linhas para os dados de teste. Com maiores recursos, é possível trabalhar com maiores conjuntos de dados, ou até fazer uma amostragem estratificada que seja representativa da população.

# 🔧 6.0 Metodologia Proposta
## 🏗️ 6.1 Estrutura do Modelo
O modelo utiliza o LLM ChatGPT para realizar a classificação dos produtos. A metodologia adotada inclui:

Treinamento com Few-shot Prompting: Utilizando um dicionário de 40 exemplos de classificação produto-categoria para treinar o LLM.
Classificação Automática: O modelo recebe como entrada o nome de um novo produto e o classifica em uma das categorias possíveis.

## 🧠 6.2 Lógica por Trás do Modelo de Classificação
Toda a lógica envolvida no modelo é baseada no prompt para o Large Language Model (LLM). LLMs são sistemas de inteligência artificial avançados projetados para entender, gerar e traduzir texto em linguagem natural. Eles são treinados em vastos conjuntos de dados de texto e aprendem a prever a próxima palavra em uma sequência, permitindo-lhes gerar respostas coerentes e contextuais.

A ideia aqui foi criar um dicionário com 40 exemplos de classificação de produtos ({'title': 'categoryName'}) e mostrar ao modelo (GPT-4). Depois disso, apresentar uma lista com todos os valores únicos de classificação possíveis ('categoryName') para contextualizar quais strings de classificação o modelo terá que fazer.

Por fim, foi criado um sistema de processamento em batelada (batch) para passar linha a linha para os dados não vistos (10 linhas), com isso, o modelo recebe o nome do produto não visto ('title') e classifica com base nos exemplos vistos (técnica de few-shot prompting).

# 🎯 7.0 Avaliação do Modelo
A performance do modelo foi avaliada utilizando as seguintes métricas:

Acurácia: Média de 90%, com variações entre 60% e 90% ao longo dos testes.
Similaridade Semântica: Média de 90%, avaliando a proximidade semântica entre a classificação prevista e a categoria correta.

![image](https://github.com/user-attachments/assets/32a7f4c7-a780-4203-bc3b-ee3613e52e51)


# 🚀 8.0 Próximos Passos
## 🗂️ 8.1 Ampliar o Conjunto de Dados
Utilizar um Conjunto de Dados Maior: Ampliar a base de dados para melhorar a generalização do modelo.
## 🔍 8.2 Implementar Técnicas Avançadas de Pré-processamento
Limpeza e Normalização de Texto: Aplicar técnicas avançadas para melhorar a qualidade dos dados de entrada.
## 📚 8.3 Explorar Outros Modelos de LLM
Testar Diferentes Modelos: Testar o desempenho de outros modelos de LLM, como o Claude 3.5 Sonnet, ou modelos mais leves e baratos como o Llama, para verificar se obtêm resultados superiores.
## 🏷️ 8.4 Implementar o Modelo em Aplicação Real
Automatização Completa: Implementar o modelo em uma aplicação real para automatizar a classificação de produtos na Amazon. Aqui pode ser através de uma API no Google Sheets para quando receber a planilha de produtos, já se obter um resultado automático da respectiva classificação.
# 🔚 9.0 Conclusão
Este projeto demonstra o potencial do uso de LLMs para a classificação de produtos na Amazon. O modelo protótipo apresentado obteve resultados promissores, com alta acurácia e similaridade semântica. Com as melhorias propostas nos próximos passos, o modelo poderá ser aprimorado e utilizado em aplicações reais para automatizar tarefas de classificação de produtos na Amazon, proporcionando ganhos significativos em eficiência e redução de custos.

# 9.0 Ferramentas utilizadas
- ![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
- ![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white)
- ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
- ![requests](https://img.shields.io/badge/requests-FF6F00?style=for-the-badge&logo=requests&logoColor=white)
- ![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)
- ![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
- ![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)


## 🗒️ Observações
Escala do Projeto: Realizado em pequena escala, utilizando apenas duas colunas do conjunto de dados original e uma amostragem aleatória de 50 linhas.
Variabilidade nas Métricas: As métricas de avaliação podem sofrer variações devido à amostragem aleatória dos dados.
Requisitos de Uso: Modelos de LLM, como o ChatGPT, requerem credenciais pagas para serem utilizados em larga escala.
Com a implementação das melhorias sugeridas, o modelo tem o potencial de se tornar uma ferramenta valiosa para a Amazon, automatizando o processo de classificação de produtos e melhorando a experiência do cliente na plataforma.


