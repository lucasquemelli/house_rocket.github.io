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

# Perguntas e pedidos 1.0

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

# Perguntas e pedidos 2.0

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

Ou podemos exibir o número de linhas e de colunas para os imóveis com 3.5 andares:

![image](https://user-images.githubusercontent.com/81119854/129774319-fdb59dbf-a141-47a1-81a6-e6a0fd61f7fc.png)

3. Criar uma classificação para os imóveis, separando-os em baixo e alto padrão, de acordo com o preço.

Acima de $540000,00 -> alto padrão
Abaixo de $540000,00 -> baixo padrão

Primeiro passo: criar uma coluna de níveis, cujo nome será 'level'.

![image](https://user-images.githubusercontent.com/81119854/129778437-09268a6f-b035-4c4a-a692-6c86bc6a25fb.png)

Segundo passo: atribuir valores de baixo e alto padrão. Consideramos 'high_standard' como alto padrão e 'low_standard' como baixo padrão.

![image](https://user-images.githubusercontent.com/81119854/129778573-91dc8c65-83af-4b1d-8c95-2ccd2dc48ada.png)

4. Relatório ordenado por preço e contendo as seguintes informações:

- id do imóvel
- data que o imóvel ficou disponível para compra
- número de quartos
- tamanho total do terreno
- preço
- classificação do imóvel

![image](https://user-images.githubusercontent.com/81119854/129782384-2397a96f-ec0c-4ea0-ad9f-29fd653e6031.png)

Para entregar o relatório, é interessante que este esteja em um arquivo csv. Para tanto, podemos fazer:

![image](https://user-images.githubusercontent.com/81119854/129783206-5a2803be-b01b-4cc5-9655-6d33015b4502.png)

5. Um mapa indicando onde as casas estão localizadas geograficamente.

![image](https://user-images.githubusercontent.com/81119854/129787022-1ff6bdbd-dbdf-4337-8d3b-45e52c530fac.png)

![image](https://user-images.githubusercontent.com/81119854/129787072-97047ba9-df12-4737-a046-2428fc93d3b3.png)
![image](https://user-images.githubusercontent.com/81119854/129787116-49cf74fa-390c-4a56-9bbc-0e99819d55b7.png)

Zoom:

![image](https://user-images.githubusercontent.com/81119854/129787292-72e40fbf-5bcd-4011-be1b-f0b1397afa5e.png)

Zoom:

![image](https://user-images.githubusercontent.com/81119854/129787372-61f20a33-677c-4d64-8ed2-d86a80f90271.png)

Localizando um imóvel:

![image](https://user-images.githubusercontent.com/81119854/129787583-d9ab8a48-6029-42ef-ba5c-c50f819fb729.png)

Para apresentar para o CEO, o ideal é que o mapa possa ser acessado no browser. Assim, é importante salvar o mapa em um arquivo html:

![image](https://user-images.githubusercontent.com/81119854/129788074-9691adac-edb4-4126-a1ca-d032b864b0fe.png)

[Mapa de imóveis da empresa House Rocket](http://localhost:8888/view/Desktop/mapa_house_rocket.html)

# Perguntas e pedidos 3.0

O CEO passou novas perguntas. As perguntas e as respostas podem ser vistas abaixo.

![image](https://user-images.githubusercontent.com/81119854/130084941-9cce17f8-2778-4f63-825f-06f8311b7ed7.png)

A coluna data está no formato 'object':

![image](https://user-images.githubusercontent.com/81119854/130085014-c7717266-ce00-47cd-bdf7-61128c84bdce.png)

Conversão da coluna data para o tipo 'datetime'. 

![image](https://user-images.githubusercontent.com/81119854/130085062-c559da08-ebda-48dc-ae61-36af56bfe023.png)

1. Crie uma nova coluna chamada: “house_age”

• Se o valor da coluna “date” for maior que 2014-01-01 => ‘new_house’

• Se o valor da coluna “date” for menor que 2014-01-01 => ‘old_house’

![image](https://user-images.githubusercontent.com/81119854/130085828-2de2d082-7525-43a8-84b8-cce9bec3f093.png)

2. Crie uma nova coluna chamada: “dormitory_type”
 
• Se o valor da coluna “bedrooms” for igual à 1 => ‘studio’

• Se o valor da coluna “bedrooms” for igual a 2 => ‘apartament’

• Se o valor da coluna “bedrooms” for maior que 2 => ‘house’

![image](https://user-images.githubusercontent.com/81119854/130086137-e6fac3b6-fd41-435a-93db-d3955519d8b3.png)

- Outra forma de responder é:

![image](https://user-images.githubusercontent.com/81119854/130108156-1d384988-ac91-443c-9967-ce7aa909da51.png)

![image](https://user-images.githubusercontent.com/81119854/130108211-d01740ce-7a18-4028-acc1-51e9d6faa8ca.png)

3. Crie uma nova coluna chamada: “condition_type”

- Se o valor da coluna “condition” for menor ou igual à 2 => ‘bad’

- Se o valor da coluna “condition” for igual à 3 ou 4 => ‘regular’

- Se o valor da coluna “condition” for igual à 5 => ‘good’

![image](https://user-images.githubusercontent.com/81119854/130087848-5b149f45-53ef-48c0-b5a4-ae4f2be1be1e.png)

- Outra forma de resolver pode ser:

![image](https://user-images.githubusercontent.com/81119854/130111172-be9c2ad5-fb03-4fde-804f-c99e2201dcff.png)

4. Modifique o TIPO da Coluna “condition” para STRING.

O tipo da coluna "condition" é inteiro:

![image](https://user-images.githubusercontent.com/81119854/130111658-7e70efb8-0a7e-4728-98fc-bd8783cf797f.png)

Para alterar, fazemos:

![image](https://user-images.githubusercontent.com/81119854/130112356-e2de2a5b-9a69-4388-8e24-b869c4d32cd6.png)

Note que o tipo string apareceu apenas como 'O'. Para aparecer 'object', pedimos para exibir o tipo de mais uma coluna, por exemplo:

![image](https://user-images.githubusercontent.com/81119854/130112578-8b6adcc0-0e57-47aa-abbc-332f9741404e.png)

5. Delete as colunas: “sqft_living15” e “sqft_lot15”.

![image](https://user-images.githubusercontent.com/81119854/130123747-7ea24907-df27-445c-ae14-d37bc045e07a.png)

Outra forma de resolver é:

![image](https://user-images.githubusercontent.com/81119854/130123884-dcbe0bc5-c752-4e83-a416-dfcf33530fd1.png)

6. Modifique o TIPO a Coluna “yr_built” para DATE.

![image](https://user-images.githubusercontent.com/81119854/130124955-f14e61f3-e44f-4049-b067-1a14b293cb33.png)

7. Modifique o TIPO a Coluna “yr_renovated” para DATE.

![image](https://user-images.githubusercontent.com/81119854/130126608-d63aec2d-2b0f-40ad-a699-a39f2ff9fe31.png)

8. Qual a data mais antiga de construção de um imóvel?

![image](https://user-images.githubusercontent.com/81119854/130128934-7e1f43d8-c864-419c-a189-a0eef2c3dc01.png)

9. Qual a data mais antiga de renovação de um imóvel?

![image](https://user-images.githubusercontent.com/81119854/130129624-f91ac6b2-cc95-4ec1-8bbc-6545f75589e5.png)

10. Quantos imóveis tem 2 andares?

![image](https://user-images.githubusercontent.com/81119854/130144929-739fae4c-b8c4-4a05-a274-b4e971565da2.png)

11. Quantos imóveis estão com a condição igual a “regular”?

![image](https://user-images.githubusercontent.com/81119854/130145393-d9cf48db-a82c-41f8-9b45-e85799ec1bf8.png)

12. Quantos imóveis estão com a condição igual a “bad” e possuem “vista para água”?

![image](https://user-images.githubusercontent.com/81119854/130146180-d815cad3-ae61-40de-9de1-573b3f5c79b7.png)

13. Quantos imóveis estão com a condição igual a “good” e são “new_house”?

![image](https://user-images.githubusercontent.com/81119854/130146694-1b67213e-b9db-41f5-8d09-6fba876505fc.png)

14. Qual o valor do imóvel mais caro do tipo “studio”?

![image](https://user-images.githubusercontent.com/81119854/130147369-54c2df5e-1d5c-439b-bb54-75a901a77c19.png)

15. Quantos imóveis do tipo “apartment” foram reformados em 2015?

![image](https://user-images.githubusercontent.com/81119854/130148005-ec2b4722-8cbc-491e-8431-a1a060be4f6c.png)

16. Qual o maior número de quartos que um imóvel do tipo “house” possui?

![image](https://user-images.githubusercontent.com/81119854/130148506-76a5758e-97f3-41e8-8a36-5738423f5e03.png)

17. Quantos imóveis “new_house” foram reformados no ano de 2014?

![image](https://user-images.githubusercontent.com/81119854/130148995-8bd6af0a-c363-445b-a27c-d797b41d9f3d.png)

18. Selecione as colunas: “id”, “date”, “price”, “floors”, “zipcode” pelo método:

- Direto pelo nome das colunas

- Pelos índices

- Pelos índices das linhas e o nome das colunas

- Índices Booleanos

![image](https://user-images.githubusercontent.com/81119854/130149931-e3c1784c-cb19-4df8-8148-42a4b3af97d8.png)

![image](https://user-images.githubusercontent.com/81119854/130149995-188ad575-377c-4876-a397-8073645fbb18.png)

![image](https://user-images.githubusercontent.com/81119854/130150160-ebd25665-85da-40fd-a99c-45699e684627.png)

![image](https://user-images.githubusercontent.com/81119854/130150804-7e169c93-3c84-4b51-9d5e-c667ffcb0519.png)

19. Salve um arquivo .csv com somente as colunas do item 10 ao 17.

![image](https://user-images.githubusercontent.com/81119854/130151751-0bc40189-f7a0-4a6a-bb8d-b3604d530cd8.png)

# Perguntas e pedidos 4.0

![image](https://user-images.githubusercontent.com/81119854/130327545-e562c205-c991-4ccf-bec7-f87543159756.png)

1. Qual o número de imóveis por ano de construção?

![image](https://user-images.githubusercontent.com/81119854/130328000-f0246eee-6725-4cc1-a0dc-297d598eca24.png)

2. Qual o menor número de quartos por ano de construção?

![image](https://user-images.githubusercontent.com/81119854/130330486-95ea7461-8a72-44f6-b345-da541b472b7c.png)

3. Qual o preço de compra mais alto por cada número de quarto?

![image](https://user-images.githubusercontent.com/81119854/130330703-7a310e9c-2a2a-4ef7-a5a7-833297f7340c.png)

4. Qual a soma de todos os preços de compra por número de quarto?

![image](https://user-images.githubusercontent.com/81119854/130330927-c9f5245d-d709-44aa-8b30-981ca15d060d.png)

A segunda hashtag acima está errada. O correto é "selecionar a soma de preços por número de quartos". O mesmo resultado por ser visto abaixo, porém sem a notação científica:

![image](https://user-images.githubusercontent.com/81119854/130330983-62ce1253-2e35-4c01-82d8-4807ba983c67.png)
![image](https://user-images.githubusercontent.com/81119854/130330990-cfed3c14-633c-4c95-8ae3-c9ed71e314eb.png)

5. Qual a soma de todos os preços de compra por número de quartos e banheiros?

![image](https://user-images.githubusercontent.com/81119854/130331162-7ae51828-e4d6-4e17-b561-ce5eb15c8952.png)

6. Qual o tamanho médio das salas dos imóveis por ano de construção? 

![image](https://user-images.githubusercontent.com/81119854/130331435-939b4683-8116-4088-841d-5ca6a985e165.png)

7. Qual o tamanho mediano das salas dos imóveis por ano de construção?

![image](https://user-images.githubusercontent.com/81119854/130331508-06d08485-b47b-4d46-8adf-b366f089f396.png)

8. Qual o desvio padrão do tamanho das salas dos imóveis por ano de construção?

![image](https://user-images.githubusercontent.com/81119854/130331626-fd49a9e3-27c4-428b-9d77-70c383264184.png)

9. Como é o crescimento total de preços de compras dos imóveis, por ano, por dia e pela semana do ano?

A coluna de datas está como tipo objeto:

![image](https://user-images.githubusercontent.com/81119854/130331728-d0fcca69-2bcb-420e-aab4-a2fd7f6020fd.png)

Para realizar as operações, é necessário convertê-la para o tipo data. 

![image](https://user-images.githubusercontent.com/81119854/130331786-a4c8c6e8-7b24-4671-9273-6bfa02935fa2.png)

Se observarmos o dataframe, veremos que o formato do campo 'date' foi alterado, porém ainda não exibe apenas o ano:

![image](https://user-images.githubusercontent.com/81119854/130331842-432fde3e-dab3-4ccf-b241-4256ab408eb2.png)

Para exibir apenas o ano, usamos o código:

![image](https://user-images.githubusercontent.com/81119854/130331884-5fec2fa7-4803-4b86-8a89-3f264f357b51.png)

O conjunto de dados:

![image](https://user-images.githubusercontent.com/81119854/130332005-0ad2da09-40d3-4d23-a68c-eebdba066e59.png)

Contudo, para fazer um gráfico, precisamos resetar o index:

![image](https://user-images.githubusercontent.com/81119854/130332024-493d5158-dfd2-4627-959f-e6de9100c856.png)

Para plotar, então, fazemos:

![image](https://user-images.githubusercontent.com/81119854/130332398-f6bed52e-764c-4564-9f3b-c3309faecc4c.png)

![image](https://user-images.githubusercontent.com/81119854/130332185-34b4c282-4c0e-4299-a61c-5e4c1b060f2e.png)

Se quisermos aumentar:

![image](https://user-images.githubusercontent.com/81119854/130332289-64e9e663-7840-46f5-9ef8-c91d3491f6ab.png)

![image](https://user-images.githubusercontent.com/81119854/130332298-bbeb0cb0-8682-4bd9-ae04-d44680058507.png)

![image](https://user-images.githubusercontent.com/81119854/130332415-88d9f16c-2209-47a2-b466-4ae3af5c7909.png)

![image](https://user-images.githubusercontent.com/81119854/130332796-a7ae3cc2-b6db-407c-bad7-d9772f749e1c.png)

![image](https://user-images.githubusercontent.com/81119854/130332717-7f8a54de-cd79-484c-a4cb-e6158413dfcf.png)

![image](https://user-images.githubusercontent.com/81119854/130332836-cadad63f-1056-4c7a-a301-d2f4398408c6.png)

![image](https://user-images.githubusercontent.com/81119854/130333037-742bbd0a-782e-4c83-9c95-6e9837472135.png)

![image](https://user-images.githubusercontent.com/81119854/130333042-a93c3338-6ad6-404b-beb9-9b2d199d7f59.png)

![image](https://user-images.githubusercontent.com/81119854/130333110-3cf872c6-09c4-4f92-8bfe-876104fd8b47.png)

![image](https://user-images.githubusercontent.com/81119854/130333117-bfd78369-69bb-4b4d-9dd1-d3580aa4686b.png)

![image](https://user-images.githubusercontent.com/81119854/130334083-bdf809c9-d42c-44f1-90b5-e0ae335056f7.png)

![image](https://user-images.githubusercontent.com/81119854/130334126-e3ac6289-ad9f-41fb-879a-499a11701ee2.png)

![image](https://user-images.githubusercontent.com/81119854/130334142-e81b7489-340c-44c6-91c0-26dc99bdf49f.png)

10. Um mapa que seja possível identificar as casas com maior preço.

![image](https://user-images.githubusercontent.com/81119854/130336391-d38b76fb-c88d-499a-9f50-5a8c8148e400.png)

![image](https://user-images.githubusercontent.com/81119854/130336393-3d719441-93ff-49bf-81aa-40de86fa3e2e.png)

![image](https://user-images.githubusercontent.com/81119854/130336401-e1a98874-14e1-4c26-9fbc-4ff778adc390.png)

- Salvando em html para criar link de acesso:

![image](https://user-images.githubusercontent.com/81119854/130336461-2a528914-1c2a-4982-84bb-0fd6dbfe03fb.png)

[Mapa para identificar casas com maior preço.](http://localhost:8888/view/Desktop/fig_house_rocket.html)

# Perguntas e pedidos 5.0

1. Crie uma nova coluna chamada: “dormitory_type”.

• Se o valor da coluna “bedrooms” for igual a 1 => ‘studio’.
• Se o valor da coluna “bedrooms” for igual a 2 => ‘apartament’.
• Se o valor da coluna “bedrooms” for maior que 2 => ‘house’.

![image](https://user-images.githubusercontent.com/81119854/130656689-55edb7e5-eab4-4767-9600-7687f989a855.png)

2. Faça um gráfico de barras que represente a soma dos preços pelo número de quartos.

Podemos visualizar o conjunto de dados a ser plotado:

![image](https://user-images.githubusercontent.com/81119854/130661167-62889251-e35b-4312-be82-55cbfe5582d5.png)

Note que o valor da soma total para os preços de apartamentos com 3 e 4 quartos é muito maior do que para os outros quartos. Esse dado sugere que há muito mais apartamentos disponíveis com esses números de quartos. Essa discrepância pode ser vista no gráfico de barras:

![image](https://user-images.githubusercontent.com/81119854/130661728-87887802-ff8a-4349-a640-d03f3e42500f.png)
![image](https://user-images.githubusercontent.com/81119854/130661763-fcccd6cb-79a4-4dfd-9156-dcb63fa18f32.png)

Também podemos construir um gráfico de barras com outra biblioteca:

![image](https://user-images.githubusercontent.com/81119854/130662753-3678ac83-512a-4818-8b8d-6fad75775ffe.png)
![image](https://user-images.githubusercontent.com/81119854/130662801-4bbe4713-8c8d-4d4d-aae3-a2557afbeb51.png)

3. Faça um gráfico de linhas que represente a média dos preços pelo ano construção dos imóveis.

![image](https://user-images.githubusercontent.com/81119854/130681791-b02cd76d-be04-4ae4-8eeb-df85e98ad9d0.png)
![image](https://user-images.githubusercontent.com/81119854/130681834-8d1998a1-6695-45e8-a36b-f4b868d315ed.png)

Com outra biblioteca:

![image](https://user-images.githubusercontent.com/81119854/130682242-8de652b6-65cd-4c2b-a444-b1f850cee5e2.png)
![image](https://user-images.githubusercontent.com/81119854/130682282-c4b8bec8-3cad-448d-891f-8db450d9f7cc.png)

4. Faça um gráfico de barras que represente a média dos preços pelo tipo dos dormitórios.

Para resolver este problema, primeiro precisamos ver que na questão 1, a forma de classificação de dormitórios resultou em linhas do tipo 'NA'.

![image](https://user-images.githubusercontent.com/81119854/130683386-b5a651c3-d8c8-4413-9f2a-00bc2dd1248c.png)

Podemos fazer uma nova classificação que não inclua esses componentes:

![image](https://user-images.githubusercontent.com/81119854/130683650-d93bd530-7dee-4be9-87fb-0d4d56855093.png)

Agora podemos plotar o gráfico:
