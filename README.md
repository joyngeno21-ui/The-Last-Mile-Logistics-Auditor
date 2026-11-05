# The-Last-Mile-Logistics-Auditor
This repository hosts the root-cause data analysis framework built for **Veridi Logistics**, an e-commerce shipping manager serving thousands of online sellers. 

### A. The Executive Summary

- A 3-5 sentence summary of your findings.

My analysis reveals that delivery performance drastically influences customer sentiment: orders that arrive late receive a low average review score of 2.53 out of 5, compared to 4.29 for those delivered on time. Geographically, main e-commerce hubs like São Paulo and Minas Gerais enjoy extremely low delay rates (approx. 5%), whereas remote Northeast regions like Alagoas suffer from high delay rates of over 23%. Finally, analyzing the overall rating distribution shows that 59.2% of customers are highly satisfied 5-star 'promoters', but a significant 12.8% are frustrated 'detractors' (1 and 2 stars) who present a high risk of churn and brand damage.

**B. Project Links**
Link to Notebook: https://colab.research.google.com/drive/1yOWdAIK4Los9BL9EEQuJq4oujIekv9Xk?usp=drive_link

Link to Dashboard: https://drive.google.com/file/d/1C5-Fm5JSihrulI2fURLXDJFnVrB1Bafj/view?usp=drive_link

Link to Presentation: https://docs.google.com/presentation/d/1pOQcL0ayrSW-pO24Q7XzOXNdfoZCHDHU/edit?usp=drive_link&ouid=114025808076984413950&rtpof=true&sd=true


  ### C. Technical Explanation

- Briefly explain how you handled the "Data Cleaning".
To build a highly reliable analytics foundation, I performed the following cleanups:
•	Merged Key Entities: Combined the raw orders, customers, and reviews datasets to create a single coherent record per order.
•	Removed Extreme Sparsity: Dropped highly sparse text columns (review_comment_title and review_comment_message) that had over 60% and 88% missing values, respectively, to maintain dataframe compactness.
•	Handled Missing Records: Removed rows with missing timestamps and missing review scores (such as orders that were never delivered, canceled, or remained unapproved), bringing our dataset down from 99,992 to a perfectly complete set of 96,344 records.
•	Addressed Translation and Encodings: Corrected Portuguese category names to English by merging product_category_name_translation.csv using the robust latin-1 encoding to safely handle special character decodings.


- Explain your "Candidate's Choice" addition.

For our custom addition, we built a Distribution of Customer Review Scores (1 to 5 Stars) with both absolute counts and relative percentages.
Why This Feature Matters to the Business:
•	Identifies Brand Promoters vs. Detractors: Rather than relying purely on an average score, this distribution shows that 59.2% of customers are highly satisfied promoters (5-star ratings), while 12.8% are disappointed detractors (1 and 2 stars).
•	Flags Retention Opportunities: Active passives (3-star ratings) account for 8.3% of users. Knowing this allows customer success teams to run specialized win-back email or voucher campaigns to prevent these users from shifting to competitors.
•	Improves Lifetime Value (LTV): Proactively addressing the detractor group reduces churn, directly saving the business money, as acquiring new users is far costlier than retaining existing ones.
