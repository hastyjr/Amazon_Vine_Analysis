# Amazon_Vine_Analysis

## Overview
## Vine Program Analysis
The following analysis is on Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

In this project, a large dataset of personal health care items was used to determine if there is any bias for Vine reviews in this category. PySpark was used to perform the ETL process to extract, transform, and connect the dataset to an AWS RDS instance, and load the transformed data into pgAdmin. Additionally, PySpark was used to determine if there was any bias toward favorable reviews from Vine members in the dataset. Finally, a written analysis was provided on the bias of the Vine reviews, to include another recommended analysis to determine other ways to identify any bias toward favorable reviews from Vine members in the dataset.

### Extracted Dataset
https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Health_Personal_Care_v1_00.tsv.gz

---
# Results

* How many Vine reviews and non-Vine reviews were there?

    There were `497` Vine reviews and `120,863` non-Vine reviews.

     The below screenshots show the number of Vine and non-Vine reviews in the dataset.

    ![total vine reviews](https://github.com/hastyjr/Amazon_Vine_Analysis/blob/main/Resources/paid_total_reviews.png)

    ![total non-vine reviews](https://github.com/hastyjr/Amazon_Vine_Analysis/blob/main/Resources/unpaid_total_reviews.png)

* How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

    There were `220` Vine reviews that were 5 stars and `74,470` non-Vine reviews that were 5 stars.

    The below screenshots show the number of 5-star Vine and non-Vine reviews in the dataset.

    ![paid_five_star_reviews](https://github.com/hastyjr/Amazon_Vine_Analysis/blob/main/Resources/paid_five_star_reviews.png)

    ![unpaid_five_star_reviews](https://github.com/hastyjr/Amazon_Vine_Analysis/blob/main/Resources/unpaid_five_star_reviews.png)

* What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
            
    `44.3% of` Vine reviews were 5 stars and `62%` of non-Vine reviews were 5 stars.

    The below screenshots show the percentage of 5-star Vine and non-Vine reviews in the dataset.

    ![paid_five_star_reviews_percentage](https://github.com/hastyjr/Amazon_Vine_Analysis/blob/main/Resources/paid_percentage_five_star_reviews.png)

    ![unpaid_five_star_reviews_percentage](https://github.com/hastyjr/Amazon_Vine_Analysis/blob/main/Resources/unpaid_percentage_five_star_reviews.png)

# Summary

The percentage of 5-star reviews for Vine members is `44.3%` while the percentage of 5-star reviews for non-Vine members is `62%`. This shows that there is a `17.7%` difference in the percentage of 5-star reviews between Vine and non-Vine members. This is a significant difference and shows that there is a positivity bias for reviews in the Vine program.

There are additional analysis that can be performed to determine if there is a positivity bias for Vine reviews. The following analysis can be performed:
* Determine if there is a positivity bias for Vine reviews in a specific category.
* Determine if there is a positivity bias for Vine reviews in a specific product parent.
* Determine if there is a positivity bias for Vine reviews in a specific marketplace.

The following code can be used to determine if there is a positivity bias for Vine reviews in a specific category.

```python
# Determine if there is any bias for Vine reviews in a specific category
vine_category_df = vine_df.filter(vine_df.category_id == "category_id")
vine_category_df.show()
```

The following code can be used to determine if there is a positivity bias for Vine reviews in a specific product parent.

```python
# Determine if there is any bias for Vine reviews in a specific product parent
vine_product_parent_df = vine_df.filter(vine_df.product_parent == "product_parent")
vine_product_parent_df.show()
```

The following code can be used to determine if there is a positivity bias for Vine reviews in a specific marketplace.

```python
# Determine if there is any bias for Vine reviews in a specific marketplace
vine_marketplace_df = vine_df.filter(vine_df.marketplace == "marketplace")
vine_marketplace_df.show()
```

---

# Resources
* [Amazon Reviews Dataset](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt)
* [Amazon Vine Program](https://www.amazon.com/gp/vine/help)
* [Amazon Vine Program Terms](https://www.amazon.com/gp/vine/help/terms)
* [Amazon Vine Program FAQ](https://www.amazon.com/gp/vine/help/faq)
* [Amazon Vine Program Help](https://www.amazon.com/gp/vine/help)

