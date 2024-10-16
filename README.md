# Association-between-sleep-duration-and-self-reported-general-health-condition
What is the association between sleep duration and self-reported general health condition,  taking into account covariates such as gender, race, and moderate physical activity?
## Research question:
Examining the relationship between sleep duration and self-reported general health condition entails exploring how the time an individual allocates to sleep correlates with their subjective assessment of overall health. This investigation also takes into account covariates such as gender, race, and moderate physical activity. The research question guiding this research is: What is the association between sleep duration and self-reported general health condition? 
## Null hypothesis: 
There is no significant association between sleep duration and self-reported general health condition when accounting for covariates such as gender, race, and moderate physical activity.
## Introduction
Sleep is pivotal in maintaining overall health and well-being, serving as a restorative process for the body and mind. The quality and quantity of sleep can significantly impact various aspects of physical and mental health. However, the interaction between sleep and general health is not merely one-dimensional; it is influenced by a complex interplay of various factors. Poor sleep quality or insufficient sleep duration can lead to numerous health problems, including cardiovascular diseases, weakened immune function, and obesity.
The relationship between sleep and general health is bidirectional and complex. Inadequate sleep can exacerbate health issues, while poor health can impair sleep quality, creating a detrimental cycle. This interaction is influenced by several factors, including physical activity, gender, and race. For instance, while physical activity may enhance sleep quality, gender and race contribute to sleep and health variations through different physiological and socio-cultural factors. Understanding these multifaceted interactions is essential for formulating public health strategies to improve sleep and overall health.      


# Statistical analysis:
"PROC LOGISTIC is employed to perform multinomial analysis, extending logistic regression to handle a categorical outcome variable with more than two categories.
Proc Logistic for Multinomial Logistic with Interaction: Building upon the multinomial logistic analysis, this procedure includes interaction terms to investigate how the association between predictor variables and the multinomial response may differ across different levels. The output provides detailed insights into the interactions and their impact on the response variable.
PROC SURVEYLOGISTIC is employed to analyze complex survey data using logistic regression. This procedure adjusts for survey design features such as strata, clusters, and weights, ensuring the validity of statistical inferences for population estimates.

The initial plan for the study is an Ordinal logistic regression, but as the Proportional odds model is not satisfied, led to the multivariate analysis, when the deviance in the multivariate analysis is not rejecting the null, the interaction model has been introduced.
Primary Model(Model 1) is defined as the model before interaction  and the Interaction Model(Model 2 ) is defined as the model with interaction.

##    Results                            
Primary Model (Model 1):
Deviance and Pearson Goodness-of-Fit Statistics
Criterion	Value	DF	Value/DF	Pr > ChiSq
Deviance	82.7613	58	1.4269	0.0181
Pearson	83.6316	58	1.4419	0.0154
Model Convergence Status
Convergence criterion (GCONV=1E-8) satisfied

Response profile
Ordered Value	Sleep	Total Frequency
1	Long	1018
2	Normal	2989
3	Short	474
Model Fit Statistics
Criterion	Intercept Only	Intercept and Covariates
AIC	7571.483	7458.216
SC	7584.298	7547.922
-2 Log L	7567.483	7430.216





Type 3 Analysis of Effects
Effect	DF	Wald
Chi-Square	Pr > ChiSq
gen_health	4	48.5620	<.0001
activity	2	13.2959	0.0013
Gender	2	22.3461	<.0001
race	4	57.1001	<.0001

Testing Global Null Hypothesis: BETA=0
Test	Chi-Square	DF	Pr > ChiSq
Likelihood Ratio	137.2668	12	<.0001
Score	141.0070	12	<.0001
Wald	137.3255	12	<.0001



In the primary model, the focus is on the relationship between variables such as general health, activity, gender, and race with sleep patterns. The model shows convergence, indicated by meeting the GCONV criterion. 
Analyzing the Deviance and Pearson Goodness-of-Fit Statistics, the Deviance value is 82.7613 (DF=58, Value/DF=1.4269) with a significance level of 0.0181, and the Pearson value is 83.6316 (DF=58, Value/DF=1.4419) with a significance of 0.0154. These statistics suggest a reasonable fit. The Model Fit Statistics show AIC and SC values of 7571.483 and 7584.298 for the intercept-only model, respectively, and improved values of 7458.216 (AIC) and 7547.922 (SC) when covariates are included, indicating a better fit with the inclusion of these variables. 
The significance of the Likelihood Ratio, Score, and Wald tests (<.0001 for all) in the Testing Global Null Hypothesis section confirms the significance of the covariates. The Type 3 Analysis of Effects also validates the importance of each covariate in the model.

 ## Interaction model (Model 2):

Response Profile
Ordered
Value	Sleep	Total
Frequency
1	Long	1018
2	Normal	2989
3	Short	474
Model Convergence Status
Convergence criterion (GCONV=1E-8) satisfied

Deviance and Pearson Goodness-of-Fit Statistics
Criterion	Value	DF	Value/DF	Pr > ChiSq
Deviance	68.7442	54	1.2730	0.0854
Pearson	67.4729	54	1.2495	0.1029
Model Fit Statistics
Criterion	Intercept Only	Intercept and Covariates
AIC	7571.483	7452.199
SC	7584.298	7567.536
-2 Log L	7567.483	7416.199
	
Joint Tests
Effect	DF	Wald
Chi-Square	Pr > ChiSq
gen_health	4	48.6424	<.0001
activity	2	10.8491	0.0044
Gender	2	22.1706	<.0001
race	4	56.0437	<.0001
activity*race	4	14.0324	0.0072
Testing Global Null Hypothesis: BETA=0
Test	Chi-Square	DF	Pr > ChiSq
Likelihood Ratio	151.2838	16	<.0001
Score	156.3035	16	<.0001
Wald	150.7333	16	<.0001

The interaction model incorporates an interaction term between activity and race. This model also demonstrates satisfactory convergence. The Deviance and Pearson statistics show an improved fit compared to the primary model, with Deviance at 68.7442 (DF=54, Value/DF=1.2730, Pr > ChiSq=0.0854) and Pearson at 67.4729 (DF=54, Value/DF=1.2495, Pr > ChiSq=0.1029). 
The Model Fit Statistics further reflect this improvement, with AIC and SC values of 7571.483 and 7584.298 for the intercept-only model, and reduced values of 7452.199 (AIC) and 7567.536 (SC) for the model with covariates and interactions. The Global Null Hypothesis tests (Likelihood Ratio, Score, Wald) again show strong significance (<.0001), underscoring the importance of the variables and the interaction term.
 The Joint Tests section, particularly regarding the activity*race interaction, demonstrates significant Wald Chi-Square values, confirming the interaction's meaningful role in the model. This interaction model thus provides a more detailed understanding of how the combined effect of activity level and race influences sleep duration.

The reasons to use Race and activity as interaction are improved Model Fit: The inclusion of the race-activity interaction term significantly enhances the model fit, as indicated by AIC and SIC values in the model with the interaction term compared to the model without it. These reduced values suggest that the model with the interaction term provides a more accurate and efficient representation of the data.
statistical Significance: The race-activity interaction term demonstrates significant statistical results, as evidenced by tests such as the Wald Chi-Square test. 

## Analysis of Likelihood Estimates:

Analysis of Maximum Likelihood Estimates
Parameter	 	 	sleep	DF	Estimate	Standard
Error	Wald
Chi-Square	Pr > ChiSq
Intercept	 	 	Long	1	-1.0497	0.0392	716.0625	<.0001
Intercept	 	 	Short	1	-1.7608	0.0508	1199.9563	<.0001
gen_health	1	 	Long	1	-0.2366	0.0515	21.1100	<.0001
gen_health	1	 	Short	1	-0.3070	0.0719	18.2496	<.0001
gen_health	3	 	Long	1	0.2445	0.0552	19.6388	<.0001
gen_health	3	 	Short	1	0.3920	0.0725	29.2066	<.0001
activity	2	 	Long	1	0.0780	0.0389	4.0293	0.0447
activity	2	 	Short	1	-0.1090	0.0505	4.6543	0.0310
Gender	2	 	Long	1	0.1410	0.0368	14.6771	0.0001
Gender	2	 	Short	1	-0.0994	0.0507	3.8414	0.0500
race	2	 	Long	1	0.0516	0.0599	0.7404	0.3895
race	2	 	Short	1	0.5010	0.0711	49.6985	<.0001
race	3	 	Long	1	-0.1261	0.0526	5.7449	0.0165
race	3	 	Short	1	-0.2879	0.0708	16.5319	<.0001
activity*race	2	2	Long	1	-0.0843	0.0598	1.9876	0.1586
activity*race	2	2	Short	1	-0.0913	0.0710	1.6562	0.1981
activity*race	2	3	Long	1	-0.00922	0.0525	0.0309	0.8605
activity*race	2	3	Short	1	-0.1561	0.0706	4.8875	0.0271

General Health:
General Health (Good Health) - Long Sleep: Wald Chi-Square = 21.1100, DF = 1, p < .0001.
General Health (Good Health) - Short Sleep: Wald Chi-Square = 18.2496, DF = 1, p < .0001.
General Health (Poor Health) - Long Sleep: Wald Chi-Square = 19.6388, DF = 1, p < .0001.
General Health (Poor Health) - Short Sleep: Wald Chi-Square = 29.2066, DF = 1, p < .0001.
Null Hypothesis: There is no association between general health and sleep duration (both long and short categories).
•	For long sleep, with estimates for good health and Poor health having p-values <.0001, the null hypothesis is rejected, indicating a significant association between general health and long sleep duration.
•	For short sleep, with estimates for good health and Poor health also having p-values <.0001, the null hypothesis is again rejected, showing a significant association between general health and short sleep duration.

Activity:
Activity (No) - Long Sleep: Wald Chi-Square = 4.0293, DF = 1, p = 0.0447.
Activity (No) - Short Sleep: Wald Chi-Square = 4.6543, DF = 1, p = 0.0310.
Null Hypothesis:  There is no association between moderate physical activity and sleep duration.
•	For long sleep, the p-value is 0.0447, rejecting the null hypothesis, and indicating an association.
•	For short sleep, the p-value is 0.0310, also leading to the rejection of the null hypothesis.
Gender:

Gender (Female) - Long Sleep: Wald Chi-Square = 14.6771, DF = 1, p = 0.0001.
Gender (Female) - Short Sleep: Wald Chi-Square = 3.8414, DF = 1, p = 0.0500.
Null Hypothesis:  There is no association between gender and sleep duration.
•	For long sleep, with a p-value of 0.0001, the null hypothesis is rejected.
•	For short sleep, the p-value is 0.0500, which is borderline; thus, the association is less clear.
Race:

Race (Non-Hisp Black) - Short Sleep: Wald Chi-Square = 49.6985, DF = 1, p < .0001.
Race (Others) - Long Sleep: Wald Chi-Square = 5.7449, DF = 1, p = 0.0165.
Race (Others) - Short Sleep: Wald Chi-Square = 16.5319, DF = 1, p < .0001.

## Null Hypothesis:  There is no association between race and sleep duration.

•	For the Non-Hispanic Black in short sleep, with a p-value <.0001, the null hypothesis is rejected.
•	For Other races, significant associations are found in both long and short sleep categories (p-values: 0.0165 and <.0001, respectively).

Activity*Race Interaction:
Activity-Race Interaction (No, Others) - Short Sleep: Wald Chi-Square = 4.8875, DF = 1, p = 0.0271.
Null Hypothesis: There is no interaction effect between activity and race on sleep duration.
•	For most of the activity*race categories, the null hypothesis is not rejected due to higher p-values, except for the interaction term in the Non-Hispanic Black  for short sleep (p=0.0271), where it is rejected.

Odds ratio table:

Odds Ratio Estimates
Effect	sleep	Point Estimate	95% Wald
Confidence Limits
gen_health 1 vs 2	Long	0.796	0.673	0.941
gen_health 1 vs 2	Short	0.801	0.632	1.016
gen_health 3 vs 2	Long	1.287	1.074	1.543
gen_health 3 vs 2	Short	1.611	1.268	2.048
Gender 2 vs 1	Long	1.326	1.148	1.532
Gender 2 vs 1	Short	0.820	0.672	1.000

Wald χ² = 21.1100, df = 1, p < 0.0001, OR: 0.789, CI: 0.697 - 0.896
The odds of Longer sleep among people with good health is 20% less when compared to people with Average heath.

Wald χ² = 19.6388, df = 1, p < 0.0001, OR: 1.287, CI: 1.074 – 1.543
The odds of Longer sleep among people with poor health is 29% more when compared to people with Average heath.

Wald χ² = 29.2066, df = 1, p < 0.0001, OR: 1.611, CI: 1.268 – 2.048
The odds of short sleep among people with poor health is 61% more when compared to people with Average heath.

Wald χ² = 14.6771, df = 1, p < 0.0001, OR: 1.326, CI: 1.148 – 1.532
The odds of Longer sleep among Females is 33% more when compared to males.

Wald χ² = 3.8414, df = 1, p  0.05, OR: 0.820, CI: 0.672 - 1
The odds of short sleep among Females is 18% less when compared to males.

Proc Survey logistic:

Response Profile
Ordered
Value	sleep	Total
Frequency	Total
Weight
1	Long	1018	39956060
2	Normal	2989	144235823
3	Short	474	17488989

Odds Ratio Estimates
Effect	Point Estimate	95% Confidence Limits
NOTE: The degrees of freedom in computing the confidence limits is 15.
gen_health 1 vs 2	0.972	0.766	1.233

