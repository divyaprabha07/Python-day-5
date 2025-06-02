# Python-day-5
The dataset has 48,620 rows and 12 columns, covering pizza orders with details like name, category, size, price, and order timing.
DATA TYPES
order_date and order_time are currently strings and can be converted to datetime for temporal analysis.
Most categorical fields are strings: pizza_size, pizza_category, pizza_name, etc.
Quantitative fields like quantity, unit_price, and total_price are numeric and ready for analysis.
Next, I’ll:
1. Clean/convert relevant columns (order_date, order_time)
2. Provide visual + statistical exploration using:
Histograms, Boxplots, Scatterplots
Pairplots & Heatmaps
OBSERVATION FOR EACH VISUALIZATION:
1. Distribution of Unit Prices
sns.histplot(df['unit_price'], kde=True, bins=30)
Unit prices are concentrated in specific tiers (e.g., 10, 15, 20), indicating a fixed pricing strategy.
The distribution is right-skewed, suggesting that most pizzas are moderately priced with a few premium options.![1000086427](https://github.com/user-attachments/assets/1bc5388e-85be-4a89-902c-893fbaadd546)
2. Boxplot of Total Price by Pizza Size
sns.boxplot(x='pizza_size', y='total_price', data=df)
Larger pizza sizes (e.g., XL and L) tend to have higher total prices, as expected.
Some outliers in smaller sizes (S and M) indicate large quantity orders of small pizzas.
![1000086428](https://github.com/user-attachments/assets/4e78fbcb-2bec-451a-86a5-07d35c0198f5)
3. Order Count by Pizza Category
sns.countplot(x='pizza_category', ...)
Classic and Veggie categories are the most popular among customers.
Supreme pizzas are ordered the least, possibly due to higher pricing or niche preference.
![1000086429](https://github.com/user-attachments/assets/f4961f5a-fb33-4a94-aa0a-f7866e7c76cb)
4. Pairplot of Quantity, Unit Price, and Total Price
sns.pairplot(df[['quantity', 'unit_price', 'total_price']])
A strong positive linear relationship exists between quantity × unit price and total price.
No strong correlation between quantity and unit price, implying consistent pricing regardless of quantity.
![1000086430](https://github.com/user-attachments/assets/84e6e50d-357f-4a0b-b36a-76cb7296b301)
