## 1. Film tablosunda film uzunluğu length sütununda gösterilmektedir. Uzunluğu ortalama film uzunluğundan fazla kaç tane film vardır?
```sql
select count(*) from film where length > (select avg(length) from film);
```

## 2. Film tablosunda en yüksek rental_rate değerine sahip kaç tane film vardır?
```sql
select count(*) from film where rental_rate = (select max(rental_rate) from film);
```

## 3. Film tablosunda en düşük rental_rate ve en düşün replacement_cost değerlerine sahip filmleri sıralayınız.
```sql
select * from film where rental_rate = (select min(rental_rate) from film) and replacement_cost = (select min(replacement_cost) from film);
```

## 4. Payment tablosunda en fazla sayıda alışveriş yapan müşterileri(customer) sıralayınız.
```sql
select
	customer.customer_id,
	customer.first_name,
	customer.last_name,
	count(payment.payment_id) as total
from
	customer
inner join
	payment on payment.customer_id = customer.customer_id
group by
	customer.customer_id
order by total desc;
```
