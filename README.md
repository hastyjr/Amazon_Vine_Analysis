# Amazon_Vine_Analysis

## Vine Program Analysis Overview

The following analysis is on Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

In this project, a large dataset of personal health care items was used. PySpark was used to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, Additionally, PySparke was used to determine if there was any bias toward favorable reviews from Vine members in the dataset. Finally, a written analysis was provided on the bias of the Vine reviews.

### Extracted Dataset
https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Health_Personal_Care_v1_00.tsv.gz

---
# Results

* How many Vine reviews and non-Vine reviews were there?

        There were 497 Vine reviews and 120,863 non-Vine reviews.
![vine reviews](/Amazon_Vine_Analysis/Resources/paid_total_reviews.png)




* How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?
            
            There were 170 Vine 5-star reviews and 61,654 non-Vine 5-star reviews.

* What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
            
                34.1% of Vine reviews were 5 stars and 51.0% of non-Vine reviews were 5 stars.

# Summary

state if there is any positivity bias for reviews in the Vine program. Use the results of your analysis to support your statement. Then, provide one additional analysis that you could do with the dataset to support your statement.
