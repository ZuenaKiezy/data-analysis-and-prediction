# Data Cleaning and Visualization of Amazon Dataset

This repository contains a project that focuses on cleaning and visualizing an Amazon dataset to extract useful insights. The dataset  includes product reviews, review count, product details, and other related information. The goal is to clean the data, handle missing or inconsistent data, and perform various visualizations to understand trends, patterns, and key metrics.

## Project Overview

The primary objectives of this project are to:
- Perform data cleaning to handle missing values, outliers, duplicates, and ensure data consistency.
- Visualize key metrics and relationships within the data.
- Gain insights into Amazon product sales, review patterns, and other features to inform decision-making.

## Data

The dataset used in this project is the Amazon dataset.It contains 1465rows and 16 columns.The data was cleaned by removing missing values and handling data types.
The dataset contained the following features:
- **Product ID**: A unique identifier for each product.
- **Product Name**: Name of the product.
- **Category**: The category under which the product falls (e.g., Electronics, car and motorbike).
- **Discount Price**: Discount Price of the product.
- **Rating**: Average rating for the product.
- **Review Count**: The number of reviews for the product.
- **Actual Price**: The actual priceof the product.
- **Review Text**: Text of the review provided by the customers.

### Example Data:
| Product ID | Product Name     | Category    | Price | Rating | Review Count | Sales | Review Text      | Date       |
|------------|------------------|-------------|-------|--------|--------------|-------|------------------|------------|
| 1234       | Wireless Headset | Electronics | 99.99 | 4.5    | 250          | 1000  | "Great quality!" | 2025-03-21 |
| 5678       | Running Shoes    | Car&motorbike    | 59.99 | 4.2    | 320          | 1500  | "Very comfortable."| 2025-03-20 |

## Steps to Reproduce the Analysis

### 1. **Install Dependencies:**

Clone the repository and install the required libraries.

```bash
git clone https://github.com/ZuenaKiezy/data-analysis-and-prediction.git
cd data-analysis-and-prediction
pip install -r requirements.txt
```

Dependencies may include:
- `pandas`: For data manipulation and cleaning.
- `numpy`: For numerical operations.
- `matplotlib` and `seaborn`: For data visualization.
- `wordcloud`: For generating word clouds from review text (optional).
- `plotly`: For interactive visualizations (optional).

### 2. **Data Cleaning:**

Load the Amazon dataset and perform necessary data cleaning tasks such as:
- Handling missing values (e.g., filling or dropping).
- Removing duplicates.
- Converting data types (e.g., converting the `object` column to respective dtypes).
- Handling outliers (e.g., checking for unrealistic values in `actual price` and `review count`).


### 3. **Exploratory Data Analysis (EDA):**

Use various visualization techniques to analyze the cleaned dataset and explore key insights such as:
- Distribution of ratings.
- Relationship between price and rating count.
- The most common categories.
- Trends over time for sales and reviews.

Example:

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Distribution of Ratings
sns.histplot(data['Rating'], bins=10, kde=True)
plt.title('Rating Distribution')
plt.show()

# Relationship between Discounted Price and Rating Count
sns.scatterplot(x='Discounted Price', y='Rating Count', data=data)
plt.title('Discounted Price vs Rating Count')
plt.show()
```

### 4. **Key Visualizations:**

- **Top Categories:** Find and visualize the most popular product categories.

```python
# Top Categories
top_categories = data['Category'].value_counts().head(10)
sns.barplot(x=top_categories.index, y=top_categories.values)
plt.title('Top 10 Product Categories')
plt.ylabel('Number of Products')
plt.xticks(rotation=45)
plt.show()
```

- **Review Count by Rating:** Analyze how the number of reviews is distributed across different ratings.

```python
# Review Count by Rating
sns.boxplot(x='Rating', y='Review Count', data=data)
plt.title('Review Count by Rating')
plt.show()
```

### 5. **Export Cleaned Data (Optional):**

If you want to save the cleaned dataset for future use or sharing, you can export it as a CSV file.

```python
# Save cleaned dataset to CSV
data.to_csv('cleaned_amazon_data.csv', index=False)
```

##RESULTS

From the analysis we find that products in the car and motorbike category were the poorest performing products in the data.This was followed closely by the products in the health and personal care category.This was all based on the rating counts of the products.The best performing categories were electronics followed by computer accessories as they had higher rating counts.

From the correlation analysis we can infer a weak positive correlation between rating and rating count.We also find that higher discounts on products improved their rating and rating counts.

From the results we can recommend that the Amazon team should prioritise products that fall in the car and motorbike category and health and personal care category due to low performance in the market.

Poor performing products should have their discount percentage increased as the product rating is seen to increase with higher discount amounts and products that had higher discount had higher rating counts.The Amazon team should also improve rating as it had a weak positive correlation with rating count.From the analysis, products with higher rating are seen to be performing better.

## Conclusion

This project demonstrates the process of cleaning and visualizing an Amazon dataset. By performing data cleaning and generating various visualizations, we can uncover valuable insights that help understand product sales, reviews, and customer preferences. These insights can guide business decisions, marketing strategies, and inventory management.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- The dataset is sourced from Kaggle Datasets.
- Special thanks to the contributors and libraries that made this project possible.








