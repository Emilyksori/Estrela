# Pré-Processamento

# **Análise de dados**
#### É feita análise de dados em acordo com gráficos, sendo eles de pizza, barras, linhas e etc. O objetivo principal é extrair informações úteis para observação dos dados, pelos gráficos criados de acordo com os atributos requisitados, como: Quantos sobreviveram e morreram de cada classe da Pclass realizados por um gráfico de linha, a observação nesse gráfico em si foi que a classe 3 representada pelas pessoas de classe alta sobreviveram mais do que as pessoas de classe baixa, diferencialmente na quantidade de pessoas que morreram, a classe baixa teve mais indícios de mortos do que de a classe alta. Outrossim. na análise de dados é reconhecido o padrão dos dados anteriormente ao tratamento de dados.

<br/>

# **Tratamento de dados**
## Tópicos do tratamento de dados:

- ### **Remoção das colunas irrelevantes**
#### Remove-se as colunas que tem dados irreleventes para o treinamento de modelos, em outros termos as colunas que foram removidas tendem a ser dados str que não há a possibilidade de tratamento para int, portanto para remoção é utilizado a função .drop().

<br/>

- ### **Dados Faltantes**
#### Nos dados faltantes é tratado fazendo a média dos dados e/ou colocando "0" para representação que não há existência desse dado, aplicando a função .fillna() que gerencia e permite que substitua os valores; para a média .mean(). Para tratar os dados usando a média eles devem ser dados númericos e não obter muitos dados faltante, o tratamento com o posicionamento do "0" na demonstração de dado inexistente consiste quando o dado é uma string que não tem poucos dados faltantes.

<br/>

- ### **Dados Categóricos**
#### Os dados categóricos são tratados de str para int, alterando suas classes por dados númericos, empregando a função .replace() que é utilizada para manipulação de variáveis do tipo string.

<br/>

- ### **Dados Duplicados**
#### Para os dados duplicados é necessário a remoção delas, usando a função .drop_duplicates(inplace=True) remove todos os dados duplicados de forma automatica. Consistindo na importância de não houver números pares de atributos originais, devido que o número repetido pode ser alto tornando uma tarefa computamente custosa, além de produzir uma quantidade de dados extremamente desbalanceada.

<br/>

- ### **Normalização dos dados númericos**
#### É utilizada para redução do problma de enviesamento no treinamento de modelos, ao qual pode-se achar que o atributo com a escala maoir é amais importante que a menor. Dessa forma, quando se há intervalos abrangentes entre as variáveis númericas, representados na distribuição de cada atributo necessita fazer a normalização para que os dados estejam no mesmo intervalo, mantendo sua originalidade. Uma das formas para a normalização ser tratada é utilizando o Zscore, uma fórmula estastística que aproxima todos os dados sendo a média em zero e o desvio padrão em 1.

<br/>

- ### **Balanceamento dos dados categóricos**
#### O balanceamento de dados refere-se ao processo de equiparar, um determinado conjunto de dados, a quantidade de amostras de cada classe disponível para análise, tornando-se igualmente representadas. 



Ele gera problema na construção de modelos e na geração de previsões. Dado que, com os altos valores numa determinada amostragem, ela desenvolverá previsões de possiveis amostras tornando-se inviável, já que com os dados previstos o índicede obter valores originais diminuirá dependendo da quantidade minoritária de cada classe, construindo assim dados "irrelevantes" para previsões. De outro modo, o desequlíbrio efetua como uma incidência dentre as classes minoritária e majoritária dos dados.

<br/>

##### **Oversampling**: Realiza o aumento de uma amostragem que está com a frequência mínims da amostragem, dessa forma aplicado o SMOTE sendo uma das técnicas utlizadas para resolução do problem de maneira simplista.

##### **Undersampling**: Consiste em manter os dados de classe com menor frequência e na diminuição na quantidade dos dados queestão na classe de maior frequência.

<br/>

- ### **One Hot Enconding**
#### Trata os dados categóricos em dados binários, assim cada dado categórico é criado uma nova coluna, atriuindo no valor de cada linha respectiva como "1" ou "0", sendo classificado os 1 para a presença da característica e do contrário 0, conseguinte melhora o desempenho do modelo, devido a que oferece mais informações da variável categórica. Ademais, com os dados categóricos o modelo tende a classificar os valores pelo seu peso, exemplo: Dentre 0 e 5, o valor 5 tem mais "prioridade" do que o 0, visto que ele qualificará o valor mais alto como peso maior, porém tratando de uma decisão é fundamental que os dados sejam de certa forma classificadas como "sim" ou "não".

<br/>

- ### **CSV tratado**
#### Após todos os tópicos anteriores é situado todos os dados tratados num novo DataSet destinado a ser utilizado no treinamento de modelos.

<br/>

# **Treinamento de Modelos**
#### Treinamento de modelos é o processo de alimentar um algoritmo com os dados do DataSet atualizado para ajudar a identificar e aprender bons valores para todos os atributos envolvidos. Existindo assim vários tipos de modelos para treinamento. Com base nisso, os modelos utilizados foram: Linear Models (MMQ); Support Vector Machines; KNN; Naive Bayes; Decision Trees; Ensamble methods (Random florest). 
#### Para a elaboração dos modelos é primordial as sepações dos dados, adquirindo os dados X e y, referindo o X como os dados do DataSet sem a coluna alvo, e o y apenas com a coluna alvo. Conseguinte, para cada modelo obtem sua função colocada em uma variável como por exemplo o modelo MMQ mmq = LinearRegression(), para que o processo do modelo seja executado empregando a função .fit(=X_train, y=y_train), a função fit ela ajusta o modelo aos dados que está sendo executado, assim dizendo, ele faz o cálculo do modelo com os dados de treino, em diante a função .predict() ... 
Em continuidade para que os dados sejam mostrados como matriz a função confusion_matrix(y_true=y_test, y_pred=y_pred) é executada,

print(classification_report(y_true=y_test, y_pred=y_pred))


