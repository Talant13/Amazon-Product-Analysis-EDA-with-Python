# 🛒 Amazon Product Analysis — EDA with Python
 
Exploratory Data Analysis on Amazon India product listings, covering pricing, discounts, ratings, and customer behavior across categories.
 
---
 
## 📁 Dataset
 
**File:** `amazon.csv`  
**Size:** 1,465 products, 16 columns  
**Source:** Amazon India product listings
 
| Column | Description |
|--------|-------------|
| `product_id` | Unique product identifier |
| `product_name` | Name of the product |
| `category` | Hierarchical category (separated by `\|`) |
| `discounted_price` | Sale price (₹) |
| `actual_price` | Original price (₹) |
| `discount_percentage` | Discount offered (%) |
| `rating` | Average customer rating (0–5) |
| `rating_count` | Number of reviews |
| `about_product` | Product description |
| `review_title / review_content` | Customer review text |
 
---
 
## 🔧 Data Cleaning
 
- Removed `₹` symbols and commas from price columns → converted to `float`
- Stripped `%` from `discount_percentage` → converted to `float`
- Converted `rating_count` to `int`
- Handled 2 missing values in `rating_count` with `fillna(0)`
- No duplicate rows found
**Engineered Features:**
 
| Feature | Description |
|---------|-------------|
| `price_difference` | `actual_price - discounted_price` |
| `discount_category` | High (≥50%) / Medium (≥30%) / Low |
| `sentiment` | Positive (rating ≥ 4) / Negative |
| `price_category` | Budget (<₹500) / Mid-Range / Premium |
| `price_range` | Binned price buckets |
 
---
 
## 📊 Analysis Performed
 
1. **Rating Distribution** — Most products are rated between 3.8–4.5
2. **Top Categories** — USB Cables dominate (233 products), followed by Smartwatches and Smartphones
3. **Average Discount by Category** — Phone charms, cable protectors, and earpads offer up to 90% discounts
4. **Top Rated Products** — Filtered by highest rating + review count for reliability
5. **Discount vs. Rating Correlation** — Weak negative correlation (−0.13); higher discounts don't guarantee better ratings
6. **Highest Price Drops** — Air conditioners (₹33K avg drop), laptops (₹22.6K), and external SSDs (₹21.6K)
7. **Best Value Products** — Filtered by: discount > 30%, rating ≥ 4, rating count > 50
8. **Customer Segmentation** — 576 Budget / 527 Mid-Range / 362 Premium buyers
---
 
## 📈 Key Findings
 
- **USB Cables** are the most listed and reviewed product category on Amazon India
- **Discount ≠ Quality** — Correlation between discount % and rating is weak (−0.13)
- **Budget products dominate** — 39% of products are priced under ₹500
- **Electronics categories** offer the steepest price drops in absolute terms (₹15K–₹33K)
- Products with 90% discounts tend to have lower ratings (~3.8 avg), suggesting inflated MRP
---
 
## 🛠️ Tech Stack
 
- **Python 3.x**
- `pandas` — data manipulation
- `numpy` — numerical operations
- `matplotlib` — plotting
- `seaborn` — statistical visualizations
---
