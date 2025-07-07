# Amazon-Product-Review-Analysis
Exploratory data analysis of Amazon product review data using Excel. Includes dashboards and insights on ratings, reviews, discounts, and revenue.


# Amazon Product Review Analysis

## Table of Contents
- **[Project Overview](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/edit/main/README.md#1-project-overview)**
- **[Project Scope](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/edit/main/README.md#2-project-scope)**
- **[Data Source](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/edit/main/README.md#3-data-source)**
- **[Data Cleaning](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/edit/main/README.md#4-data-cleaning)**
- **[Objectives](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/edit/main/README.md#5-objectives)**
- **[Tools Used](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/edit/main/README.md#6-tools-used)**
- **[Project Summary](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/edit/main/README.md#project-summary)**
- **[Key Business Questions Answered](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/edit/main/README.md#business-questions-answered)**
- **[Key Insight](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/edit/main/README.md#-key-insights)**
- **[Dashboard & Visuals](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/edit/main/README.md#dashboard--visuals)**
- **[Conclusion]()**

## 1. Project Overview
This project explores product and customer review data from Amazon with the goal of uncovering practical insights that can help sellers improve their products, adjust pricing strategies, and better connect with their customers. It was carried out as part of my Project in The Incubator Hub

The dataset contains a blend of product details and aggregated customer reviews for over 1,400 products. With a mix of pivot tables, calculated columns, and creative visualizations, this analysis follows a storytelling approach—one that doesn’t just answer questions but tells the story behind the numbers.

## 2. Project Scope
- The focus of this project is to:
- Understand how discounts, prices, and reviews affect product performance
- Identify patterns in customer engagement across different product categories
- Discover opportunities to improve potential revenue
- Build a simple, clean, and informative Excel dashboard that tells the story visually

## 3. Data Source
The dataset was sourced from Amazon product pages and provided as part of the RetailTech Insights training program. Each row represents a unique product listing. The dataset has 1,465 rows and 16 columns before cleaning. It includes:
Product names, categories, actual prices, discounts, ratings, and number of reviews
Customer review details like title, content, and images

## 4. Data Cleaning
Before diving into the analysis, I spent time cleaning the dataset to make it easier to work with:
### Removed irrelevant columns:
Deleted: `about_product, user_id, user_name, review_id, review_title, review_content, img_link, and product_link`. These added no analytical value to the objectives.

### Handled missing values:
Instead of dropping entire rows with missing cells, I replaced the blanks with the average of that column but only when the row still held other valuable data. This helped preserve useful information without introducing noise.

### Removed duplicate entries:
Duplicate records based on the Product ID were identified and removed to ensure the accuracy of product counts and avoid inflating summary metrics.

### Created new calculated columns to enhance the analysis:
`Product >=50% discount:` `=IF(F2>=50%, "YES", "NO")`

`Less than 1000 reviews:` `=IF(H2<1000, "<1000 Reviews", ">=1000 Reviews")`

`Potential_Revenue:` `=E2*H2` (E2 = Actual Price, H2 = Rating Count)

`Price_Range:` `=IFS(E2<200,"<₹200",E2<=500,"<=₹500",E2>500,">₹500")`

`Top_Product:` `=G2+(H2/1000)` (G2 = Rating, H2 = Rating Count)

These changes helped make the data analysis-ready and allowed for more focused pivot table breakdowns later on.

## 5. Objectives
This project was built around 14 specific questions, each designed to uncover something useful:
 1. Average discount % by category
 2. Product count per category
 3. Total number of reviews per category
 4. Highest-rated products
 5. Average actual vs discounted prices by category
 6. Products with the most reviews
 7. Count of products with 50%+ discount
 8. Rating distribution
 9. Potential revenue by category
 10. Unique products per price range
 11. Relationship between rating and discount
 12. Count of products with <1,000 reviews
 13. Categories with highest discounted products
 14. Top 5 products based on rating + review count

## 6. Tools Used
- Microsoft Excel (primary tool)
- Pivot Tables
- Calculated Columns
- Conditional Formatting
- Charts (Bar, Pie, Clustered Columns, and Slicers)
- Excel Dashboard

## Project Summary
- **Dataset Size:** 1,465 products × 16 columns
- **Tools Used:** Excel (Pivot Tables, Calculated Columns, Dashboard Design)
- **Goal:** Use Excel to analyze trends in ratings, pricing, reviews, discounts and build a clean, interactive dashboard.

## Business Questions Answered
### 1. What is the average discount percentage by product category?
To understand which product categories offer the most value to customers, I calculated the average discount percentage by category. Using a pivot table, I placed `category` in the row section and `discount_percentage` in the values section (set to average). This showed me which categories consistently offer higher discounts. A column chart helped visualize this clearly, highlighting categories like electronics and fashion as the most discounted.


![](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/blob/main/1.%20Average%20Discount%20by%20Category.png)



### 2. How many products are listed under each category?
This question aims to show the breadth of products offered per category. I used a pivot table with category in rows and product_id in values (set to count). This gave me a simple but powerful snapshot of product variety across categories. For instance, some categories had hundreds of listings, while others were more niche. A bar chart was used to communicate this distribution visually.


![](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/blob/main/2.%20Products%20per%20Category.png)



### 3. What is the total number of reviews per category? 
To understand customer engagement per category, I analyzed the total number of reviews. `rating_count` is a direct indicator of how many customers interacted with a product, so I summed it up per category using a pivot table. This showed which categories attracted the most customer feedback. A bar chart helped visualize the top-performing categories in terms of review volume.


![](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/blob/main/3.%20Total%20Review%20by%20Category.png)



### 4. Which products have the highest average ratings?  
Customer satisfaction is key, so I focused on identifying top-rated products. I used a pivot table where `product_name` was placed in rows and `rating` in values (set to average). I then sorted the pivot table in descending order to reveal the highest-rated products. This helped spotlight standout items, some of which had 4.9 to 5.0 ratings, a sign of consistent quality.


![](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/blob/main/4.%20Highest%20Average%20Ratng%20Products.png)


### 5. What is the average actual price vs discounted price by category?  
This comparison helps understand pricing strategies across categories. I created a pivot table with `category` in rows, then added both `actual_price` and `discounted_price` in the values section (set to average). A clustered column chart made the comparison easy to grasp. It was interesting to see how deeply certain categories are discounted, and which ones hold their value more.


![](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/blob/main/5.%20Average%20Actual%20Price%20vs%20Discount%20Price%20by%20Category.png)



### 6. Which products have the highest number of reviews?  
This metric reflects product popularity or marketing success. I created a pivot table with `product_name` in rows and `rating_count` in values (set to sum). Sorting by review count in descending order gave a clear view of the most-reviewed products. These are often bestsellers or highly visible items. A horizontal bar chart was used to showcase the top performers.


![](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/blob/main/6.%20Products%20with%20Highest%20Reviews.png)



### 7. How many products have a discount of 50% or more?  
To identify deep deals, I used a simple formula:
`=COUNTIF(discount_percentage, ">=50")  `
This gave me the number of products with at least 50% off. This figure is useful for understanding the intensity of discounting on the platform. I presented it as a KPI card on the dashboard for quick visibility.


![](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/blob/main/7.%20Products%20greater%20than%20or%20equal%20to%2050%25%20Discount.png)



### 8. What is the distribution of product ratings?
This analysis shows how well products are generally rated. I used a pivot table with `rating` in rows and counted how many products fall under each rating. A column chart helped illustrate the spread. Most products cluster around 4.0 to 4.5, showing that sellers are doing well in maintaining customer satisfaction.


![](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/blob/main/8.%20Distribution%20of%20Product%20Ratings.png)



### 9. What is the total potential revenue by category?
To estimate how much money each category could generate, I created a new column:  
excel
potential_revenue = actual_price × rating_count  
Then I built a pivot table with `category` in rows and `potential_revenue` in values (sum). This showed which categories could drive the most revenue based on interest and price. A bar chart visualized the potential cash flow by segment.

![](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/blob/main/9.%20Potential%20Revenue%20by%20Category.png)



### 10. What is the number of unique products per price range bucket?
I created a new column to bucket products:
`excel`
`=IF(actual_price<200,"<₹200",IF(actual_price<=500,"₹200–₹500",">₹500"))`
Then I used a pivot table to count the number of products in each price range. This helped identify how pricing is distributed across the catalog. I used a pie chart to represent the product spread by pricing tier.


![](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/blob/main/10.%20Price%20Range%20Distribution.png)



### 11. What is the relationship between rating and discount percentage?
To explore this relationship, I used a scatter plot with `discount_percentage` on the x-axis and `rating` on the y-axis. I added a trendline with an R² value of **0.0186**. The trendline was nearly horizontal, suggesting that there is **no meaningful relationship** between discount and rating. This insight shows that customers don’t rate products based on discount alone — they focus more on product quality.


![](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/blob/main/11.%20Rating%20Vs%20Discount%20Scatter%20Plot.png)



### 12. How many products have fewer than 1,000 reviews?
This analysis helps highlight low-engagement products. I used a formula:  
`excel`
`=COUNTIF(rating_count, "<1000") `
This gave the count of products with under 1,000 reviews — useful for identifying products that might need more marketing or exposure. I also visualized this as a big number card for easy reference on the dashboard.


![](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/blob/main/12.%20Products%20with%20and%20greater%20than%201000%20reviews.png)



### **13. Which categories have products with the highest discounts?**
To answer this, I used a pivot table with `category` in rows and `discount_percentage` in values (set to **Max**, not average or sum). This highlighted which category had the **single most discounted product**, giving a more accurate picture of deep deals. It’s useful for spotting aggressive pricing strategies by category.


![](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/blob/main/13.%20Categories%20with%20Highest%20Discount.png)



### 14. Identify the top 5 products in terms of rating and number of reviews combined.
Here I created a **custom score** using:
`excel`
`=rating + (rating_count / 1000)`
This formula balances quality (rating) and popularity (review count). I used a helper column for this and sorted the data to find the top 5 products. These represent the best of both worlds: high-quality and high-volume — perfect for identifying flagship products.


![](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/blob/main/14.%20Top%205%20Products.png)



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



## Dashboard & Visuals

### Final Dashboard Preview

![](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/blob/main/Amazon%20Dashboard.png)



### KPI Cards

![](https://github.com/manuel-sam/Amazon-Product-Review-Analysis/blob/main/KPI%20cards.png)



## 9. Conclusion
This analysis uncovered several practical insights that Amazon sellers can act on:

**Top Engagement Categories:** The Electronics category led in overall review count, while Personal Care had the highest product listings—showing two very different types of customer engagement patterns.

**High Revenue Buckets:** Products priced above ₹500 generated the highest potential revenue, despite being fewer in number. For example, a luxury skincare product priced at ₹1,099 with over 2,000 reviews significantly boosted revenue projections.

**Rating vs. Discount:** Discounts didn’t always lead to better ratings. Many highly rated products had modest or no discounts—like a gadget in the Electronics category with a 4.8-star rating and only a 10% discount.

**Low Exposure:** A majority of products had fewer than 1,000 reviews, signaling low customer reach. This includes products from categories like Kitchen and Home Decor.

**Deep Discounts, Poor Results:** Some products with 50%+ discount still had poor ratings and low review. For instance, a beauty item discounted by 60% had a rating of just 2.9 and under 200 reviews.

From identifying top performing categories to questioning the effectiveness of big discounts, this project revealed more than just numbers it exposed strategy gaps and opportunities.
This journey also allowed me to improve my Excel and storytelling skills through data. It reinforced the idea that no data is too small to tell a powerful story if you ask the right questions and explore with sincerity.

I’m currently seeking an internship or Entry level data analyst role in an organization where I can apply these skills, continue learning, and contribute meaningfully to the Organization.

Feel free to connect with me on [LinkedIn](https://www.linkedin.com/in/emmanuel-samuel001) or send an email to e.samuel4907@gmail.com.

Thank you for reading!


