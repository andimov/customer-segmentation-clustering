# Customer Segmentation & Behavioral Analysis
## Unsupervised Learning Project: RFM-Based Clustering

This project uses unsupervised learning to group customers based on how they shop. Transaction data from a UK online retail store (2009-2011) was analyzed to find different types of customers. This helps businesses create better marketing campaigns and keep customers coming back.

## What was Found

Four to five distinct customer groups were discovered using K-Means and Hierarchical Clustering. The analysis shows clear differences between high-value customers ("Champions") and customers who haven't shopped in a while ("Hibernating"). Specific marketing recommendations for each group were created.

The main customer segments are:
1. **Champions** - Shop often, spend a lot, bought recently (treat them like VIPs)
2. **Loyal Customers** - Regular shoppers with moderate spending (keep them engaged)
3. **Potential Loyalists** - Recent buyers who might become regulars (nurture them)
4. **New Customers** - Just made their first purchase (help them get started)
5. **At-Risk** - Used to shop but haven't lately (try to win them back)
6. **Hibernating** - Haven't shopped in a long time (decide if it's worth reactivating)

## Getting Started

You'll need Python 3.8 or higher and pip installed.

1. Clone this repository:
   ```bash
   git clone https://github.com/andimov/customer-segmentation-clustering.git
   cd customer-segmentation-clustering
   ```

2. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

3. Download the dataset from [Kaggle](https://www.kaggle.com/datasets/mashlyn/online-retail-ii-uci) and save it as `data/online_retail_II.csv`

4. Open the notebook:
   ```bash
   jupyter notebook customer_segmentation_analysis.ipynb
   ```

## About the Data

The Online Retail II dataset from the UCI Machine Learning Repository (hosted on Kaggle) was used. It contains about 1 million transactions from a UK-based online store between 2009 and 2011. Each transaction includes information like invoice number, product code, quantity, price, customer ID, and country.

## How It Was Done

First, the data was cleaned. About 20% of records had missing customer IDs, so those were removed. Cancellations, returns, and unusual product codes were also filtered out. Then extreme outliers that could skew the results were handled.

Next, RFM scores were calculated for each customer:
- **Recency:** How many days since their last purchase
- **Frequency:** How many times they've shopped
- **Monetary:** How much money they've spent total

The data was skewed (most customers shop rarely and spend little), so a log transformation was applied and everything was standardized. This makes the clustering work better.

Two clustering methods were tried - K-Means and Hierarchical Clustering - to make sure the segments are real and not just an artifact of one algorithm. PCA was used to visualize the clusters in 2D and confirm they're well-separated.

Finally, what makes each cluster unique was examined and business-friendly names were given to them. Then specific marketing strategies for each group were created.

## What Was Learned

The models found 4-5 clusters that make business sense. Both K-Means and Hierarchical Clustering agreed on the segmentation, which provides confidence in the results.

From a business perspective, this segmentation lets you:
- Target high-value customers with special offers
- Re-engage customers who are slipping away
- Focus marketing dollars where they'll have the most impact

## Marketing Recommendations

**Champions** (shop often, spend a lot, bought recently)
- Give them VIP treatment: early access to new products, loyalty rewards, referral bonuses
- These customers drive a lot of revenue, so invest in keeping them happy

**At-Risk** (used to shop regularly but haven't lately)
- Send win-back emails with special offers
- Ask them why they stopped shopping
- High priority - losing these customers hurts

**Hibernating** (haven't shopped in a long time)
- Try aggressive win-back campaigns with deep discounts
- But evaluate carefully - reactivation might not be worth the cost

**New Customers** (just made first purchase)
- Send onboarding emails with product tips
- Offer a discount on their second purchase
- Focus on getting that first repeat purchase

For detailed recommendations on all segments, check out the notebook.

## Project Files

```
customer-segmentation-clustering/
├── data/
│   └── online_retail_II.csv          # Dataset (download separately)
├── customer_segmentation_analysis.ipynb  # Main analysis
├── requirements.txt                   # Python packages needed
├── .gitignore                         
└── README.md             
```

## Technologies Used

- Python 3.8+
- pandas, numpy for data work
- matplotlib, seaborn for visualizations
- scikit-learn for machine learning (K-Means, Hierarchical Clustering, PCA)
- scipy for statistical functions
- jupyter for the interactive notebook

## Future Improvements

There's always more that could be done:
- Track how customers move between segments over time
- Add product preferences and predict customer lifetime value
- Try other clustering methods like DBSCAN or Gaussian Mixture Models
- Test marketing campaigns on different segments to measure what works
- Build a system that automatically segments customers in real-time

## References

- Dataset: [Online Retail II - UCI ML Repository via Kaggle](https://www.kaggle.com/datasets/mashlyn/online-retail-ii-uci)
- RFM Analysis is a well-established customer segmentation framework
- Clustering algorithms from scikit-learn

## Note

The dataset file is too large to include in this repository. You'll need to download it from Kaggle and place it in the `data/` folder before running the notebook.

## License

This project is open source and available under the [MIT License](LICENSE).

---

**Project Repository:** https://github.com/andimov/customer-segmentation-clustering
