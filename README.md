# Projeto-Previsao-de-Demanda

## Descrição do projeto 
Este é um código Python que realiza previsões de séries temporais de vendas utilizando o pacote PyCaret. O código importa o pacote Pandas para lidar com os dados, o pacote PyCaret para realizar as previsões e o Win32COM para enviar um e-mail com os resultados.

## Importação dos dados
A importação dos dados é feita através da biblioteca Pandas, com um arquivo local denominado 'pandas.xlsx'. Após a importação, é possível visualizar os dados com o qual trabalharemos:

![image](https://user-images.githubusercontent.com/87774019/216478358-d88543f5-6ce8-4f8b-9983-f8c14ac01e63.png)

A base de dados possui 47 linhas e 2 colunas, sendo elas 'vendas' e 'data'. Após a importação dos dados, foi necessário transformar a coluna 'Data' em DataTime e em index, para que assim o Python entenda que a coluna se trata de uma linha temporal.

## Escolha do melhor modelo

Em seguida, o PyCaret é configurado com a série temporal e uma comparação entre modelos é realizada para identificar o melhor modelo. Para isso, o método "compare_models" é utilizado.

![image](https://user-images.githubusercontent.com/87774019/216480561-bbd4b887-c4e0-46fe-ad4c-48845c9b5216.png)

O método ARIMA é selecionado por obter os melhores resultados dentre os modelos. A métrica R², a mais utilizada, aponta um resultado de 0.86 (neste caso, quanto mais próximo de 1, mais próximos os dados são da realidade).

## Criação do modelo e teste

É criado então o modelo ARIMA. Após isso, é plotado um gráfico que representa de maneira eficiente os dados utilizados para a avaliação do modelo, permitindo uma comparação direta com os dados originais:

![image](https://user-images.githubusercontent.com/87774019/216481913-b79111bd-4fda-4a02-9c74-53994fa928b2.png)

Repare que os dados utilizados para treino estão em azul, enquanto os dados que representam o resultado do teste estão em amarelo. O resultado é praticamente o mesmo da realidade.

## Resultado final e previsão para os próximos 5 dias

Após a configuração e avaliação do modelo, o código foi utilizado para fazer previsões dos próximos 5 dias de vendas. O resultado final desta aplicação foi o seguinte:

![image](https://user-images.githubusercontent.com/87774019/216482453-575586f5-f829-4128-a50b-bb4711c6db49.png)

A parte destacada em azul é o resultado da previsão, que compreende os dias 21-25 de janeiro.

## Envio dos resultados para o e-mail

O código finaliza com a realização de previsões de vendas e a sua armazenagem em uma tabela no formato HTML. Esta tabela é, posteriormente, enviada por meio do aplicativo Outlook como corpo do e-mail para um destinatário específico, com o assunto "Previsão de vendas para os próximos 5 dias".

![image](https://user-images.githubusercontent.com/87774019/216482998-7d831905-1c91-480a-82cc-644ff4733a0f.png)
