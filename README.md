1- Quantas vezes Natalie Portman foi indicada ao Oscar?
select count(*) from indicados_ao_oscar where nome_do_indicado = 'Natalie Portman';

2- Quantos Oscars Natalie Portman ganhou?
select count(*) from indicados_ao_oscar where nome_do_indicado = 'Natalie Portman' and vencedor = 'sim';

3- Amy Adams já ganhou algum Oscar?
select count(*) from indicados_ao_oscar where nome_do_indicado = 'Amy Adams' and vencedor = 'sim';

4- A série de filmes Toy Story ganhou um Oscar em quais anos? 
select nome_do_filme, ano_cerimonia from indicados_ao_oscar where nome_do_filme like '%Toy Story%' and vencedor = 'sim';

5- A partir de que ano que a categoria "Actress" deixa de existir? 
SELECT MAX(ano_cerimonia)
FROM indicados_ao_oscar 
WHERE categoria = "Actress";

6- O primeiro Oscar para melhor Atriz foi para quem? Em que ano?

nome_do_indicado, ano_cerimonia FROM indicados_ao_oscar where categoria = 'Actress' and vencedor = 'sim' limit 1;

7- Na coluna/campo "Vencedor", altere todos os valores com "Sim" para 1 e todos os valores "Não" para 0.
UPDATE indicados_ao_oscar
SET vencedor = 0 
WHERE vencedor = "não";
SET vencedor = 1
WHERE vencedor = "sim";

8- Em qual edição do Oscar "Crash" concorreu ao Oscar?
SELECT ano_cerimonia FROM indicados_ao_oscar WHERE nome_do_filme = "Crash";

9- Bom... dê um Oscar para um filme que merece muito, mas não ganhou.
INSERT INTO indicados_ao_oscar (
 ano_filmagem, 
 cerimonia,
 categoria,
 ano_cerimonia,
 nome_do_filme,
 vencedor) 
VALUES (2010, 2011, "Filme bom" , 2011,  "Gente Grande", "sim");


10- O filme Central do Brasil aparece no Oscar?

SELECT nome_do_filme FROM indicados_ao_oscar where nome_do_filme = 'Central do Brasil';

11- Inclua no banco 3 filmes que nunca foram nem nomeados ao Oscar, mas que merecem ser. 
INSERT INTO indicados_ao_oscar (
 ano_filmagem, 
 cerimonia,
 categoria,
 ano_cerimonia,
 nome_do_filme,
 vencedor) 
VALUES (2018, 2019, "Anime" , 2019,  "Dragon ball Super Broly", "sim");
VALUES (2023, 2024, "Anime" , 2024,  "Black Clover", "sim");
VALUES (2024, 2025, "Anime" , 2025,  "Haikyuu", "sim");

14 - Pensando no ano em que você nasceu: Qual foi o Oscar de melhor filme, Melhor Atriz e Melhor Diretor?

SELECT nome_do_indicado, categoria, ano_filmagem FROM indicados_ao_oscar WHERE ano_cerimonia = '2003' and vencedor ='sim'and (categoria = 'DIRECTING' or categoria = 'ACTRESS' or categoria= "")
