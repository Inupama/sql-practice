# Week 1 · Medium Level LeetCode Problems in PostgreSQL

### 1. Managers with at Least 5 Direct Reports (570)

- **Tricky part** - Understanding how `WHERE id IN (...)` matches employee IDs to the manager IDs returned by the subquery.
- **Solution** - Group employees by `managerId`, keep groups with at least five employees, then look up the managers’ names.

### 2. Confirmation Rate (1934)

- **Tricky part**  - Keeping users who made no requests.
- **Solution** - Use `LEFT JOIN` to keep all users. Assign `1` to confirmed requests and `0` to other rows, then average per user and round to two decimal places.

### 3. Monthly Transactions I (1193)

- **Tricky part** - Showing `0` when there are no approved transactions.
- **Solution** - Group by year-month and country. Use `COUNT` and `SUM` for all transactions, `FILTER` for approved transactions, and `COALESCE` to turn a missing approved total into `0`.

### 4. Second Highest Salary (176)

- **Tricky part** - Skipping every copy of the highest salary.
- **Solution** - Find the highest salary, then use `MAX()` on salaries strictly below it. If none remain, `MAX()` returns `NULL`.

### 5. Immediate Food Delivery II (1174)

- **Tricky part** - Matching both `customer_id` and the earliest `order_date` to keep each customer’s first order.
- **Solution** - Find the first order with `MIN(order_date)` per customer. Assign `1` if the order and preferred delivery dates match and `0` otherwise. Average, multiply by 100, and round to two decimal places.

### 6. Game Play Analysis IV (550)

- **Tricky part** - Checking for a login exactly one day after each player’s first login.
- **Solution** - Find each player’s first login with `MIN(event_date)`. Use `LEFT JOIN` to check for a next-day login while keeping all players. Divide next-day returners by total players and round to two decimal places.
