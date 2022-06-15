# Case Study #1 - Danny's Diner

![DannysDinerImage](https://user-images.githubusercontent.com/103615594/173914640-19dc3b14-5389-4fc7-b0c9-4b2954fc568c.png)

Details about the case study can be found [here](https://8weeksqlchallenge.com/case-study-1/).

## Business Requirement

Danny wants to use data to get insights about his customers, especially about their visiting patterns, how much money they’ve spent and also which menu items are their favourite.

## Entity Relationship Diagram

![ETR](https://user-images.githubusercontent.com/103615594/173915575-b502fa8a-00e7-4fcf-b69c-f2cf7c5a4f56.jpeg)

## Case Study Questions and Answers

### Q1. What is the total amount each customer spent at the restaurant?
```SQL
SELECT
  sales.customer_id,
  SUM(menu.price) AS total_sales
FROM dannys_diner.sales
INNER JOIN dannys_diner.menu
USING(product_id)
GROUP BY
  sales.customer_id
ORDER BY
  total_sales DESC;
  ```



### Q2. How many days has each customer visited the restaurant?
```SQL
SELECT
  customer_id,
  -- are we missing anything?
  COUNT(DISTINCT(order_date))
FROM dannys_diner.sales
GROUP BY customer_id;
```
>`DISTINCT` was used to ensure date is counted only once if a customer decides to visit the restaurant more than once on that date.


### Q3. What was the first item from the menu purchased by each customer?



### Q4. What is the most purchased item on the menu and how many times was it purchased by all customers?



### Q5. Which item was the most popular for each customer?



### Q6. Which item was purchased first by the customer after they became a member?



### Q7. Which item was purchased just before the customer became a member?



### Q8. What is the total items and amount spent for each member before they became a member?



### Q9. If each $1 spent equates to 10 points and sushi has a 2x points multiplier - how many points would each customer have?



### Q10. In the first week after a customer joins the program (including their join date) they earn 2x points on all items, not just sushi - how many points do customer A and B have at the end of January?



### Q11. Recreate the following table output using the available data:



### Q12. Danny also requires further information about the ranking of customer products, but he purposely does not need the ranking for non-member purchases so he expects null ranking values for the records when customers are not yet part of the loyalty program.



