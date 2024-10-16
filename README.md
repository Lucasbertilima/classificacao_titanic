Projeto de classificação da base de dados do titanic

# Importação das bibliotecas

 Primeiramente importamos todas as bibliotecas que serão utilizadas no nosso projeto, como o pandas e as bibliotecas de machine learning do sklearn

 # Carregando os datasets

 Em sequencia importamos os dois datasets do Drive usando  o read_csv do pandas

 # Visualização dos dados

 É feito um display dos dados para entender como eles são, em sequencia eu uso metodos do pandas para entender o estado do dataset, como o shape para ver a quantidade de linhas e colunas, o describe que mostra varias informações como a quantidade de linhas por coluna, a media, a variação padrão (std). o dtypes para ver qual a tipagem de cada coluna, e em sequencia é feito um for para visualizar quantas linhas nulas existem em cada coluna.

 #Tratamento de nulos

 Aqui é feito o tratamento dos nulos nas colunas, usando diferentes metodos dependendo do tipo da coluna, por exemplo na coluna 'Cabin' é string, então só substituimos os nulos por string vazia, na coluna 'Age' é int de idade, então usamos a mediana para preencher os faltantes, foi usado a mediana pois foi feito um plot da coluna usando um histograma e entendi que não tinha uma distribuição normal, então a mediana ajudaria melhor pois ela não seria muito afetada por outliner.

 #Seleção de colunas para o treino
 Aqui selecionamos as coluna para treino ['Pclass', 'Sex', 'Age','Fare', 'Survived', 'Embarked'], e fazemos um get_dummies que transforma as colunas categoricas em números.

 #Divisão de treino e teste
 Aqui usamos o train_test_split do sklearn para separa o dataset em duas partes, uma para o treino do modelo de machine learning e outra para testar ele, foi dividido em 70% para treino e 30% para teste.

 #Treino do modelo
 Usamos o KNN(K Nearest Neighbors) para treinar o modelo, esse algoritmo vai basicamente calcular a distancia dos vizinhos mais proximos do dado, nesse modelo passamos o parametro k=3 que vai fazer com que ele considere os 3 vizinhos mais proximos

 #Acuracia e matriz de confusão
 Em sequencia fazemos um teste de acuracia que apontou que nosso modelo tem a nota de 68%, e plotamos uma matriz de confusão, que vai nos dizer como foi o resultado do modelo falando quantos foram verdadeiros positivos, verdadeiro negativo, falso positivo e falso negativo

 ##Conclusão
 Nosso modelo obteve uma acuracia de 68%, por ser um problema mais simples acredito que isso seja uma nota ruim, o que significa que o nosso modelo pode ser melhorado, talvez usando outro metodo para tratar os nulos, como usar a media em vez da mediana pode nos dar um resultado melhor, outro jeito seria mexer nos parametros do modelo, como almentar o numero de vizinhos que vão ser consideras, no nosso algoritmo isso não deve ser dificil, já que temos um dataset bem pequeno, mas em datasets maiores isso vira um problema pois o algoritmo vai precisar de mais processamento para conseguir rodar.
