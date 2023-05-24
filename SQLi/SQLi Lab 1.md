# LAB 1 SQLi: in WHERE clause retreival of data

##Theory
- SQL  Retreive hidden data
    - Retrive hidden data
    
    [https://website.com/products?category=gifts](https://website.com/products?category=gifts)
    
    equates to select * from products where category = gifts AND released = 1
    
    since there is nothing hidden we can also use "--"
    what does -- do?
    -- is a comment indicator in sql
    meaning that rest of the query is interpreted as a comment
    
    [https://website.com/products?category=gifts'--](https://website.com/products?category=gifts%27--)
    will show everything even if its released or not
    
##Lab1: SQL injection vulnerability in WHERE clause allowing retrieval of hidden data


Given : SQLi in product category filter

SELECT * FROM products WHERE category = 'Gifts' AND released = 1

To Solve : use an SQLi causing app to display details of all products in any category

Solve :

1. Search for something in URL
2. Add `'+OR+1=1--`what does this mean?

Note : ' by itself means empty and 1=1 everything is returned since 1=1 means it is a true statement
<img width="1027" alt="Lab1-1" src="https://github.com/minhasan3/PortSwigger-WebSecurityAcademy-Labs/assets/81883584/74db88c3-dbe6-4f8c-9917-a1da57226855">
<img width="875" alt="Lab1-2" src="https://github.com/minhasan3/PortSwigger-WebSecurityAcademy-Labs/assets/81883584/e5714757-15b8-45d0-98db-7d0b0b545a74">

