---
title: 'BUDS Training: Error rates, coverage rates, and power Lab'
subtitle: Raven Ico
output:
  pdf_document:
    fig_height: 2
    fig_width: 5
    number_sections: false
---



# Problem 1

Each time we make a statistical decision, say based on a confidence interval or p-value, we are making a decision in the face of uncertainty, and therefore there is an associated risk of making an incorrect decision.  In hypothesis testing we refer to two types of errors: type I errors, when we reject a true $H_0$; and type II errors, when we fail to reject a false $H_0$.  The type I error rate can be controlled directly by the construction of our test - in particular, our $\alpha$ significance level tells us the maximum $P(\mbox{Type I Error})$.  The likelihood of a type II error depends on several things: the sample size, the significance level, the variability in the data, and the true effect size.  

## Part (a)

Suppose we observe Shaq shoot 20 freethrows, and we want to use our sample to decide if he shoots freethrows with better than 50\% accuracy.  Let $p$ be his true freethrow percentage, and consider a test that rejects $H_0: p \leq 0.5$ when he make $c$ or more shots out of 20. $c/20$ is the critical value for this hypothesis test (i.e. will reject the null hypothesis if the sample freethrow percentage is greater than or equal to $c/20$). 

Suppose his freethrow percentage is exactly 50\% (so rejecting $H_0$ is an error).  Make a plot of $P(\mbox{Type I Error})$ versus $c$, for $c=0,1,\ldots,20$.  Which value of $c$ will give us a test with a type I error rate closest to but not greater than $0.05$?  

(hint: notice that $P(\mbox{Type I Error}) = P(X \geq c)$, where $X\sim binomial(20,0.5)$. Be careful to include the $Pr(X=c)$ in your calculations).  





## Part (b)

Assume now, we don't know the true value of Shaq's free throw percentage. Use your value of $c$ from the previous problem and calculate the value of a type II error, $Pr(X < c)$, for all values of freethrow percentage ($p = X/20$) where it is possible to make a type II error (it's not possible to make this error when $H_0: p \le 0.5$ is true).  Create a plot of type II error vs. Shaq's true FT\%, 




# Problem 2

## Part (a)
We would like to conduct a clinical trial to compare the mean levels of expression of a specific protein in patients given drug A versus patients given drug B. The null hypothesis is that the expression levels for drug B are less than or equal to those of drug A. Assuming the protein expression levels in each of the groups is approximately normally distributed with a pooled standard deviation of 1. The effect size is the true difference in means between the two groups. Plot the power of a t-test with significance level 0.05 by the effect size for sizes $\{0.05, .1, .15, ... 0.95, 1\}$.  Plot different curves for sample sizes $n = 50, 100, 150, 200$.



## Part (b)
For each sample size, what effect size can you detect with a power of 0.8? Explain this result in words. 




# Problem 3

```r
set.seed(2019)
n <- 9 # Sample size
alpha <- 1 # Shape parameter  
beta <- 10 # Scale parameter

x <- rgamma(n, alpha, beta) #A random sample to play with
ci <- t.test(x)$conf.int[1:2] #Get the confidence interval bounds
```

## Part (a)
The above piece of code simulates a sample from a gamma distribution and calcultes the confidence interval for the mean. Simulate 100 random samples and store the confidence interval and mean for each sample, arrange the dataframe by the value of the means.

## Part (b)
Create a plot of the 100 simulated confidence intervals with the true mean indicated by a line on the graph.

## Part (c)
Report the percentage of confidence intervals that successfully capture the true expected value (the coverage rate), and conversely, the percentage of confidence intervals that don't contain the true value (the error rate). 

## Part (d) 
Is the error rate close to what it should be?

## Part (e)
Now run the simulation 1,000 times. Calculate the coverage rate and error rate and comment. Can you think of any reasons these intervals might have a higher error rate than they should? 




