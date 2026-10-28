# Homework 11: Bootstrap, CLT, and Normal Approximation

Use two-sided large-sample Normal tests and intervals throughout. Use the following critical values unless a problem says otherwise:

| Confidence Level | Significance Level $\alpha$ | Two-Sided Critical Value |
| :---: | :---: | :---: |
| 90% | 0.10 | 1.645 |
| 95% | 0.05 | 1.96 |
| 99% | 0.01 | 2.576 |

For Problems 4-6, assume independent random samples from the two groups and independent observations within each group.

1. A random sample has
   $$
   \bar{X}=52,\qquad s=10,\qquad n=100.
   $$
   Compute the estimated standard error of $\bar{X}$. Test
   $$
   H_0:\mu=50
   \qquad \text{vs.} \qquad
   H_1:\mu\ne 50
   $$
   at significance levels $\alpha=.10,.05,.01$ using the large-sample $z$-statistic. These correspond to 90%, 95%, and 99% confidence levels. Construct a 95% confidence interval for $\mu$.

2. Suppose
   $$
   \hat{S}=3.1,\qquad \widehat{SE}(\hat{S})=1.3.
   $$
   Construct 90%, 95%, and 99% confidence intervals, and test the null hypothesis that $S=0$ at the corresponding significance levels $\alpha=.10,.05,.01$. When do you reject or fail to reject the null of $S=0$?

3. A health survey compares a biomarker to a benchmark value of 12. The sample has
   $$
   \bar{X}=11.5,\qquad s=3,\qquad n=36.
   $$
   Is 12 a plausible value for the population mean? Construct a 95% confidence interval for $H_0:\mu=12$ versus $H_1:\mu\ne12$. Do you reject or fail to reject the null?

4. A real estate analyst compares the average price of a house in two neighborhoods.
    Group A:
    $$
    \bar{X}_A=25,\qquad s_A=8,\qquad n_A=100
    $$
    Group B:
    $$
    \bar{X}_B=22,\qquad s_B=7,\qquad n_B=100.
    $$
    Compute the two-sample $Z$-statistic for testing equality of means. Construct an approximate 95% confidence interval for $\mu_A-\mu_B$.

5. A hospital compares recovery time under two treatments.
    Treatment A:
    $$
    \bar{X}_A=14,\qquad s_A=6,\qquad n_A=81
    $$
    Treatment B:
    $$
    \bar{X}_B=12,\qquad s_B=5,\qquad n_B=64.
    $$
    Compute the standard error of the difference in means and the corresponding test statistic for
    $$
    H_0:\mu_A-\mu_B=0.
    $$

6. A product-quality team compares defect scores across two factories.
    Factory A:
    $$
    \bar{X}_A=3.2,\qquad s_A=1.5,\qquad n_A=49
    $$
    Factory B:
    $$
    \bar{X}_B=2.8,\qquad s_B=1.4,\qquad n_B=64.
    $$
    Is the difference statistically large relative to the noise? Compute the test statistic and confidence interval for $H_0:\mu_A-\mu_B=0$, and interpret the result at $\alpha=.05$.

7. In `./data/ames_prices.csv`, create an indicator that equals 1 when `Central.Air == 'Y'` and 0 otherwise.
   
   a. Estimate the proportion of homes with central air.
   
   b. Using a reproducible random-number seed, generate at least 2,000 bootstrap estimates of this proportion. Report the seed and number of bootstrap replications.
   
   c. Compute the bootstrap standard error as the sample standard deviation of the bootstrap estimates (using `ddof=1` ensures that there's the $1/(N-1)$ degrees of freedom correction).
   
   d. Using the original estimate and the bootstrap standard error, construct Normal 90%, 95%, and 99% confidence intervals.
   
   e. Use each confidence interval to evaluate $H_0:p=.90$. At the matching significance levels $\alpha=.10,.05,.01$, state whether you reject or fail to reject the null hypothesis. Briefly interpret your results.

8. In `./data/ames_prices.csv`, estimate the Pearson correlation between `np.arcsinh(area)` and `np.arcsinh(price)`.
   
   a. Using a reproducible random-number seed, generate at least 2,000 bootstrap estimates of the correlation by resampling paired rows. Report the seed and number of bootstrap replications.
   
   b. Compute the bootstrap standard error as the sample standard deviation of the bootstrap estimates (using `ddof=1` ensures that there's the $1/(N-1)$ degrees of freedom correction).
   
   c. Using the original estimate and the bootstrap standard error, construct centered-Normal 90%, 95%, and 99% confidence intervals.
   
   d. Use each confidence interval to evaluate $H_0:\rho=0$. At the matching significance levels $\alpha=.10,.05,.01$, state whether you reject or fail to reject the null hypothesis. Briefly interpret the association without making a causal claim.
   
   e. Briefly explain why `area` and `price` must remain paired during resampling.

9. In `./data/metabric.csv`, use `Overall Survival (Months)` to estimate the mean recorded time to death or last follow-up. Include both living and deceased patients.
   
   a. Using a reproducible random-number seed, generate at least 2,000 bootstrap estimates of the mean. Report the seed and number of bootstrap replications.
   
   b. Compute the bootstrap standard error as the sample standard deviation of the bootstrap estimates (using `ddof=1` ensures that there's the $1/(N-1)$ degrees of freedom correction).
   
   c. Using the original estimate and the bootstrap standard error, construct centered-Normal 90%, 95%, and 99% confidence intervals.
   
   d. Use each confidence interval to evaluate $H_0:\mu=120$ months. At the matching significance levels $\alpha=.10,.05,.01$, state whether you reject or fail to reject the null hypothesis.
   
   e. Interpret the estimate and confidence intervals in both months and years. Because living patients' eventual death times are right-censored, explain why these results do not estimate unrestricted mean lifetime.


10. In `./data/nhanes_data_17_18.csv`, select respondents who are at least 18 years old and have an observed value for `SleepHoursWeekdaysOrWorkdays`. Estimate their mean weekday sleep.
   
   a. Using a reproducible random-number seed, generate at least 2,000 bootstrap estimates of the mean. Report the seed and number of bootstrap replications.
   
   b. Compute the bootstrap standard error as the sample standard deviation of the bootstrap estimates (`ddof=1`).
   
   c. Using the original estimate and the bootstrap standard error, construct centered-Normal 90%, 95%, and 99% confidence intervals.
   
   d. Use each confidence interval to evaluate $H_0:\mu=8$ hours. At the matching significance levels $\alpha=.10,.05,.01$, state whether you reject or fail to reject the null hypothesis.
   
   e. Interpret the result and discuss whether its statistical and practical significance tell the same story. For this exercise, treat observations as independent and unweighted. Because the complex survey design is ignored, do not describe the result as nationally representative or the intervals as survey-adjusted.
