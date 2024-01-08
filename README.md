### 1. Source Data Analysis

The initial data didn't have many mistakes, so there was no need for a preliminary correction. 
We cleaned up the data by removing any unusual values to get accurate stats. 
We looked at user profiles based on their activity levels (low, medium, high) and when they placed orders.

#### Key Findings:

- Orders without surge pricing have a higher conversion rate (86%) compared to orders during surge periods (72%).
- During surge times, orders from the center have a better conversion rate (72%) compared to other locations (68%).
- Users cancel short trips more often (17%) than long ones (14%).

### 2. Hypotheses Generation:

Initially, 7 hypotheses were generated. A quick analysis enabled the swift dismissal of 2 hypotheses, 
as the suggested features were deemed unprofitable for the business and detrimental to the user experience.

The remaining five hypotheses underwent prioritization using the ICE method. For the upcoming AB test, the hypothesis with the highest assessment is as follows:

#### Hypothesis for the AB test:
If the surge factor is reduced for users placing orders during rush hours, then the price-to-order conversion will increase by 5 percentage points (pp). 
This is anticipated because the more attractive pricing offer is expected to enhance the user's willingness to make a purchase.

### Preparing for A/B Testing:

The sample was composed of users for whom the proposed change is relevant, specifically those who placed orders during the surge period. 
Using the Evan Miller calculator, the minimum sample size was determined to be 1300 in each group, with a test power of 80%, a significance level (alpha) of 5%, 
a baseline pre-test conversion rate of 72%, and a desired minimum change of 5 percentage points (pp).

Users were randomly assigned to either the test or control group. 

#### The homogeneity of the resulting groups was assessed using three methods:

- Mann-Whitney Test: p-value = 0.21 (based on the metric "average number of orders per user").
- Bootstrap: p-value = 0.44 (based on the price-to-order conversion).
- Bucketing: p-value = 0.48 (based on the price-to-order conversion).

**Conclusion:** The p-values obtained from the tests are all greater than 0.05, indicating that the groups are homogeneous. 
This suggests that any observed differences in the upcoming A/B test results are likely attributable to the proposed change rather than initial group imbalances.

### Conducting an A/B Test

The difference in price_to_order conversions between test and control groups:
![Price_to_order_conversion](https://github.com/gelya1709/AB_Test/blob/main/Graphs/Price_to_order_conversion.png)

**Conclusion:** In the test group the conversion to order is higher, but the increase is less than we expected (less than 5pp)

### Analysis of A/B Test Results (statistical)

Periodic (on the left) and cumulative (on the right) p-value:
![Periodic_and_cumulative_pvalue](https://github.com/gelya1709/AB_Test/blob/main/Graphs/Periodic_and_cumulative_pvalue.png)

**Conclusion:** The cumulative p-value shows that the results are statistically significant

### Analysis of A/B Test Results (business)

The results indicate that our initial hypothesis was not confirmed. The observed increase in the price-to-order conversion was lower than anticipated. 
The A/B test revealed that implementing the proposed change, specifically reducing the surge coefficient, may not be suitable for all users.

**Explanation:** While there was a slight increase in conversion (approximately 2-3 percentage points), 
it proved insufficient to offset the decline in revenue resulting from the reduced surge. 
Consequently, the implemented feature is projected to lead to a decrease in revenue, contradicting our business goals. 
As a result, it is not advisable to roll out this change to all users.
