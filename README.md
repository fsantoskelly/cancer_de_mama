# Modelo para diagnóstico de câncer de mama

👩‍💻 Autor: Kelly Ferreira

🛠️ Linguagem: Python

📈 Desenvolvido durante a Trilha Data Science - ADA Tech

Fonte do Dataset: [Kaggle](https://www.kaggle.com/datasets/yasserh/breast-cancer-dataset?resource=download)

## Objetivo do Modelo

Utilizar os parâmetros de **características morfológicas** das células a fim de identificar padrões associados ao câncer de mama

## 📚Bibliotecas utilizadas/ aplicabilidade

🔹 Pandas

O `pandas` foi usado para manipulação e análise dos dados, facilitando a leitura do arquivo e o pré-processamento das variáveis. Ele foi essencial para tratar dados ausentes e converter variáveis para os tipos adequados.

🔹 Scikit-learn

O `scikit-learn` foi usado para a regressão logística, treinamento do modelo, para parametrizar a matriz de confusão e avaliação da precisão, acurácia, precisão, recall e F1-Score

## 🧮Desenvolvimento do modelo

🔹 Carregamento do dataset:

`df = pd.read_csv('breast-cancer.csv')`

🔹Visualização das colunas/linhas da tabela:

`df.head()`

![image](https://github.com/user-attachments/assets/c5194b00-eb19-441c-91b6-9b06411308a2)

🔹Mudança do padrão da coluna diagnóstico, em que `M` seria 1 (maligno) e `B` seria 0 (benigno):

`x= df.drop(columns = ['id', 'diagnosis'], axis=1)`

`y = df['diagnosis']`

🔹Criação do modelo de aprendizagem:

`modelo = LogisticRegression(max_iter = 10000)`

🔹Separação dos dados em `treino`e `teste`:

Os dados foram divididos em  (X) e  (y), e em seguida separados em conjuntos de treino e teste.

`x_treino, x_teste, y_treino, y_teste = train_test_split(x, y)`

🔹Treinamento do modelo:

Um modelo de regressão logística foi treinado com os dados de treino. O parâmetro `max_iter` é aplicado para garantir que o algoritmo tenha tempo suficiente para convergir.

`modelo.fit(x_treino, y_treino)`

🔹Fazendo a predição:

`y_previsto = modelo.predict(x_teste)`

🔹 Gerando uma matriz de confusão: 

A matriz de confusão foi criada para exibir o relatório de classificação  e avaliar o desempenho do modelo.

`cm = confusion_matrix(y_previsto, y_teste)`` 

🔹 Chamando a imagem "matriz de confusão"

`plot_confusion_matrix(cm)`

![image](https://github.com/user-attachments/assets/56160aaf-854c-490e-912d-c276c47f7fcf)

🔹 Visualização das classificações: 

`print(classification_report(y_previsto, y_teste))`

##  📝Considerações Finais

🔹 O modelo de regressão logística apresentou um desempenho bom para este problema de diagnóstico de câncer, com uma alta taxa de recall (90%), o que significa que ele identifica corretamente a maioria dos casos de câncer.

🔹A precisão poderia ser melhorada para reduzir o número de falsos positivos, mas a alta taxa de recall é um bom indicativo de que o modelo é útil para diagnóstico precoce, onde a prioridade é identificar a presença de câncer.

💡 O modelo de regressão logística é eficaz e fornece uma boa base para a sugestão de diagnóstico de câncer. A capacidade do modelo de identificar a presença de câncer (alta taxa de recall), sendo, portanto, uma boa ferramenta para auxílio diagnóstico em um contexto médico, onde são avaliados outros sinais, sintomas e parâmetros para fechamento do diagnóstico. No entanto, melhorias podem ser feitas para reduzir os falsos positivos e aumentar a precisão do modelo, garantindo uma melhor confiança nos diagnósticos feitos.











