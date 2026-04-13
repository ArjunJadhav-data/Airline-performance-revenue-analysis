## 📊 Airline Revenue Driver Analysis

### 🎯 Objective

Identify which factors — **Passengers, Ticket Price, and Load Factor** — have the strongest impact on airline revenue.

---

### 🛠️ Approach

To determine the key drivers of revenue, we performed **correlation analysis** using Pandas. Correlation helps measure the strength and direction of the relationship between variables.

---

### 💻 Code Implementation

```python
import pandas as pd

# Load dataset
data = pd.read_csv("airline_data.csv")

# Select relevant columns
df = data[['Passengers', 'Ticket_Price_USD', 'Load_Factor_%', 'Revenue_USD']]

# Calculate correlation
correlation_matrix = df.corr()

print(correlation_matrix)
```

---

### 📈 Visualization (Heatmap)

```python
import seaborn as sns
import matplotlib.pyplot as plt

plt.figure(figsize=(8,5))
sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
plt.title("Correlation Matrix - Revenue Drivers")
plt.show()
```

---

### 🔍 Key Insights

* **Passengers** show a strong positive correlation with revenue
  → More passengers directly increase total revenue

* **Ticket Price** also has a strong positive impact
  → Higher ticket prices lead to higher revenue per flight

* **Load Factor (%)** has a moderate impact
  → Indicates seat utilization efficiency but affects revenue indirectly

---

### 💼 Business Interpretation

* Increasing **passenger count** and optimizing **ticket pricing** are the most effective ways to boost revenue
* Maintaining a high **load factor (>80%)** ensures better utilization and profitability
* Airlines should focus on **pricing strategies and demand forecasting** to maximize revenue

---

### 🚀 Conclusion

Revenue in airline operations is primarily driven by **passenger volume and ticket pricing**, while load factor plays a supporting role in improving efficiency. These insights can help airlines make better decisions related to pricing, scheduling, and capacity management.
