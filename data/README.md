#Group 23 - Buy Now, Pay Later project

##Project Description
Since the BNPL company has limited places for merchants to onboard, this project aims to utilise datasets provided and external datasets to create a ranking system for merchants so that BNPL company can choose merchants to cooperate with to optimise their profit.

##Datasets Description
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

##Environmental Requirement
Python 3.x
PySpark
Pandas
Matplotlib
Seaborn
Install dependencies using: pip install pyspark pandas matplotlib seaborn
Additionally, a local Spark cluster is needed to ensure Spark is properly installed and configured.
Make sure sufficient storage is passed to the Spark session

##Models and Methods
