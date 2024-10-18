# Group 23 - Buy Now, Pay Later project

## Project Description
Since the BNPL company has limited places for merchants to onboard, this project aims to utilise datasets provided and external datasets to create a ranking system for merchants so that BNPL company can choose merchants to cooperate with to optimise their profit.

## Datasets Description
`transaction` contains the transaction details between different merchants and consumers, including transaction amount, order datetime, `merchant_abn` and `consumer_id`
`c_match` matches `consumer_id` with `user_id`
`c_raw_detail` contains the personal information of consumers with `consumer_id`
`m_detail` contains information of each merchant
`c_fraud` contains `user_id` with their fraud probability on a particular date
`m_fraud` contains `merchant_abn` with their fraud probability on a particular date

`employee` contains the employment information of each suburb (in SA2 suburb code)from 2021 ABS census
`postcode` matches SA2 suburb code to postcode
`aus_population` contains population information of each suburb from 2021 ABS census
`aus_income` contains weekly income information of each suburb from 2021 ABS census

## Environmental Requirement
Python 3.x
PySpark
Pandas
Matplotlib
Seaborn
Install dependencies using: pip install pyspark pandas matplotlib seaborn
Additionally, a local Spark cluster is needed to ensure Spark is properly installed and configured.
Make sure sufficient storage is passed to the Spark session

## Models and Methods
### Pre-processing and Analysis
The Isolation Forest model identifies anomalies by isolating data points in a dataset based on their feature values, with points that are easier to isolate being more likely to be classified as anomalies.
Using Seaborn/Matplotlib, we create a boxplot to visualize the distribution of transaction amounts after outlier removal.
Using Pandas and NumPy, a correlation matrix is created for the selected numeric columns. This matrix will hold the correlation coefficients between pairs of variables, which quantify the strength and direction of their relationships.
The correlation matrix is visualized using a heatmap with Seaborn. Annotations (annot=True) are added to display the correlation coefficients directly on the heatmap. We use the coolwarm colormap to distinguish positive and negative correlations clearly.
### Categorization
This part focuses on categorizing merchants based on their tags using machine learning and natural language processing (NLP) techniques. We employed tokenization, Word2Vec for feature extraction, and K-means clustering to group the merchants into distinct categories.
Step 1: Tokenization
We began by tokenizing the tags_lower column in the dataset using a Tokenizer. This step breaks down the merchant tags into individual tokens (words) which are later used for feature extraction.
Step 2: Word2Vec for Feature Extraction
Once the data was tokenized, we used Word2Vec to convert the tokenized words into numeric feature vectors. This step captures the semantic meaning of the merchant tags.
Step 3: K-means Clustering
We applied the K-means algorithm to group the merchants into distinct categories based on their feature vectors. After testing multiple values of k, we determined that k=25 yielded the best results.
Step 4: Assigning Descriptive Labels to Clusters
To make the clusters more interpretable, we manually assigned descriptive labels to each cluster. For example, clusters were labeled as "Garden and Florist Retail", "Technology", etc.
