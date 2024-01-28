RFM-Analysis
RFM Analysis is used to understand and segment customers based on their buying behaviour. RFM stands for recency, frequency, and monetary value, which are three key metrics that provide information about customer engagement, loyalty, and value to a business. 

Overview 
RFM Analysis is a concept used by Data Science professionals, especially in the marketing domain for understanding and segmenting customers based on their buying behaviour.
Using RFM Analysis, a business can assess customers’:
recency (the date they made their last purchase)
frequency (how often they make purchases)
and monetary value (the amount spent on purchases)
Recency, Frequency, and Monetary value of a customer are three key metrics that provide information about customer engagement, loyalty, and value to a business.
To perform RFM analysis using Python, we need a dataset that includes customer IDs, purchase dates, and transaction amounts. With this information, we can calculate RFM values for each customer and analyze their patterns and behaviours. I found an ideal dataset for this task.

RFM Analysis using Python
I’ll start the task of RFM Analysis by importing the necessary Python libraries.
Calculating RFM Values
I’ll now calculate the Recency, Frequency, and Monetary values of the customers to move further.
To calculate recency, we subtracted the purchase date from the current date and extracted the number of days using the datetime.now().date() function. It gives us the number of days since the customer’s last purchase, representing their recency value.
After that, we calculated the frequency for each customer. We grouped the data by ‘CustomerID’ and counted the number of unique ‘OrderID’ values to determine the number of purchases made by each customer. It gives us the frequency value, representing the total number of purchases made by each customer.
Finally, we calculated the monetary value for each customer. We grouped the data by ‘CustomerID’ and summed the ‘TransactionAmount’ values to calculate the total amount spent by each customer. It gives us the monetary value, representing the total monetary contribution of each customer.
By performing these calculations, we now have the necessary RFM values (recency, frequency, monetary value) for each customer, which are important indicators for understanding customer behaviour and segmentation in RFM analysis.
Calculating RFM Scores

Now let’s calculate the recency, frequency, and monetary scores:
We assigned scores from 5 to 1 to calculate the recency score, where a higher score indicates a more recent purchase. It means that customers who have purchased more recently will receive higher recency scores.
We assigned scores from 1 to 5 to calculate the frequency score, where a higher score indicates a higher purchase frequency. Customers who made more frequent purchases will receive higher frequency scores.
To calculate the monetary score, we assigned scores from 1 to 5, where a higher score indicates a higher amount spent by the customer.
To calculate RFM scores, we used the pd.cut() function to divide recency, frequency, and monetary values into bins. We define 5 bins for each value and assign the corresponding scores to each bin.

Once the scores are added to the data, you will notice that they are categorical variables. You can use the data.info() method to confirm this. So we need to convert their datatype into integers to use these scores further:
RFM Value Segmentation
Now let’s calculate the final RFM score and the value segment according to the scores:
To calculate the RFM score, we add the scores obtained for recency, frequency and monetary value. For example, if a customer has a recency score of 3, a frequency score of 4, and a monetary score of 5, their RFM score will be 12.
After calculating the RFM scores, we created RFM segments based on the scores. We divided RFM scores into three segments, namely “Low-Value”, “Mid-Value”, and “High-Value”. Segmentation is done using the pd.qcut() function, which evenly distributes scores between segments.
Now let’s have a look at the resulting data:

RFM Customer Segments
The above segments that we calculated are RFM value segments. Now we’ll calculate RFM customer segments. The RFM value segment represents the categorization of customers based on their RFM scores into groups such as “low value”, “medium value”, and “high value”. These segments are determined by dividing RFM scores into distinct ranges or groups, allowing for a more granular analysis of overall customer RFM characteristics. The RFM value segment helps us understand the relative value of customers in terms of recency, frequency, and monetary aspects.
Now let’s create and analyze RFM Customer Segments that are broader classifications based on the RFM scores. These segments, such as “Champions”, “Potential Loyalists”, and “Can’t Lose” provide a more strategic perspective on customer behaviour and characteristics in terms of recency, frequency, and monetary aspects. Here’s how to create the RFM customer segments:

RFM Analysis
Now let’s analyze the distribution of customers across different RFM customer segments within each value segment:
Summary
RFM Analysis is used to understand and segment customers based on their buying behaviour. RFM stands for recency, frequency, and monetary value, which are three key metrics that provide information about customer engagement, loyalty, and value to a business. I hope you liked this article on RFM Analysis using Python. Feel free to ask valuable questions in the comments section below.
