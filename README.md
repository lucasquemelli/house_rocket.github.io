# house_rocket.github.io
Este é um projeto para maximizar a receita de uma empresa de compra e venda de imóveis. 

A House Rocket é uma plataforma digital que tem como modelo de negócio, a compra e a venda de imóveis usando tecnologia.

Objetivos: encontrar as melhores oportunidades de negócio no mercado de imóveis e maximizar a receita da empresa.

Estratégia: comprar boas casas em ótimas localizações com preços baixos e depois revendê-las posteriormente a preços mais altos. Quanto maior a diferença entre a compra e a venda, maior o lucro da empresa e portanto maior sua receita.

As casas possuem muitos atributos que as tornam mais ou menos atrativas aos compradores. Os vendedores, a localização e o período do ano também influenciam os preços.

O CEO da empresa adotou as seguintes perguntas como principais:

1. Quais casas o CEO da House Rocket deveria comprar e por qual preço de compra?
2. Uma vez a casa em posse da empresa, qual o melhor momento para vendê-las e qual seria o preço da venda?
3. A House Rocket deveria fazer uma reforma para aumentar o preço da venda? Quais seriam as sugestões de mudanças? Qual o incremento no preço dado por cada opção de reforma?

Em seguida, para melhorar a tomada de decisão, o CEO acrescentou as seguintes perguntas:

1. Quantas casas estão disponíveis para compra?
2. Quantos atributos as casas possuem?
3. Quais são os atributos das casas?
4. Qual a casa mais cara (casa com o maior valor de venda)?
5. Qual a casa com o maior número de quartos?
6. Qual a soma total de quartos do conjunto de dados?
7. Quantas casas possuem 2 banheiros?
8. Qual o preço médio de todas as casas no conjunto de dados?
9. Qual o preço médio de casas com 2 banheiros?
10. Qual o preço mínimo entre as casas com 3 quartos?
11. Quantas casas possuem mais de 300 metros quadrados na sala de estar?
12. Quantas casas tem mais de 2 andares?
13. Quantas casas tem vista para o mar?
14. Das casas com vista para o mar, quantas tem 3 quartos?
15. Das casas com mais de 300 metros quadrados de sala de estar, quantas tem mais de 2 banheiros?

# Respostas ao CEO

Para responder as perguntas do CEO, primeiro importamos as bibliotecas:

![image](https://user-images.githubusercontent.com/81119854/129558378-687a3784-febe-49ad-955d-2156964c8051.png)

Em seguida, carregamos o arquivo com o qual vamos trabalhar:

![image](https://user-images.githubusercontent.com/81119854/129560555-b2f37333-2847-4ef2-9c3a-79396489f7e2.png)

Para uma melhor visualização do problema e, assim, para uma melhor resolução, disponibilizo um screenshot do dataframe no LibreOffice:

![image](https://user-images.githubusercontent.com/81119854/129561978-136dd55c-e5c9-410a-be65-ead0903f76a2.png)

1. Quantas casas estão disponíveis para a compra?

O número de casas disponíveis pode ser identificado a partir do número de identificação das casas. Entretanto, os números de identificação podem estar repetidos e, por isso, o código deve identificar apenas valores únicos de 'id'.

![image](https://user-images.githubusercontent.com/81119854/129561105-eac0ad33-456d-49db-9b16-9b12ad17e926.png)

2. Quantos atributos as casas possuem?

Os atributos são as colunas do dataframe, com exceção do número de identificação e da coluna de data.

![image](https://user-images.githubusercontent.com/81119854/129562210-cd9538b0-0d68-47bf-864b-687de2f954ef.png)

3. Quais são os atributos das casas?

Apresentarei duas maneiras de visualizar os atributos das casas. Em ambas as formas, devemos criar um dataframe novo que exclua as coluna 'id' e 'date'. 

A primeira forma é exibindo a primeira linha do dataframe:

![image](https://user-images.githubusercontent.com/81119854/129562866-fe948963-aeab-4b5f-8b93-a32e35928e98.png)
![image](https://user-images.githubusercontent.com/81119854/129562910-3cf2d7f9-2ea6-4b18-8705-a060d1e435c1.png)

A segunda forma é exibindo os atributos em forma de lista:

![image](https://user-images.githubusercontent.com/81119854/129563180-fe4ec58a-9891-4b57-a6f2-78169c401d6f.png)

4. Qual a casa mais cara?

Para identificarmos a casas mais cara, devemos organizar as casas pelos seus respectivos preços (em ordem decrescente) e exibir o primeiro valor do 'id'.

![image](https://user-images.githubusercontent.com/81119854/129573167-e37e462d-645b-4463-a79c-180096c28d8c.png)

![image](https://user-images.githubusercontent.com/81119854/129573264-384da5f3-8f18-4867-9f0d-db2efef48de8.png)

5. Qual a casa com o maior número de quartos?

Podemos identificar a casa com o maior número de quartos ao organizar as casas pelo número de quartos, em ordem decrescente, e exibir o primeiro valor do 'id'.

![image](https://user-images.githubusercontent.com/81119854/129573396-6ee2b9c2-28e1-4e4e-85fa-87a6f516f8c4.png)

![image](https://user-images.githubusercontent.com/81119854/129573663-208457c0-8c1b-48b0-af10-88fe897ff219.png)

6. Qual a soma total de quartos do conjunto de dados?

![image](https://user-images.githubusercontent.com/81119854/129588286-920a68ae-c0ff-429f-96d2-d6717be9e927.png)

7. Quantas casas possuem dois banheiros?

Podemos visualizar o número de casas com seus respectivos números de banheiros:

![image](https://user-images.githubusercontent.com/81119854/129592070-eab0d021-204c-4e1e-8db0-f1de8081a02e.png)

Ou simplesmente podemos exibir o número de casas com dois banheiros. Para tanto, localizamos as linhas em que o número de banheiros é igual a 2 (verificação em todas as colunas). Em seguida, determinamos o tamanho do dataframe com 2 banheiros.

![image](https://user-images.githubusercontent.com/81119854/129592655-b8bb7f4a-a277-4c46-909b-50a61c08697e.png)

8. Qual o preço médio de todas as casas no conjunto de dados?

![image](https://user-images.githubusercontent.com/81119854/129593791-698ee8d7-79f4-4ce5-bde0-0bec530af93b.png)

Geralmente, são adotados 02 dígitos após a vírgula. Por isso, para arredondar, podemos fazer:

![image](https://user-images.githubusercontent.com/81119854/129593941-4f0228df-0aa9-4f63-bf07-fa1b2059b980.png)

9. Qual o preço médio de casas com 02 banheiros?

Devemos identificar as casas com 02 banheiros e calcular a média da coluna de preços para essas casas:

![image](https://user-images.githubusercontent.com/81119854/129595426-358a1672-c9a5-40c2-8798-c956d9b15f48.png)

10. Qual o preço mínimo entre as casas com 03 quartos?

Devemos identificar as casas com 03 quartos e procurar na coluna de preços dessas casas o valor que é mínimo.

![image](https://user-images.githubusercontent.com/81119854/129596216-c02b0e6e-e806-46cf-90f2-04351dd65b19.png)

11. Quantas casas possuem mais de 300 metros quadrados na sala de estar?

Primeiramente, criamos um conjunto de dados para identificar as casas com mais de 300 m² na sala de estar. Depois, contamos a quantidade de itens nesse conjunto de dados.

![image](https://user-images.githubusercontent.com/81119854/129599894-7e573a5a-b298-4422-8514-df26cba46462.png)

Ou podemos calcular de forma mais direta:

![image](https://user-images.githubusercontent.com/81119854/129600257-4edbcf8b-b54b-4b72-8065-232a378b98f3.png)

12. Quantas casas tem mais de 2 andares?

![image](https://user-images.githubusercontent.com/81119854/129604517-24a82d60-01a7-4341-99ee-c216921ebc37.png)

13. Quantas casas tem vista para o mar?

![image](https://user-images.githubusercontent.com/81119854/129604635-d0e962ee-4489-45b5-ac50-028148f4f17c.png)

14. Das casas com vista para o mar, quantas tem 3 quartos?

![image](https://user-images.githubusercontent.com/81119854/129604677-c089bdff-5946-4348-9361-f0f5debef96c.png)

![image](https://user-images.githubusercontent.com/81119854/129605342-9fa86cd8-0b89-4a18-88ca-60b921d30d61.png)

15. Das casas com mais de 300 metros quadrados de sala de estar, quantas tem mais de 2 banheiros?

![image](https://user-images.githubusercontent.com/81119854/129605468-5057da56-6075-43fa-8edf-2690840a3a7f.png)

# Novas perguntas

O CEO passou novas perguntas. As perguntas e as respostas podem ser vistas abaixo:

1. Qual a data do imóvel mais antigo no portfólio?

![image](https://user-images.githubusercontent.com/81119854/129772007-fbf917fc-e989-4b27-8d42-8408cc478296.png)

Com uma busca direcionada:

![image](https://user-images.githubusercontent.com/81119854/129772090-4a5c69b5-abad-4c15-b593-b53190739799.png)

2. Quantos imóveis possuem o número máximo de andares?

![image](https://user-images.githubusercontent.com/81119854/129772466-6e9eceda-f975-4a91-9e14-3cebb13d9338.png)

Podemos ver que 8 imóveis possuem 3.5 andares. 

Podemos solucionar esse problema de uma forma diferente. Primeiramente, exibindo na tela os valores existentes de andares:

![image](https://user-images.githubusercontent.com/81119854/129773560-81132409-920a-4195-9c6e-a6438e7ac04a.png)

Depois, verificando os imóveis que aparecem com valor de 3.5 andares:

![image](https://user-images.githubusercontent.com/81119854/129773605-004e1549-c911-40d3-8ff9-ff281aeb5972.png)

Também podemos selecionar apenas o 'id' e o número de andares 'floors':

![image](https://user-images.githubusercontent.com/81119854/129773964-cd50ab6a-578b-4838-9748-a88db2ccf1a8.png)

