## Film tablosundan 'K' karakteri ile başlayan en uzun ve replacenet_cost u en düşük 4 filmi sıralayınız.
```sql
select 
	title,
	length,
	replacement_cost
from film
where 
	title like 'K%'
order by 
	length desc,
	replacement_cost asc
limit 4;
```

## Film tablosunda içerisinden en fazla sayıda film bulunduran rating kategorisi hangisidir?
```sql
select 
	rating, 
	count(*) as adet 
from film
group by rating 
order by adet desc
limit 1;
```

## Customer tablosunda en çok alışveriş yapan müşterinin adı nedir?
```sql
select distinct
	customer.first_name,
	customer.last_name
from customer
inner join payment on customer.customer_id = payment.customer_id
where 
	customer.customer_id = (select customer_id from payment group by customer_id order by count(*) desc limit 1);
```

## Category tablosundan kategori isimlerini ve kategori başına düşen film sayılarını sıralayınız.
```sql
select category.name, count(*) from film
inner join film_category on film.film_id = film_category.film_id
inner join category on film_category.category_id = category.category_id
group by category.name;
```
## Film tablosunda isminde en az 4 adet 'e' veya 'E' karakteri bulunan kç tane film vardır?
```sql
select count(*) from film where title ilike '%e%e%e%e%';
```
