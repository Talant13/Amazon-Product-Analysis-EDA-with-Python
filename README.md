🛒 Amazon Sales Analysis — EDA with Python
Exploratory Data Analysis on Amazon product listings, uncovering pricing patterns, discount strategies, rating behavior, and category trends across 1,465 products.

📦 Dataset: Amazon Sales Dataset — Kaggle


📁 Dataset
File: amazon.csv
Size: 1,465 products, 16 columns — no duplicates, 2 missing values in rating_count
ColumnTypeDescriptionproduct_idobjectUnique product identifierproduct_nameobjectName of the productcategoryobjectHierarchical category (separated by |)discounted_priceobject → floatSale price (₹)actual_priceobject → floatOriginal price (₹)discount_percentageobject → floatDiscount offered (%)ratingobject → floatAverage customer rating (0–5)rating_countobject → intNumber of customer reviewsabout_productobjectProduct descriptionreview_title / review_contentobjectCustomer review text

🔧 Data Cleaning

Removed ₹ symbols and commas from price columns → converted to float
Stripped % from discount_percentage → converted to float
Converted rating_count to int, filled 2 missing values with 0
No duplicate rows found

Engineered Features:
FeatureDescriptionprice_differenceactual_price - discounted_pricediscount_categoryHigh (≥50%) / Medium (≥30%) / LowsentimentPositive (rating ≥ 4) / Negativeprice_categoryBudget (<₹500) / Mid-Range / Premiumprice_rangeBinned price buckets

📊 Analysis & Findings
1. Rating Distribution

Ratings are left-skewed — the vast majority of products are rated between 3.5 and 4.5
Peak is around 4.0–4.2, indicating a generally satisfied customer base
Very few products fall below 3.0, suggesting low-rated items may get delisted

2. Top Product Categories

USB Cables dominate the dataset by a large margin — nearly 3x more listings than the next category
Smartwatches and Smartphones follow, then Televisions and In-Ear Headphones
The long tail is steep — top 3 categories account for a disproportionate share of listings

3. Correlation Analysis

actual_price and discounted_price are highly correlated (~0.96) — discounts are proportional, not arbitrary
discount_percentage has a weak negative correlation with rating (−0.13) — heavily discounted products tend to rate slightly lower
rating_count has minimal correlation with any pricing variable

4. Discount vs. Price Range

Budget products (<₹200) receive the highest average discounts — often 70–90%
Discounts gradually decrease as price increases — premium products offer less aggressive markdowns
This suggests MRP inflation is more common in low-cost accessory categories

5. Discount % vs. Rating (Scatter)

Wide, diffuse scatter with no visible trend — confirms the weak correlation
Products with 90% discounts span the full rating range from 3.0 to 5.0
High discounts are not a reliable signal of product quality in either direction

6. Best Value Products

576 Budget / 527 Mid-Range / 362 Premium products after price segmentation
Strong best-value candidates: discount >30%, rating ≥4.0, review count >50
Categories with the highest absolute price drops: Air Conditioners (₹33K avg), Laptops (₹22.6K), External SSDs (₹21.6K)


🔑 Key Takeaways
FindingInsightUSB Cables dominate listingsAccessories far outnumber electronics in volumeDiscount ≠ QualityWeak −0.13 correlation between discount % and ratingPrice & discount are proportionalHigh actual price → high absolute discount, not necessarily high %Budget items get steepest % discountsMRP inflation is prevalent in low-cost categoriesMost products are well-ratedRatings cluster at 4.0–4.2; very few below 3.0

🛠️ Tech Stack

Python 3.x
pandas — data cleaning and feature engineering
numpy — numerical operations
matplotlib — scatter plots, bar charts
seaborn — histograms, heatmaps, countplots
