# Amazon-Product-Review-Analysis
Exploratory data analysis of Amazon product review data using Excel. Includes dashboards and insights on ratings, reviews, discounts, and revenue.

# Amazon Product Review Analysis

This project is part of my DSA Data Analysis Capstone. It focuses on analyzing Amazon product review data to uncover insights that help inform pricing, product strategy, and customer satisfaction.

## Project Summary

-  **Dataset Size:** 1,465 products × 16 columns
- 🛠**Tools Used:** Excel (Pivot Tables, Calculated Columns, Dashboard Design)
- **Goal:** Use Excel to analyze trends in ratings, pricing, reviews, and discounts — and build a clean, interactive dashboard.

## 🧾 Business Questions Answered

### 1. What is the average discount percentage by product category?
To understand which product categories offer the most value to customers, I calculated the average discount percentage by category. Using a pivot table, I placed category in the row section and discount_percentage in the values section (set to average). This showed me which categories consistently offer higher discounts. A column chart helped visualize this clearly, highlighting categories like electronics and fashion as the most discounted.

---

### 2. How many products are listed under each category?
This question aims to show the breadth of products offered per category. I used a pivot table with category in rows and product_id in values (set to count). This gave me a simple but powerful snapshot of product variety across categories. For instance, some categories had hundreds of listings, while others were more niche. A bar chart was used to communicate this distribution visually.

---

### 3. What is the total number of reviews per category? 
To understand customer engagement per category, I analyzed the total number of reviews. rating_count is a direct indicator of how many customers interacted with a product, so I summed it up per category using a pivot table. This showed which categories attracted the most customer feedback. A bar chart helped visualize the top-performing categories in terms of review volume.

### 4. Which products have the highest average ratings?  
Customer satisfaction is key, so I focused on identifying top-rated products. I used a pivot table where product_name was placed in rows and rating in values (set to average). I then sorted the pivot table in descending order to reveal the highest-rated products. This helped spotlight standout items, some of which had 4.9 to 5.0 ratings — a sign of consistent quality.

---

### 5. What is the average actual price vs discounted price by category?  
This comparison helps understand pricing strategies across categories. I created a pivot table with category in rows, then added both actual_price and discounted_price in the values section (set to average). A clustered column chart made the comparison easy to grasp. It was interesting to see how deeply certain categories are discounted, and which ones hold their value more.

---

### 6. Which products have the highest number of reviews?  
This metric reflects product popularity or marketing success. I created a pivot table with product_name in rows and rating_count in values (set to sum). Sorting by review count in descending order gave a clear view of the most-reviewed products. These are often bestsellers or highly visible items. A horizontal bar chart was used to showcase the top performers.

---

### 7. How many products have a discount of 50% or more?  
To identify deep deals, I used a simple formula:
=COUNTIF(discount_percentage, ">=50")  
This gave me the number of products with at least 50% off. This figure is useful for understanding the intensity of discounting on the platform. I presented it as a KPI card on the dashboard for quick visibility.

---

### 8. What is the distribution of product ratings?

This analysis shows how well products are generally rated. I used a pivot table with `rating` in rows and counted how many products fall under each rating. A column chart helped illustrate the spread. Most products cluster around 4.0 to 4.5, showing that sellers are doing well in maintaining customer satisfaction.

---

### 9. What is the total potential revenue by category?

To estimate how much money each category could generate, I created a new column:  
excel
potential_revenue = actual_price × rating_count  
Then I built a pivot table with `category` in rows and `potential_revenue` in values (sum). This showed which categories could drive the most revenue based on interest and price. A bar chart visualized the potential cash flow by segment.

---

### 10. What is the number of unique products per price range bucket?

I created a new column to bucket products:
excel
=IF(actual_price<200,"<₹200",IF(actual_price<=500,"₹200–₹500",">₹500"))
Then I used a pivot table to count the number of products in each price range. This helped identify how pricing is distributed across the catalog. I used a pie chart to represent the product spread by pricing tier.

---

### 11. What is the relationship between rating and discount percentage?**

To explore this relationship, I used a scatter plot with `discount_percentage` on the x-axis and `rating` on the y-axis. I added a trendline with an R² value of **0.0186**. The trendline was nearly horizontal, suggesting that there is **no meaningful relationship** between discount and rating. This insight shows that customers don’t rate products based on discount alone — they focus more on product quality.

---

### 12. How many products have fewer than 1,000 reviews?

This analysis helps highlight low-engagement products. I used a formula:  
excel
=COUNTIF(rating_count, "<1000") 
This gave the count of products with under 1,000 reviews — useful for identifying products that might need more marketing or exposure. I also visualized this as a big number card for easy reference on the dashboard.

---

### **13. Which categories have products with the highest discounts?**

To answer this, I used a pivot table with `category` in rows and `discount_percentage` in values (set to **Max**, not average or sum). This highlighted which category had the **single most discounted product**, giving a more accurate picture of deep deals. It’s useful for spotting aggressive pricing strategies by category.

---

### 14. Identify the top 5 products in terms of rating and number of reviews combined.

Here I created a **custom score** using:
excel
=rating + (rating_count / 1000)
This formula balances quality (rating) and popularity (review count). I used a helper column for this and sorted the data to find the top 5 products. These represent the best of both worlds: high-quality and high-volume — perfect for identifying flagship products.

---



## 💡 Key Insights

| Metric                     | Value Example       |
|----------------------------|---------------------|
| Total Products             | 1,351               |
| Total Reviews              | ~25.6 million        |
| Average Rating             | 4.1 ★               |
| Total Potential Revenue    | ₹119.1 Billion      |
| Products with ≥50% Discount| 680                 |
| Average Discount Price     | 3,296 |
| Average Discount Percent    | 47% |

---

## 📸 Dashboard & Visuals

### 🧩 Final Dashboard Preview

![](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/blob/main/Amazon%20Dashboard.png)

---

### 🎯 KPI Cards

![](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/blob/main/KPI%20cards.png)

---

### 📈 Rating Distribution

![Rating Chart](
---

### 🛍️ Discount % by Category

![Discount Chart](./visuals/discount_by_category.png)

---

### 🧊 Price Range Distribution

![](

### 🏆 Top 5 Products by Combined Score

![Top Products](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/blob/main/14.%20Top%205%20Products.png)

---

### 📉 Rating vs Discount Scatter Plot

![Scatter Plot](./visuals/scatter_rating_vs_discount.png)

**R² = 0.0186**  
➡️ No significant relationship between discount and rating. Customers rate products independently of pricing strategy.

---

## 📂 Files Included

| File | Description |
|------|-------------|
| `data/amazon_product_reviews_cleaned.xlsx` | Cleaned dataset |
| `analysis/pivot_tables.xlsx` | Pivot tables answering all questions |
| `analysis/dashboard_final.xlsx` | Interactive dashboard |
| `analysis/dashboard_screenshot.png` | Full dashboard preview |
| `visuals/*.png` | Visual assets used in dashboard and README |
| `insights_summary.md` | Detailed interpretation of results |

---

## 🧠 What I Learned

- Creating interactive dashboards using Pivot Tables & Slicers
- How to extract and communicate business insights from product-level data
- Designing a professional Excel layout (dark mode, KPI cards, charts)
- Translating raw data into compelling visuals and narratives for stakeholders

---

## 🚀 About This Project

This case study was part of my final capstone for the **DSA Data Analysis Program**. It demonstrates my ability to:
- Clean and analyze real-world datasets
- Visualize data clearly for decision-making
- Use Excel to answer business questions with confidence

---

**🔗 Connect with me on [LinkedIn](#) to view more projects!**
