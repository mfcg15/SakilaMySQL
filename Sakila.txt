SELECT customers.first_name as Nombre, customers.last_name as Apellido, customers.email as Email, addresses.address as Direccion,cities.city as Ciudad , countries.country as Pais FROM customers 
inner join addresses on customers.address_id = addresses.id 
inner join cities on cities.id = addresses.city_id 
inner join countries on cities.country_id = countries.id 
where addresses.city_id = 312;

SELECT films.title as Pelicula , films.description as Descripcion, films.release_year as Año ,films.rating as Clasificacion, categories.name as Categoria, films.special_features as Caracteristicas_Especiales FROM films_categories 
inner join categories on films_categories.category_id = categories.id 
inner join films on films.id = films_categories.film_id 
where categories.name = 'Comedy';

SELECT actors.id, concat(actors.first_name,' ',actors.last_name) as Actor , films.title as Pelicula, films.description as Descripcion, films.release_year as Año FROM films_actors 
inner join actors on actors.id = films_actors.actor_id 
inner join films on films.id = films_actors.film_id 
where actor_id = 5;

SELECT customers.first_name as Nombre, customers.last_name as Apellido, customers.email as Correo, addresses.address as Direccion FROM customers 
inner join addresses on customers.address_id = addresses.id 
inner join cities on cities.id = addresses.city_id 
where customers.store_id = 1 
and (cities.id = 1 or cities.id = 42 or cities.id = 312 or cities.id = 459);

SELECT films.title as Pelicula, films.description as Descripcion,films.release_year as Año,films.rating as Clasificacion,films.special_features as Caracteristica_Especial FROM films_actors 
inner join actors on actors.id = films_actors.actor_id 
inner join films on films.id = films_actors.film_id 
where films_actors.actor_id = 15 and films.rating = 'G' and films.special_features Like '%Behind the Scenes%';

SELECT films_actors.film_id, films.title as Titulo, films_actors.actor_id, concat(actors.first_name,' ', actors.last_name) as Actor FROM films_actors 
inner join actors on actors.id = films_actors.actor_id 
inner join films on films.id = films_actors.film_id 
where films_actors.film_id = 369;

SELECT films.title as Pelicula, films.description as Descripcion, films.release_year as Año, films.rating as Clasificacion, films.special_features as Caracteristica_Especial, categories.name as Categoria FROM films_categories 
inner join categories on films_categories.category_id = categories.id 
inner join films on films.id = films_categories.film_id 
where categories.name = 'Drama' and films.rental_rate = 2.99;

SELECT films.title as Pelicula, films.description as Descripcion, films.release_year as Año, films.rating as Clasificacion, films.special_features as Caracteristicas_Especiales, categories.name as Categoria, concat(actors.first_name, ' ',actors.last_name) as Actor FROM films_categories 
inner join categories on films_categories.category_id = categories.id 
inner join films on films.id = films_categories.film_id 
inner join films_actors on films_actors.film_id = films.id 
inner join actors on actors.id = films_actors.actor_id
where categories.name = 'Action' and actors.first_name = 'Sandra' and actors.last_name = 'Kilmer';