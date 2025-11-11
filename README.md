# 📊 Portfolio Management & Analysis Using SQL

This project analyzes personal investment data using SQL. It includes brokers, assets, transactions, market prices, and derived time elements to generate insights using SQL queries.

---

## 📁 Project Overview

This SQL-based project focuses on analyzing personal portfolio data to answer key investment questions. It explores total investments, top-performing assets, monthly trends, and broker-specific metrics.

---

## 🛠️ Tools & Technologies Used

- MySQL
- SQL Workbench
- Structured CSV files

---

## 🗂️ Dataset Structure

| Table Name              | Description                                      |
|-------------------------|--------------------------------------------------|
| Brokers                 | Contains BrokerID and BrokerName                |
| Assets                  | Contains AssetID, AssetName, and AssetType      |
| InvestmentTransactions  | Contains TransactionID, AssetID, BrokerID, Date, Quantity, TotalValue |
| AssetType               | AssetType, AssetID                              |
| Date                    | Date, Month, Year, Quarter                      |
| MarketPrices            | Date, AssetID, MarketPrice                      |

---

## 🧮 SQL Queries & Use Cases

- ✅ Total Investment Made
- 📈 Top 3 Assets by Total Value
- 📅 Monthly Investment Flow (Inflow / Outflow)
- 🧩 Number of Assets Managed by Each Broker
- 🏆 Broker with Highest Total Investment
- 📋 Last Three Transactions
- 🔁 Same Assets Invested on More Than 8 Days
- 📊 Percentage of Investment per Broker
- 💰 Average Price Per Unit for Each Asset
- 📆 Daily Investment Summary
- 📉 Least Invested Broker
- 🔢 Average Units Invested per Transaction

---

## 🧠 Sample Advanced Use Cases

```sql
-- Assets with investment above average
SELECT a.AssetName, SUM(t.TotalValue) AS TotalInvestment
FROM InvestmentTransactions t
JOIN Assets a ON t.AssetID = a.AssetID
GROUP BY a.AssetName
HAVING SUM(t.TotalValue) > (
    SELECT AVG(TotalValue) FROM InvestmentTransactions
);

-- Brokers with no transactions
SELECT BrokerName
FROM Brokers
WHERE BrokerID NOT IN (
    SELECT DISTINCT BrokerID FROM InvestmentTransactions
);
```

---

## 📄 Conclusion

This project demonstrates the use of SQL for data cleaning, aggregation, subqueries, and time-based investment analysis. It highlights skills in database design, schema creation, and efficient querying.

---

👤 **Done By**: Divakaran S
