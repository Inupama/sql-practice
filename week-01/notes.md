# Week 1: PostgreSQL Medium Level Problems by Leetcode

###Problem 1 

-Problem - 570. Managers with at Least 5 Direct Reports
-Tricky part - Understanding WHERE id IN (...)
-Solution - Group employees by managerId, keep groups with at least five employees, then match those manager IDs to employee IDs to get their names.


###Problem 2

-Problem - 1934. Confirmation Rate
-Tricky part - `LEFT JOIN` keeps users who made no requests.
-Solution - `LEFT JOIN` signups to requests, group by user, give confirmed requests `1` and other rows `0`, then average and round to two decimal places.


###Problem 3

-Problem - 1193. Monthly Transactions I
-Tricky part - COALESCE shows 0 when there are no approved transactions.
-Solution - Group by year-month and country. Use COUNT and SUM for all transactions, and FILTER to count and sum only approved ones.


###Problem 4

-Problem - 176. Second Highest Salary
-Tricky part - Skip all copies of the highest salary.
-Solution - Find the highest salary, then use MAX() on salaries strictly below it. If none remain, MAX() returns NULL.


###Problem 5

-Problem - 1174. Immediate Food Delivery II
-Tricky part - Match both customer_id and the earliest order_date to keep only each customer’s first order.
-Solution - Use MIN(order_date) per customer. For those first orders, assign 1 if the preferred delivery date equals the order date and 0 otherwise. Average the values, multiply by 100, and round to two decimal places.


###Problem 6

-Problem - 550. Game Play Analysis IV
-Tricky part - Check whether each player logged in exactly one day after their first login.
-Solution - Use MIN(event_date) to find each player’s first login. Use LEFT JOIN to check for a login the next day while keeping all players. Divide the number who returned by the total number of players and round to two decimals.
