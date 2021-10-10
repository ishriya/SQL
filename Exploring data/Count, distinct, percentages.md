- [x] Count records
- [x] Distinct
- [x] Group by counts

## How many rows are there in the film_list table?

```
select
  count(*) as row_count
from
  dvd_rentals.film_list
```

## What are the unique values for the rating column in the film table?

```
select
  distinct rating
from
  dvd_rentals.film_list
```  

## How many unique category values are there in the film_list table?

```
select
  count(DISTINCT category) as unique_categories
from
  dvd_rentals.film_list
```

## What is the frequency of values in the rating column in the film_list table?

```
select rating,count(*) as frequency from dvd_rentals.film_list
group by rating
```

```
select rating,count(*) as frequency, round(100 * count(*)::numeric/sum(count(*)) over (), 2) as percentage from dvd_rentals.film_list
group by rating
order by frequency desc
```
>> ::numeric --> used numeric to avoid integer floor division

## What are the 5 most frequent rating and category combinations in the film_list table?

```
select rating, category, count(*) as frequency
from dvd_rentals.film_list
group by rating, category
order by frequency desc
```

### Exercises

## Which actor_id has the most number of unique film_id records in the dvd_rentals.film_actor table?

```
select actor_id, count(DISTINCT film_id) as films
from dvd_rentals.film_actor
group by actor_id
order by films desc
limit 5;
```

## How many distinct fid values are there for the 3rd most common price value in the dvd_rentals.nicer_but_slower_film_list table?

```
select price,count(distinct fid) as fid_count
from dvd_rentals.nicer_but_slower_film_list
group by price
order by fid_count desc
limit 10
```

## What percentage of overall total_sales does the Sports category make up in the dvd_rentals.sales_by_film_category table?

``` 
select category, 
round(100*total_sales::numeric/sum(total_sales) over (),2) as percentage 
from dvd_rentals.sales_by_film_category
```

## What percentage of unique fid values are in the Children category in the dvd_rentals.film_list table?

```
select category, count(distinct fid) as fid_count, 
round(100* count(distinct fid)::numeric/sum(count(distinct fid)) over (),2) as percentage 
from dvd_rentals.film_list
group by category
```
