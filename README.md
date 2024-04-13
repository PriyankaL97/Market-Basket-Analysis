# Market-Basket-Analysis
A market basket analysis (Association analysis) on The Instacart Online Grocery Shopping Dataset 2017. 
Data used: https://www.kaggle.com/competitions/instacart-market-basket-analysis/data

### Stage 1: Data Integration & EDA

We have five different files:
- orders.csv
- order_products_train.csv
- products.csv
- aisles.csv
- departments.csv

#### Understanding relationship and new insights from the data
1. How many times was each product ordered?
    
2. The numbers of orders per department and visualize using an appropriate plot.

3. On which day of the week do customers tend to buy more groceries? Which are the peak hours of shopping?

    * The frequency of orders on week days  using an appropriate plot
    * The frwquency of orders during hours of the day using and appropriate plot?
    
4. The ratio of Re-ordered and Not Re-ordered products and visualize it
 
5. The heatmap of Re-order ratio of the Day of week vs Hour of day


 
### Stage 2: Creating a basket

As the dataset contains huge amout of data, let us take a subset of the data to extract the association rules from it.

**Assumptions:** Segment the data by considering the 100 most frequent ordered items. Please note it is just an assumption. You can consider 'n frequent order items as per your choice.

Steps:

* Drop the unwanted columns

* Find the frequencies of orders based on the products and consider 100 most frequent order items

 * Extract the records of 100 most frequent items(which are extracted in previous step) from combined dataframe.
 
 * Create a Pivot table with `order_id` as index and `product_name` as columns and `reorder` as values.
 
     * set the `order_id` as index using set_index()
     * fill all the nan values with 0
     
  * After performing the above step, tehre are a lot of zeros in the data, make sure that any positive values are converted to a 1 and anything less than 0 is set to 0.

### Stage 3: Apply Apriori algorithm to find association rules

* As the dataset contains huge amount of data, let us take a subset of the data to extract the association rules from it.

    **Assumptions:** Segment the basket by considering 100000 record. Please note its just an assumption, you can consider 'n' records as per choice.

- Find the association rules and make a dataframe
