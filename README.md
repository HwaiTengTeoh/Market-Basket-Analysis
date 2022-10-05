# Market Basket Analysis for Groceries Transaction
## Introduction
Frequent pattern mining is a process of extracting recurring relationships based on the number of frequencies or occurrences in a dataset. Frequent patterns are those items, sequences, or substructures that reprise database transactions with a  user-specified frequency [1]. A frequent itemset is a form of frequent pattern and refers to a set of items that occurs together and exists at least a minimum number of times (known as minimum support). Finding all frequent item sets is one of the step-ins in mining for association rule. 

The concept of association rule mining was popularised in 1993 through a study on an extensive database of retail customer transactions known as market basket analysis. A new algorithm is proposed to generate all significant association rules between items bought together in a shopping cart.

Market basket analysis is structured around association rules which tell us that items are related to each other, perhaps due to the items being bought together frequently. The Association rule can be regarded as "if-then" statements that consist of antecedent (if) and consequent (then), which both are made up of a list of items. The association rule's strength or interestingness for the relationship between the antecedent and consequent is then measured by support and confidence. For instance, if we find that buying bread is associated with buying milk, we could state it as "if bread then milk."

### The role of Metrics
The usage of the association rule in market basket analysis will focus on the analysis of rules. Since there are many rules available, it would be significant if we could limit them by taking only the valuable rules. To get those rules, we will use some metrics acting as a measure of the performance of the rule, which allows us to quantify the usefulness of the relationships or associations between the items. The metrics discussed in this report are as follows: support, confidence, Lift, and convictions.

#### Support
- Support is the ratio of the frequency of an item set to the total number of transactions and represents the applicability of an association rule. 
- An Association rule with a high support count indicates that the rule plays a significant role in the whole transaction, and those with a low support count can be ruled out as uninteresting rules and hence can be excluded from further association analysis. 

#### Confidence
- Confidence is the reliability measure of inference made by a rule or the conditional probability of occurrence of the consequent given the antecedent. 
- The higher the confidence, the more likely it is for the consequent's item set to be present in the antecedent's item set. 

#### Lift
- Lift measure can be used to consider the support for consequent in determining the correlation between the rule antecedent and rule consequent, meaning it measures both sides of the rule. 
- Lift is the ratio between the rule's confidence and the support of the itemset in the consequent, assuming the consequent is independent of the antecedent. 
- The lift value primarily revolves around 1, in which the value equivalent to 1 indicates that the antecedent and consequent are independent and not correlated. 
- A lift value more excellent than 1 represents a strong association and positive correlation, denoting that the occurrence of one implies the occurrence of the other. However, the weakness of the lift value is that it only measures the co-occurrence of the consequent instead of the implication value of the rule. 

#### Conviction
- The conviction was developed as an alternative to confidence which was found not to capture the direction of associations adequately, and in contrast to lifting, it takes into consideration the absence of consequent and is sensitive to rule direction. 
- Conviction measures the degree of implication of a rule or has the value of 1 if items are unrelated. 
- Conviction value is the ratio of the frequency that the rule is making an incorrect prediction divided by the observed frequency of incorrect prediction. 
- The higher conviction value indicates that the consequent depends strongly on the antecedent.

## Problem Statement

## Objectives
The objectives are as follows:
-	To discuss about Apriori algorithm and its application with transaction data
-	To compute the usage of metrics and pruning process to determine the significant association rules between items
-	To detail out the procedure and observations from Market Basket Analysis by application with transaction data

## Data Sources
- The "Market_Basket_Data.csv" dataset contains all the items purchased in each transaction per row. 
- The items sold are tomato sauce, bramble, babies food, salt, extra dark chocolate, mushroom cream sauce, escalope, frozen vegetables, strawberries, dessert wine, antioxydant juice, cake, french wine, tea, tomatoes, frozen smoothie, sparkling water, gluten free bar, body spray, green grapes, eggplant, spaghetti, energy drink, candy bars, yogurt cake, butter, chocolate bread, shrimp, eggs, mineral water, red wine, shampoo, whole wheat pasta, magazines, zucchini, rice, ham, hand protein bar, chili, clothes accessories, parmesan cheese, energy bar, champagne, white wine, corn, mint, asparagus, meatballs, chicken, turkey, burger sauce, protein bar, milk, salmon, avocado, light cream, spinach, carrots, pancakes, soda, cookies, oil, salad, blueberries, low fat yogurt, burgers, french fries, shallot, hot dogs, gums, chutney, strong cheese, flax seed, honey, cream, chocolate, black tea, whole weat flour, almonds, cottage cheese, pet food, whole wheat rice, melons, cauliflower, water spray, light mayo, mayonnaise, tomato juice, cider, pickles, green beans, bacon, toothpaste, grated cheese, pepper, fresh bread, fresh tuna, cereals, barbecue sauce,  asparagus, mashed potato, bug spray, green tea, vegetables mix, fromage blanc, nonfat milk, brownies, muffins, sandwich, olive oil, oatmeal, cooking oil, yams, napkins, soup, ketchup, pasta, ground beef, herb & pepper, mint green tea.

