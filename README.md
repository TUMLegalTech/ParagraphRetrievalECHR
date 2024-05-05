
### Dataset Summary

Legal professionals often grapple with navigating lengthy legal judgements to pinpoint information that directly address their queries. This paper focus on this task of extracting relevant paragraphs from legal judgements based on the query. We construct a specialized dataset for this task from the European Court of Human Rights (ECtHR) using the case law guides

### Data splits
We eventually end up with 4109 query-judgement pairs with 708 unique queries. The number of paragraphs in Judgement ranges from 21 to 942 with a mean of 102.78. The percentage of relevant paragraphs in each query-judgement pair ranges from 0.10% to 15% of the total number of paragraphs in that judgement, with a mean around 1.95%. The queries and paragraphs have a mean length of 36 and 135 tokens.

We partition the article/theme case law guides into two distinct splits: one exclusively designated for testing with 403 query-judgment pairs (111 unique queries) derived from these case law guides, referred to as 'Unseen article/themes'. This creates a rigorous unseen evaluation scenario, assessing the model’s performance on unfamiliar legal concepts from themes and articles that were not encountered during training. Queries originating from the other split are further divided into two subsets, resulting in 'Seen article/theme, Unseen Query' with 694 pairs (120 unique queries) and 'Seen article/theme, Seen Query' with 3012 pairs (477 unique queries). 

The former, reserved for testing, exposes the model to previously encountered themes/articles, but with new queries. The latter group is further divided into training (2230 pairs), validation (302 pairs), and test (480 pairs) sets. The test set within the 'Seen article/theme, Seen Query' category assesses the model’s comprehension of familiar legal concepts on new judgments in the test set.

## Dataset structure

File court_data.pkl has the following columns:
- id: judgmenet ECHR id
- par_num: number of the paragraph
- paragraph: actual paragraph content

For the other files we have: 
- id: fjudgment ECHR id that was cited.
- context2: The query with the location of the citations inside the Judgement section.
- joined: Joined list of paragraph numbers that were cited inside the Judgement section

### Languages

English