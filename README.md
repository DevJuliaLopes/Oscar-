#O Oscar vai para?...


Hoje vamos trabalhar com o Oscar.
A ideia de premiar ou ser premiado é para reconhecer:
- Reconhecer uma qualidade
- Reconhecer um atributo
- Reconhecer o esforço... 

Alguns diriam que prêmios são apenas um reconhecimento superficial do nosso trabalho, uma forma de massagear o ego e nos deixar com a sensação de que estamos fazendo algo certo. Outros, no entanto, defendem que os prêmios são uma forma de validação do nosso trabalho, uma prova de que estamos no caminho certo e de que estamos fazendo a diferença.

Prêmios têm sim o seu valor, mas que eles não são o único indicador de sucesso. É claro que é sempre bom ser reconhecido pelo nosso trabalho e ter um troféu ou uma placa para pendurar na parede, mas o mais importante mesmo é a satisfação pessoal que sentimos quando fazemos algo que amamos e que acreditamos ser importante. Então, sim, prêmios importam, mas não devemos deixá-los ser o único fator que determina o nosso sucesso e a nossa felicidade.


<h2> Inicio da Cerimônia </h2>

1- Quantas vezes Natalie Portman foi indicada ao Oscar? 3
 SELECT * FROM movies WHERE `name` Like "%Natalie Portma%";

2- Quantos Oscars Natalie Portman ganhou? 1
 SELECT * FROM movies WHERE `name` Like "%Natalie Portma%" AND winner = 'true';

3- Amy Adams já ganhou algum Oscar? 0\
 SELECT * FROM movies WHERE `name` Like "%Amy Adams%" AND winner = 'true';	

4- A série de filmes Toy Story ganhou um Oscar em quais anos?  2011 E 2020
 SELECT * FROM movies WHERE film LIKE "%Toy Story%" AND winner = 'true';	
 
 5- Quem tem mais Oscars: a categoria "Melhor Ator" ou "Melhor Filme"? Melhor filme
  SELECT count(*) FROM movies WHERE category LIKE "%ACTOR%" AND winner = 'true';
  SELECT count(*) FROM movies WHERE category LIKE "%FILM%" AND winner = 'true';

6- O primeiro Oscar para melhor Atriz foi para quem? Em que ano?Janet Gaynor 1928
  SELECT `name`, year_ceremony, winner FROM movies WHERE category LIKE "%ACTRESS%" AND winner = 'true';

7- Na coluna/campo Winner, altere todos os valores com "True" para 1 e todos os valores "False" para 0.
  UPDATE  movies SET winner = 1 WHERE winner = "True"; 
  UPDATE  movies SET winner = 0 WHERE winner = "False";

8- Em qual edição do Oscar "Crash" ganhou o prêmio principal? 2006, FILM EDITING, BEST PICTURE e WRITING
 SELECT film, year_ceremony,category, winner FROM movies WHERE film LIKE "Crash" AND winner = 1;

9- Bom... dê um Oscar para um filme que merece muito, mas não ganhou.
  INSERT INTO movies (year_film, year_ceremony, ceremony, category, `name`, film, winner) VALUES ('1928', '1929', '2', 'WRITING', 'Bess Meredyth', 'A Woman of Affairs;', 'False');

10 - O filme Central do Brasil aparece no Oscar? Não tem
  SELECT film FROM movies WHERE film LIKE "%Central do Brasil%";

11) Inclua no banco 3 filmes que nunca nem foram nomeados ao Oscar, mas que na sua opinião, merecem.
   INSERT INTO movies (year_film, year_ceremony, ceremony, category, `name`, film, winner) VALUES ('1927', '1928', '1', 'SPECIAL AWARD', 'Charles Chaplin', '', 'True');
   INSERT INTO movies (year_film, year_ceremony, ceremony, category, `name`, film, winner) VALUES ('1928', '1929', '2', 'OUTSTANDING PICTURE', 'Metro-Goldwyn-Mayer', 'The Broadway Melody', 'True');
   INSERT INTO movies (year_film, year_ceremony, ceremony, category, `name`, film, winner) VALUES ('1928', '1929', '2', 'CINEMATOGRAPHY', 'Clyde De Vinna', 'White Shadows in the South Seas', 'True');

12) Crie uma nova categoria de premiação. Qualquer prêmio que você queira dar. Agora vamos dar esses prêmios aos filmes que você cadastrou na questão acima. R: Melhor Romance de época
   UPDATE movies SET category = 'Melhor Romance de época' WHERE category = 'film'; 

13) Qual foi o primeiro ano a ter um prêmio do Oscar? 1928
   SELECT year_ceremony FROM movies
 
14) Pensando no ano em que você nasceu: Qual foi o Oscar de melhor filme, Melhor Atriz e Melhor Diretor? 'Pirates of the Caribbean: The Curse of the Black Pearl', 'ACTOR IN A LEADING ROLE', '2004', '76'
    SELECT film, category, year_ceremony, ceremony FROM movies WHERE year_ceremony = "2004";

