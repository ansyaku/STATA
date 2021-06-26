# Analysis of Variance

Anova can fit
* one-way and
* N-way ANOVA or
* analysis of covariance (ANCOVA)
for
* balanced and
* unbalanced designs,
* including designs with missing cells.

It can also fit
* factorial,
* nested,
* mixed or
* repeated-measures designs.

# One Sample Test
***
The questions we might want to answer are these:
* what is the mean value?
* is the mean value significantly different from current expectation or theory?
* what is the level of uncertainty associated with our estimate of the mean value?

### Level Confidence 95
    . ttest preS=10

    One-sample t test
    ------------------------------------------------------------------------------
    Variable |     Obs        Mean    Std. Err.   Std. Dev.   [95% Conf. Interval]
    ---------+--------------------------------------------------------------------
        preS |      24    10.79167    .9402034    4.606037    8.846708    12.73663
    ------------------------------------------------------------------------------
        mean = mean(preS)                                             t =   0.8420
    Ho: mean = 10                                    degrees of freedom =       23

        Ha: mean < 10               Ha: mean != 10                 Ha: mean > 10
     Pr(T < t) = 0.7958         Pr(|T| > |t|) = 0.4084          Pr(T > t) = 0.2042

### Level Confidence 90
    . ttest preS=10, level(90)

    One-sample t test
    ------------------------------------------------------------------------------
    Variable |     Obs        Mean    Std. Err.   Std. Dev.   [90% Conf. Interval]
    ---------+--------------------------------------------------------------------
        preS |      24    10.79167    .9402034    4.606037    9.180279    12.40305
    ------------------------------------------------------------------------------
        mean = mean(preS)                                             t =   0.8420
    Ho: mean = 10                                    degrees of freedom =       23

        Ha: mean < 10               Ha: mean != 10                 Ha: mean > 10
     Pr(T < t) = 0.7958         Pr(|T| > |t|) = 0.4084          Pr(T > t) = 0.2042














# Two Sample Test
***

# One Way Analysis of variance
***

# Two and N Way Analysis of variance
***

# Factor Variables and Analysis of Covariance (ANCOVA)
***
