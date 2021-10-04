- [x] Sort by text
- [x] Sort by numbers
- [x] Sort by descending
- [x] Sort by multiple columns


### What are the first 5 values in reverse alphabetical order in the country column from the country table?

``` 
select country
from dvd_rentals.country
order by country DESC
limit 5;
```

### Which category had the lowest total_sales value according to the sales_by_film_category table? What was the total_sales value?

```
select category, total_sales
from dvd_rentals.sales_by_film_category
order by total_sales
limit 1;
```

### What was the latest payment_date of all dvd rentals in the payment table?

```
select payment_date from dvd_rentals.payment
order by payment_date DESC
limit 1;
```

### Which customer_id had the latest rental_date for inventory_id = 1 and 2?

```
select customer_id, inventory_id, rental_date
from dvd_rentals.rental
order by inventory_id, rental_date DESC
limit 10
```

### Exercises

### What is the name of the category with the highest category_id in the dvd_rentals.category table?

```
select name, category_id
from dvd_rentals.category
order by category_id DESC
limit 10
```


### For the films with the longest length, what is the title of the “R” rated film with the lowest replacement_cost in dvd_rentals.film table?

** find the longest length first and then lowest replacement cost (sorting order affects the rows)

```
select title, length, replacement_cost, rating
from dvd_rentals.film
order by length DESC, replacement_cost
limit 10
```

### Who was the manager of the store with the highest total_sales in the dvd_rentals.sales_by_store table?

```
select manager, total_sales
from dvd_rentals.sales_by_store
order by total_sales DESC
limit 10
```

### What is the postal_code of the city with the 5th highest city_id in the dvd_rentals.address table?

```
select postal_code, city_id
from dvd_rentals.address
order by city_id DESC 
limit 10
```
