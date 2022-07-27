##Varshni's Portfolio
### DVD Rental Database

In this project, I have queried the DVD Rental database. The Database holds information about a company that rents movie DVDs. For this project, I have queried the database to gain an understanding of the customer base, such as what the patterns in movie watching are across different customer groups, how they compare on payment earnings, and how the stores compare in their performance.


-- Q1. We want to send out a promotional email to all our existing customers. 
```markdown 
SELECT first_name, last_name,email FROM customer;
```
-- Q2. We want to know the distinct rating types in our database
```markdown 
SELECT DISTINCT rating FROM film;
```
-- Q3. Find out how many transactions were greater than $5.00
```markdown 
SELECT COUNT(*)amount FROM payment
WHERE amount >5.00;
```
-- Q4. How many actors have a first name that starts with a letter P?
```markdown
SELECT COUNT(*)first_name FROM actor
WHERE first_name LIKE 'P%';
```
-- Q5. How many unique districts are our customers from?
```markdown
SELECT COUNT(DISTINCT(district)) FROM address;
```
-- Q6. How many films have a rating of R and a replacement cost between $5 and $15?
```markdown
SELECT COUNT(*) FROM film
WHERE rating = 'R' 
AND replacement_cost BETWEEN 5.00 AND 15.00;
```
-- Q7. How many films have the word Truman somewhere in the title?
```markdown
SELECT COUNT(*) FROM film 
WHERE title LIKE '%Truman%';
```
-- Q8. We are launching a platinum service for our most loyal customers. We will assign platinum status to customers that had 40 or more transaction payments.What customer_ids are eligible for platinum status?
```markdown
SELECT customer_id, COUNT(*) FROM payment
GROUP BY customer_id
HAVING COUNT(*)>= 40;
```
-- Q9. What are the customer ids of customers who have spent more than $100 in payment transactions with our staff_id member 2?
```markdown
SELECT customer_id, sum(amount) FROM payment
WHERE staff_id= 2
GROUP BY customer_id
HAVING SUM(amount)>100;
```
-- Q10. What customer has the highest customer ID number whose name starts with an 'E' and has an address ID lower than 500?
```markdown
SELECT first_name, last_name FROM customer
WHERE first_name LIKE 'E%'
AND address_id < 500
ORDER BY customer_id DESC
LIMIT 1;
```
-- Q11. California sales tax laws have changed and we need to alert our customers to this through email. What are the emails of the customers who live in California?
```markdown
SELECT address.district, customer.email FROM address
INNER JOIN CUSTOMER
ON address.address_id = customer.customer_id
where district = 'California';
```
-- Q12. A customer is a huge fan of the actor Nick Wahlberg and wants to know which movies he is in. Get a list of all the movies 'Nick Wahlberg' has been in.
```markdown
SELECT  first_name, last_name,title FROM film_actor
INNER JOIN actor
ON film_actor.actor_id = actor.actor_id
INNER JOIN film
ON film_actor.film_id= film.film_id
WHERE first_name = 'Nick' AND last_name = 'Wahlberg';
```
-- Q13. Find out which movies are NOT in the inventory at the moment at any of the stores.
```markdown
SELECT film.film_id, title, inventory_id, store_id FROM film
LEFT OUTER JOIN inventory
ON inventory.film_id= film.film_id
WHERE inventory.film_id IS NULL; 
```
-- Q14. During which months did payments occur?
```markdown
SELECT DISTINCT(TO_CHAR(payment_date, 'MONTH')) FROM payment;
```
-- Q15. How many payments occured on a Monday?
```markdown
SELECT COUNT(*) FROM payment
WHERE EXTRACT(dow FROM payment_date)=1;
```
-- Q16. Find out which films have a rental rate that is higher than the average rental rate?
```markdown
SELECT titlte, rental_rate FROM film
WHERE rental_rate > 
(SELECT AVG(rental_rate) FROM film;
```
-- Q17. Find the film titles that have been returned between May 29, 2005 and May 30, 2005. 
```markdown 
SELECT film_id, title FROM title
WHERE film_id IN 
(SELECT inventory.film_id FROM rental
INNER JOIN inventory
ON inventory.inventory_id = rental.inventory_id
WHERE return_date BETWEEN '2005-05-29' AND '2005-05-30')
ORDER BY film_id
```








# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/VarshniR/Test/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
