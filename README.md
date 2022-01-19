# Sakila-Answers---Jonathan-White
Sakila Answers - Jonathan White, got to question 22 & skipped 14
[200~#Sakila QA community challenge Jonathan White
Use sakila;

#1 added an order by to be neat
Select First_name, Last_Name From actor Order By First_name;

#2
Select First_Name, Last_Name From actor Where First_name = 'john';

#3
Select First_name, Last_name From actor Where last_name = 'neeson';

#4
Select actor_id, First_name, Last_name FROM actor Where (actor_id % 10) = 0;

#5
Select Film_id, Title FROM film Where film_id = 100;

#6
Select * FROM film Where rating = 'R';

#7
Select * FROM film Where rating != 'R';

#8
Select * From film where length >= 0 order by length Limit 10;

#9
Select * From film where length = 185 order by film_id;

#10
Select * From film Where special_features = 'deleted scenes';

#11
Select actor_id, first_name, last_name FROM actor group by last_name having actor_id >= 0 order by last_name;

#12
Select last_name, count(last_name) AS frequency FROM actor group by last_name order by frequency DESC;

##with having kinda
Select last_name, count(last_name) AS frequency FROM actor group by last_name having frequency >1 order by frequency DESC;

#13
Select film_actor.actor_id, actor.First_name, actor.Last_name, count(film_actor.actor_id) AS 'frequency' From film_actor  
JOIN actor ON actor.actor_ID = film_actor.actor_id group by film_actor.actor_id order by count(film_actor.actor_id) desc;

#14 Skip & try again later

#15
Select SUM(length) as total From film;

##Think this is it working
Select AVG(length) FROM film where (
	Select SUM(length) FROM film);

	#16
	Select Category.name, AVG(film.length) AS AVGRuntime 
	FROM film Join film_category ON film_category.film_id = film.film_id 
	Join category ON category.category_id = film_category.category_id group by category.name;

	#17
	Select * FROM film Where description LIKE '%robot%';

	#18
	Select Release_year, count(release_year) AS Releases FROM film group by release_year;

	#19
	Select film.title, category.name FROM film Join film_category ON film_category.film_id = film.film_id 
	Join category ON category.category_id = film_category.category_id where category.name = 'horror';

	#20
	Select staff_id, first_name, Last_name FROM staff where staff_id = 2;

	#21
	Select film.title, actor.first_name, actor.last_name FROM actor 
	Join film_actor ON film_actor.actor_id = actor.actor_id
	Join film ON film.film_id = film_actor.film_id Where first_name = 'fred' AND last_name = 'Costner';

	#22
