# 📊 Previsão de Estoque Inteligente na AWS com [SageMaker Canvas](https://aws.amazon.com/pt/sagemaker/canvas/)

Bem-vindo ao desafio de projeto "Previsão de Estoque Inteligente na AWS com SageMaker Canvas. Neste Lab DIO, você aprenderá a usar o SageMaker Canvas para criar previsões de estoque baseadas em Machine Learning (ML). Siga os passos abaixo para completar o desafio!

## 📋 Pré-requisitos

Antes de começar, certifique-se de ter uma conta na AWS. Se precisar de ajuda para criar sua conta, confira nosso repositório [AWS Cloud Quickstart](https://github.com/digitalinnovationone/aws-cloud-quickstart).


## 🎯 Objetivos Deste Desafio de Projeto (Lab)

![image](https://github.com/digitalinnovationone/lab-aws-sagemaker-canvas-estoque/assets/730492/72f5c21f-5562-491e-aa42-2885a3184650)

- Dê um fork neste projeto e reescreva este `README.md`. Sinta-se à vontade para detalhar todo o processo de criação do seu Modelo de ML para uma "Previsão de Estoque Inteligente".
- Para isso, siga o [passo a passo] descrito a seguir e evolua as suas habilidades em ML no-code com o Amazon SageMaker Canvas.
- Ao concluir, envie a URL do seu repositório com a solução na plataforma da DIO.


## 🚀 Passo a Passo

### 1. Selecionar Dataset

-   Navegue até a pasta `datasets` deste repositório. Esta pasta contém os datasets que você poderá escolher para treinar e testar seu modelo de ML. Sinta-se à vontade para gerar/enriquecer seus próprios datasets, quanto mais você se engajar, mais relevante esse projeto será em seu portfólio.
-   Escolha o dataset que você usará para treinar seu modelo de previsão de estoque.
-   Faça o upload do dataset no SageMaker Canvas.

### 2. Construir/Treinar

-   No SageMaker Canvas, importe o dataset que você selecionou.
-   Configure as variáveis de entrada e saída de acordo com os dados.
-   Inicie o treinamento do modelo. Isso pode levar algum tempo, dependendo do tamanho do dataset.

### 3. Analisar

-   Após o treinamento, examine as métricas de performance do modelo.
-   Verifique as principais características que influenciam as previsões.
-   Faça ajustes no modelo se necessário e re-treine até obter um desempenho satisfatório.

### 4. Prever

-   Use o modelo treinado para fazer previsões de estoque.
-   Exporte os resultados e analise as previsões geradas.
-   Documente suas conclusões e qualquer insight obtido a partir das previsões.

## 🤔 Dúvidas?

Esperamos que esta experiência tenha sido enriquecedora e que você tenha aprendido mais sobre Machine Learning aplicado a problemas reais. Se tiver alguma dúvida, não hesite em abrir uma issue neste repositório ou entrar em contato com a equipe da DIO.


### Conclusão

Utilizei o arquivo dataset-500-curso-sagemaker-canvas-dio.csv como base para a análise.

Defini a coluna de quantidade de produto como o principal alvo do estudo.

Optei pelo modo quick build para acelerar o processo de criação do modelo.

O Root Mean Square Error (RMSE), que representa a média das diferenças entre os valores previstos e os valores reais, ficou em 1,527. Esse valor é aceitável, embora pudesse ser reduzido com um treinamento mais longo, como o de 4 horas. Em geral, quanto mais próximo de zero, melhor o desempenho.

Já o Mean Absolute Error (MAE), que mede o erro médio absoluto sem elevar os desvios ao quadrado (tratando todos os erros de forma uniforme), alcançou 0,178. Para um modelo gerado rapidamente, esse resultado é excelente — valores abaixo de 1 já indicam boa precisão.

O modelo ainda destacou duas colunas com possível influência sobre a variável de quantidade em estoque:

Holiday_BR: indica os feriados nacionais e apresentou impacto estimado de 1,98%. Esse efeito é muito pequeno, praticamente dentro da margem de erro indicada pelo RMSE, o que sugere que essa variável não influencia de forma relevante o estoque.

FLAG_PROMOCAO: obteve impacto de 0%, mostrando que a existência de promoção não altera o volume de estoque.

Com isso, é seguro afirmar que a melhor referência para tomada de decisão é a previsão P50, por representar um cenário intermediário entre a projeção otimista (P90) e a pessimista (P10). Assim, torna-se possível manter um nível de estoque equilibrado, evitando tanto excessos quanto faltas.
