
## 📦 Previsão de Estoque Inteligente com Amazon SageMaker Canvas

Este projeto foi desenvolvido como parte da formação **Machine Learning para Iniciantes na AWS** da DIO, com o objetivo de aplicar técnicas de Machine Learning no-code utilizando o **Amazon SageMaker Canvas** para prever a quantidade de estoque de produtos.

---

### 🎯 Objetivo

Criar um modelo preditivo capaz de estimar a quantidade de estoque com base em variáveis históricas, utilizando o SageMaker Canvas, sem a necessidade de programação.

---

### 🛠️ Etapas do Projeto

#### 1. Seleção do Dataset

- Dataset utilizado: `dataset-1000-com-preco-promocional-e-renovacao-estoque.csv`
- Fonte: Pasta `datasets` do repositório base disponibilizado pela DIO
- Upload realizado diretamente no SageMaker Canvas

#### 2. Criação do Modelo

- Nome do modelo: `previsao_estoque_inteligente`
- Tipo de análise: **Predictive analysis**
- Coluna alvo (target): `QUANTIDADE_ESTOQUE`
- Tipo de modelo: **Numérico** (Estimativa de valor)
- Método de construção: **Quick Build** (2 a 15 minutos)

#### 3. Métricas de Avaliação

- **RMSE (Root Mean Squared Error)**: `26.756`
- **MSE (Mean Squared Error)**: `715.859`

> O modelo geralmente prevê um valor dentro de ±26.756 da quantidade real de estoque.

#### 4. Análise e Insights

- As principais variáveis que influenciaram a previsão foram: `DATA_EVENTO`, `ID_PRODUTO`, `PRECO`, `FLAG_PROMOCAO`
- O modelo apresentou desempenho satisfatório para uma primeira versão com Quick Build.
- Possíveis melhorias incluem: uso de **Standard Build**, enriquecimento do dataset, e ajuste de variáveis.

#### 5. Previsões

- Foram realizadas previsões com base em novos dados.
- Os resultados foram exportados e analisados.
- [Adicione aqui prints ou gráficos, se desejar.]

---

### 📁 Arquivos Importantes

- `dataset-1000-com-preco-promocional-e-renovacao-estoque.csv`: Dataset original usado no treinamento
- `previsoes.csv`: Resultados das previsões exportadas
- `imagens/`: Prints das telas do SageMaker Canvas (gráficos, métricas, etc.)

---

### 🚀 Como Reproduzir

1. Faça o fork deste repositório.
2. Acesse o Amazon SageMaker Canvas com sua conta AWS.
3. Importe o dataset e siga os passos descritos acima.
4. Analise os resultados e compare com os seus.

---

### 📚 Recursos Complementares

- [Documentação Oficial do SageMaker Canvas](https://docs.aws.amazon.com/sagemaker/latest/dg/canvas.html)
- [Repositório base da DIO](https://github.com/digitalinnovationone/lab-aws-sagemaker-canvas-estoque)
- [Guia de Introdução ao SageMaker](https://docs.aws.amazon.com/sagemaker/latest/dg/whatis.html)

---

### 👨‍💻 Autora

- **Amanda Rezende Chaves**
- [LinkedIn - Amanda Rezende Chaves]([https://linkedin.com/in/seuusuario](https://www.linkedin.com/in/amanda-rezende-chaves-6927201bb/))
- [GitHub - AmandaRez]([https://github.com/seuusuario](https://github.com/AmandaRez))

---

### 📊 **Resumo da Análise do Modelo `previsao_estoque_inteligente`**

#### ✅ **Status do Modelo**
- **RMSE (Erro Quadrático Médio da Raiz)**: `26.756`  
  → Isso significa que, em média, o modelo erra a previsão da quantidade de estoque em cerca de **±26,76 unidades**.
- **MSE (Erro Quadrático Médio)**: `715.859`  
  → É uma métrica que penaliza erros maiores. Quanto menor, melhor.

---

### 🔍 **Colunas que Mais Influenciam a Previsão**
Essas são as variáveis que mais impactam o valor previsto para `QUANTIDADE_ESTOQUE`:

1. **DATA_EVENTO** – 56,22%  
   → A data do evento é o fator mais importante. Pode indicar sazonalidade ou padrões temporais.
2. **ID_PRODUTO** – 25,62%  
   → O tipo de produto também influencia bastante a quantidade em estoque.
3. **PRECO** – 17,14%  
   → O preço tem um impacto moderado. Pode indicar que produtos mais caros ou mais baratos têm padrões de estoque diferentes.
4. **FLAG_PROMOCAO** – 1,03%  
   → Promoções têm pouco impacto neste modelo, talvez porque não há muitos dados com promoções ou o efeito delas é pequeno.

!IMAGEM 1

---

### 📈 **Gráfico: Impacto da DATA_EVENTO**
- O gráfico mostra como diferentes datas influenciam a previsão da quantidade de estoque.
- Isso ajuda a entender se há sazonalidade (ex: mais estoque em dezembro, menos em janeiro, etc.).

---

### 📉 **Análise de Precisão: Predito vs. Real**

#### 📌 Gráfico: Predicted vs. Actual
- O gráfico mostra a comparação entre os valores **previstos** e os **valores reais** da coluna `QUANTIDADE_ESTOQUE`.
- Cada ponto azul representa uma previsão feita pelo modelo.
- O ideal é que os pontos estejam próximos da linha diagonal (onde previsto = real), o que indicaria alta precisão.

! IMAGEM 2 

#### 📏 Faixa de Erro (RMSE)
- O modelo tem um erro médio de **±26.756 unidades**.
- Quanto **mais espessa** a faixa de erro (RMSE band), **menor** a precisão do modelo.
- Isso significa que, embora o modelo esteja razoavelmente bom, ainda há espaço para melhorias, especialmente se os pontos estiverem muito dispersos.

---

### 📊 **Métricas Detalhadas do Modelo**

#### 📈 Métricas de Avaliação
- **RMSE (Erro Quadrático Médio da Raiz)**: `26.756`  
  → O modelo erra, em média, cerca de ±26,76 unidades.
- **MSE (Erro Quadrático Médio)**: `715.859`  
  → Penaliza erros maiores. Quanto menor, melhor.
- **MAE (Erro Absoluto Médio)**: `±19.198`  
  → Em média, o erro absoluto entre o valor previsto e o real é de 19,2 unidades.
- **R² (Coeficiente de Determinação)**: `17.246%`  
  → O modelo explica apenas cerca de **17% da variabilidade** dos dados. Isso indica que há espaço para melhorias.
- **MAPE (Erro Percentual Absoluto Médio)**: *Não disponível*

#### 📉 Gráfico de Resíduos
- Mostra a diferença entre os valores previstos e os reais.
- Os pontos azuis representam os resíduos.
- As linhas roxas indicam o MAE.
- Idealmente, os resíduos devem estar distribuídos de forma aleatória em torno de zero — isso indicaria que o modelo não está cometendo erros sistemáticos.

!Gráfico de Resíduos e Métricas Detalhadas

---

