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
