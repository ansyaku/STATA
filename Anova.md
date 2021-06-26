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
Test satu arah biasanya berfungsi untuk melihat apakah rata-rata sampel berbeda secara signifikan dari nilai yang diharapka, nilai tahun lalu, atau secara general nilai yang dihipotesiskan. Selain itu, mungkin juga untuk melihat level ketidakpastian yang terasosiasi dengan nilai rata-rata.
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





         . signtest preS=10

         Sign test

                 sign |    observed    expected
         -------------+------------------------
             positive |          12          11
             negative |          10          11
                 zero |           2           2
         -------------+------------------------
                  all |          24          24

         One-sided tests:
           Ho: median of preS - 10 = 0 vs.
           Ha: median of preS - 10 > 0
               Pr(#positive >= 12) =
                  Binomial(n = 22, x >= 12, p = 0.5) =  0.4159

           Ho: median of preS - 10 = 0 vs.
           Ha: median of preS - 10 < 0
               Pr(#negative >= 10) =
                  Binomial(n = 22, x >= 10, p = 0.5) =  0.7383

         Two-sided test:
           Ho: median of preS - 10 = 0 vs.
           Ha: median of preS - 10 != 0
               Pr(#positive >= 12 or #negative >= 12) =
                  min(1, 2*Binomial(n = 22, x >= 12, p = 0.5)) =  0.8318

## Paired T Test
    . ttest postS=preS

    Paired t test
    ------------------------------------------------------------------------------
    Variable |     Obs        Mean    Std. Err.   Std. Dev.   [95% Conf. Interval]
    ---------+--------------------------------------------------------------------
       postS |      24      26.375    1.693779    8.297787    22.87115    29.87885
        preS |      24    10.79167    .9402034    4.606037    8.846708    12.73663
    ---------+--------------------------------------------------------------------
        diff |      24    15.58333    1.383019    6.775382    12.72234    18.44433
    ------------------------------------------------------------------------------
           mean(diff) = mean(postS - preS)                              t =  11.2676
       Ho: mean(diff) = 0                              degrees of freedom =       23

       Ha: mean(diff) < 0           Ha: mean(diff) != 0           Ha: mean(diff) > 0
            Pr(T < t) = 1.0000         Pr(|T| > |t|) = 0.0000          Pr(T > t) = 0.0000


## Sign

    . signrank postS = preS

    Wilcoxon signed-rank test
            sign |      obs   sum ranks    expected
    -------------+---------------------------------
        positive |       24         300         150
        negative |        0           0         150
            zero |        0           0           0
    -------------+---------------------------------
             all |       24         300         300

    unadjusted variance     1225.00
    adjustment for ties       -1.63
    adjustment for zeros       0.00
                         ----------
    adjusted variance       1223.38

    Ho: postS = preS
             z =   4.289
    Prob > |z| =   0.0000
    Exact Prob =   0.0000







# Two Sample Test
***

# One Way Analysis of variance
***

# Two and N Way Analysis of variance
***

# Factor Variables and Analysis of Covariance (ANCOVA)
***
