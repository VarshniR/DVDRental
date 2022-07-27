## Varshni's Portfolio

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
