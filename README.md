# Prototipo de classificação de produtos com IA
![image](https://github.com/user-attachments/assets/33609c73-4af5-4d50-ab81-4ee65e7e39a0)

Este projeto demonstra a criação de um protótipo de modelo de aprendizado de máquina para classificar produtos da Amazon usando um Large Language Model (LLM). O modelo é treinado em um conjunto de dados público do Amazon Brazil 2023 e utiliza a técnica de "few-shot prompting" para classificar novos produtos. O código completo do projeto está disponível [aqui](link do código).

Contexto do Negócio:

O objetivo do projeto é automatizar processos de estoque de produtos na Amazon. Através da classificação precisa dos produtos, é possível otimizar a organização e o gerenciamento do estoque, reduzindo custos e aumentando a eficiência.

Metodologia:

O modelo utiliza o LLM ChatGPT para realizar a classificação dos produtos. O LLM é treinado em um dicionário de 40 exemplos de classificação produto-categoria e, em seguida, recebe como entrada o nome de um novo produto e classifica-o em uma das categorias possíveis.

Avaliação do Modelo:

A performance do modelo foi avaliada utilizando as métricas de acurácia e similaridade semântica. A acurácia média obtida foi de 90%, com variações entre 60% e 90% ao longo dos testes. A similaridade semântica também apresentou média de 90%.

Próximos Passos:

Ampliar o conjunto de dados: Utilizar um conjunto de dados maior e mais representativo para melhorar a generalização do modelo.
Implementar técnicas de pré-processamento de texto: Aplicar técnicas de pré-processamento, como limpeza e normalização de texto, para melhorar a qualidade dos dados e o desempenho do modelo.
Explorar outros modelos de LLM: Testar o desempenho de outros modelos de LLM, como o LaMDA ou o WuDao 2.0, para verificar se obtêm resultados superiores.
Integrar o modelo em uma aplicação real: Implementar o modelo em uma aplicação real para automatizar a classificação de produtos na Amazon.
Conclusão:

Este projeto demonstra o potencial do uso de LLMs para a classificação de produtos. O modelo protótipo apresentado obteve resultados promissores, com alta acurácia e similaridade semântica. Com as melhorias propostas nos próximos passos, o modelo poderá ser aprimorado e utilizado em aplicações reais para automatizar tarefas de classificação de produtos na Amazon.

Observações:

Este projeto foi realizado em pequena escala, utilizando apenas duas colunas do conjunto de dados original e uma amostragem aleatória de 50 linhas.
As métricas de avaliação podem sofrer variações devido à amostragem aleatória dos dados.
É importante ressaltar que modelos de LLM, como o ChatGPT, requerem credenciais pagas para serem utilizados em larga escala.
