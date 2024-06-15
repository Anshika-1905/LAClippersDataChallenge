# LA Clippers Data Challenge - README

## Project Overview

With the opening of Intuit Dome this summer, the LA Clippers hope to become the gold standard for sports entertainment and fan experience. By utilizing an unprecedented amount of technology in our new arena, our data team will be able to perform more detailed analysis on customer-related information and fan behavior than ever before. As we continue to expand our reach, we are utilizing a variety of dynamic data streams, such as an in-house fan app, social media channels, streaming services, website traffic, retail purchases, and ticketing/attendance data.

In our new home, we utilize cutting-edge frictionless checkout technology across the arena, including at merchandise stores/kiosks and food & beverage stores. For this project, you will be provided with a sample of food & beverage sales data. This dataset should be used to facilitate detailed analysis of sales performance and customer behavior. Please refer to the dataset Excel file for the data dictionary.

## Deliverables

### Deliverable 1: SQL Queries and Data Visualization

#### SQL Queries

1. **Average spending for a group of 2 people:**
    - SQL Query:
      ```sql
      SELECT AVG(OrderTotalQuantity) AS AverageSpending
      FROM your_dataset
      WHERE GroupSize = 2;
      ```

2. **Highest amount of Food purchased in a day and the date:**
    - SQL Query:
      ```sql
      SELECT MAX(ProductQuantity) AS HighestAmount, ArrivalDatetime
      FROM your_dataset
      WHERE Category = 'Food'
      GROUP BY ArrivalDatetime
      ORDER BY HighestAmount DESC
      LIMIT 1;
      ```

3. **Top 5 spending orders:**
    - SQL Query:
      ```sql
      SELECT OrderID, COUNT(ProductID) AS NumOfProducts, SUM(ProductFullPrice) AS TotalRevenue, RANK() OVER (ORDER BY SUM(ProductFullPrice) DESC) AS Rank
      FROM your_dataset
      GROUP BY OrderID
      ORDER BY TotalRevenue DESC
      LIMIT 5;
      ```


