# A/B Testing for Payment Behavior Analysis
## Project Overview
This project aims to analyze user payment behavior through A/B testing. The dataset contains user interactions, payment history, and experiment group classifications. The goal is to determine whether a particular change (e.g., feature rollout, pricing strategy) significantly impacts user payment rates.

## Dataset Description
The dataset (raw_data.csv) contains 58,938 observations and 13 features:

id_user – Unique user identifier
gender – User's gender
date_reg – Date of registration
platform – User platform (mobile, desktop, other)
id_traffic_source – Traffic source ID
country_group – Country category
age_group – User age category
system – Operating system (Windows, iOS, etc.)
date_payment – Date of payment (if applicable)
method – Payment method (card, apple-pay, etc.)
amount – Payment amount
successful_payment – Binary flag (1 if payment is successful, 0 otherwise)
split_group – A/B testing group (0 = Control, 1 = Treatment)
## Data Preprocessing
Converted date_reg and date_payment columns to datetime format.
Created the paying_share metric, indicating whether a user successfully made a payment.
Analyzed weekly paying share trends.
## Exploratory Data Analysis (EDA)
User Registration Trends

Most users registered in July (34,255 users), followed by June (12,512) and August (12,171).
Paying share fluctuates over time, with notable peaks and drops.
Platform Distribution

79.1% of users are on mobile, while 14.7% use desktop and 6.2% fall under 'other'.
Payment Behavior

Users in the treatment group (split_group = 1) and control group (split_group = 0) were compared for spending trends.
Visualized daily mean payment amounts for each group.
Demographic Insights

Payment trends analyzed across age groups, gender, and platform using box plots and histograms.
## A/B Testing Methodology
### Step 1: Stratified Sampling
Randomly sampled users from both groups while maintaining the same age distribution.
645 users from Control (A) and 826 users from Treatment (B) were selected.
### Step 2: Calculating Paying Share
Control group (A) paying share: 23.09%
Treatment group (B) paying share: 10.32%
A significant drop in paying share observed in the treatment group.
### Step 3: A/A Testing for Validation
Split the control group into two subgroups (A0 and A1) and conducted a chi-square test.
Result: p-value = 0.8115 (no significant difference).
Confirms that sampling was random and unbiased.
### Step 4: A/B Test Analysis
Compared paying share between A and B groups using a chi-square test.
## Result:
Chi-square statistic = 8.81
p-value = 0.0122 → Statistically significant!
Indicates that the treatment had a significant negative impact on payment rates.
Conclusion & Recommendations
Findings
The treatment group (B) paid significantly less than the control group (A).
The A/A test confirmed no selection bias, validating our experiment's integrity.
The feature introduced in the treatment group negatively impacted payment behavior.
