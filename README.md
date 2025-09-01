# ☕ Coffee Sales Dashboard (Power BI)

This repository contains a **Power BI ** built to analyze coffee sales data.  
The project includes **data preprocessing**, **custom measures**, and **visual storytelling** to highlight sales performance, customer preferences, and daily/weekly patterns.

---

## 📂 Data Preparation

The dataset was originally provided in **CSV format**. Before building the dashboard, a few preprocessing steps were applied:

1. **Removed unnecessary column**:  
   - The `cash_type` column contained the same value (`card`) for all rows.  
   - Since it did not provide meaningful insights, the column was deleted.

2. **Sorted data (Ascending Order)**:  
   - The dataset was sorted to ensure clarity and consistency.
<img width="1254" height="774" alt="csv" src="https://github.com/user-attachments/assets/7dfe23fe-da0b-474d-bfb8-6f80059d3f83" />


---


## 📊 Dashboard Overview

<img width="1308" height="735" alt="coffee sales dashboard png" src="https://github.com/user-attachments/assets/7dd8bb79-dae1-46ef-9212-a77891ad80f1" />

The dashboard visualizes key metrics and insights from the coffee sales dataset.  
Below is a breakdown of each card and visualization:

### 1. **KPI Cards**
- **Total Sales (1M)**: Shows the total revenue generated from coffee sales.  
- **Total Orders (426)**: Displays the total number of customer orders.  
- **Average Sales per Day (44.81K)**:  
  - Custom **measure** created with DAX:  
    ```DAX
    Average Sales per Day =
    DIVIDE(
        SUM(Coffe_sales[money]),
        DISTINCTCOUNT(Coffe_sales[Date])
    )
    ```
  - Shows the average daily sales amount.
- **Average Orders per Day (14)**:  
  - Custom **measure** created with DAX:  
    ```DAX
    Average Orders per Day =
    DIVIDE(
        COUNTROWS(Coffe_sales),
        DISTINCTCOUNT(Coffe_sales[Date])
    )
    ```
  - Represents the average number of orders placed per day.

---

### 2. **Pie Chart – Sum of Money by Coffee Type**
- Displays the **revenue contribution** of each coffee type.  
- A **custom color palette** was applied to represent each coffee according to its natural tone:

| Coffee Type             | Color Description                | Hex Code  |
|--------------------------|----------------------------------|-----------|
| Latte                   | Light milky coffee               | `#D7B899` |
| Americano with Milk      | Creamy coffee                    | `#B08968` |
| Cappuccino              | Cinnamon-toned light coffee      | `#C49E85` |
| Cortado                 | Caramel with milk tones          | `#A47149` |
| Hot Chocolate           | Dark chocolate                   | `#5D4037` |
| Americano               | Black coffee                     | `#3E2723` |
| Espresso                | Almost black (very dark roast)   | `#1C0A00` |
| Cocoa                   | Sweet cocoa brown                | `#7B3F00` |

This enhances readability and creates an intuitive connection between the coffee type and its color.

---

### 3. **Bar Chart – Average Orders per Day by Coffee Type**
- Displays the **average number of daily orders** for each coffee type.  
- Latte appears to be the most frequently ordered coffee.

---

### 4. **Funnel – Sum of Money by Time of Day**
- Compares sales revenue across **Morning, Afternoon, and Night**.  
- Morning generates the highest revenue, showing coffee’s importance as a morning beverage.

---

### 5. **Treemap – Sum of Money by Weekday**
- Breaks down total revenue by day of the week.  
- Useful to identify **peak business days** (e.g., Tuesday, Thursday) and **slower periods** (e.g., Sunday).

---

### 6. **Slicer – Sales by Month**
- Provides a month-by-month distribution of sales.  
- Helps to identify **seasonal patterns** and **monthly performance**.

---

## 🛠️ Tools & Technologies
- **Microsoft Power BI Desktop**
- **CSV Dataset** (cleaned & prepared)
- **DAX Measures** (for calculated KPIs)

---








