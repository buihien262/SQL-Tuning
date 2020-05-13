# Bùi Thị Thu Hiền - Bài tập buổi 1
Phần 1: Từ các kết quả EXPLAIN ANALYZE, viết lệnh SQL tương ứng.
Câu 1: 
Select actor_id, first_name, last_name, last_update
From actor
Câu 2:
Select first_name, last_name
From actor
Where actor.first_name = 'Nick'
Câu 3:
Select actor_id, first_name, last_name, last_update
From actor
Where actor.actor_id = 100
Order by actor.first_name, actor.last_name
Câu 4: 
Select rating, count(film_id)
From film
Where film.length > 100
Group by film.rating
Order by film.rating DESC
Câu 5: 
Select city.city, country.country
From city Inner Join country
          On city.country_id = country.country_id
Câu 6:
Select film.title, film.description, film.rating, film.length, 
  (Select avg(rating_avg.length) 
   From film rating_avg
   Group by rating_avg.rating
   Having film.rating = rating_avg.rating)
From film
Order by film.rating
