# Regresi Logistik
***

Regresi logistik merupakan regresi yang menghubungkan antara satu atau beberapa variabel independen (variabel bebas) dengan **variabel dependen yang berupa kategori biner (dichotomous)**, biasanya 0 dan 1. <br>

Regresi logistik berusaha untuk membedakan :
1. Apakah suatu email spam atau bukan spam?
2. Apakah hari ini hujan atau tidak hujan?
3. Apakah nilai UN, keikusertaan bimbel berpengaruh dalam menentukan mahasiswa lulus SNMPTN atau tidak?

Asumsi Dalam Regresi Logistik:
1. Variabel dependen harus bersifat biner.
2. Tidak boleh ada outliers di dalam data
3. Tidak boleh ada korelasi tinggi antar variabel prediktor (multicollinearity). Bisa dinilai menggunakan  correlation matrix antar prediktor. Tabachnick and Fidell (2013) menyarankan bahwa selama koefisien korelasi antar variabel independen kurang dari 0.90, asumsi terpenuhi.

Formula regresi logistik:<br>
<img src="http://www.sciweavers.org/tex2img.php?eq=P%3D%5Cfrac%7B1%7D%7B1%2Be%5E%7Ba%2BbX%7D%7D&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0" align="center" border="0" alt="P=\frac{1}{1+e^{a+bX}}" width="115" height="43" />


## Tipe-tipe regresi logistik:
1. Binary Logistic Regression
2. Multinomial Logistic Regression
3. Ordinal Logistic Regression


## Loss Function
A loss function is a measure of fit between a mathematical model of data and the actual data. We choose the parameters of our model to minimize the badness-of-fit or to maximize the goodness-of-fit of the model to the data. <br>

<img src="http://www.sciweavers.org/tex2img.php?eq=odds%3D%5Cfrac%7BP%7D%7B1-P%7D&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0" align="center" border="0" alt="odds=\frac{P}{1-P}" width="112" height="43" />

sehingga<br>
<img src="http://www.sciweavers.org/tex2img.php?eq=log%28odds%29%3Dlogit%28P%29%3Dln%28%5Cfrac%7BP%7D%7B1-P%7D%29&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0" align="center" border="0" alt="log(odds)=logit(P)=ln(\frac{P}{1-P})" width="267" height="43" />










    . logit admit gre gpa i.rank

    Iteration 0:   log likelihood = -249.98826  
    Iteration 1:   log likelihood = -229.66446  
    Iteration 2:   log likelihood = -229.25955  
    Iteration 3:   log likelihood = -229.25875  
    Iteration 4:   log likelihood = -229.25875  

    Logistic regression                             Number of obs     =        400
                                                    LR chi2(5)        =      41.46
                                                    Prob > chi2       =     0.0000
    Log likelihood = -229.25875                     Pseudo R2         =     0.0829

    ------------------------------------------------------------------------------
           admit |      Coef.   Std. Err.      z    P>|z|     [95% Conf. Interval]
    -------------+----------------------------------------------------------------
             gre |   .0022644    .001094     2.07   0.038     .0001202    .0044086
             gpa |   .8040377   .3318193     2.42   0.015     .1536838    1.454392
                 |
            rank |
              2  |  -.6754429   .3164897    -2.13   0.033    -1.295751   -.0551346
              3  |  -1.340204   .3453064    -3.88   0.000    -2.016992   -.6634158
              4  |  -1.551464   .4178316    -3.71   0.000    -2.370399   -.7325287
                 |
           _cons |  -3.989979   1.139951    -3.50   0.000    -6.224242   -1.755717
------------------------------------------------------------------------------


The likelihood ratio chi-square of41.46 with a p-value of 0.0001 tells us that our model as a whole fits significantly
better than an empty model (i.e., a model with no predictors).

In the table we see the coefficients, their standard errors, the z-statistic, associated p-values, and the 95% confidence interval of the coefficients.  Both gre and gpa are statistically significant, as are the three indicator variables for rank. The logistic regression coefficients give the change in the log odds of the outcome for a one unit increase in the predictor variable.
For every one unit change in gre, the log odds of admission (versus non-admission) increases by 0.002.
For a one unit increase in gpa, the log odds of being admitted to graduate school increases by 0.804.
The indicator variables for rank have a slightly different interpretation. For example, having attended an undergraduate institution with rank of 2, versus an institution with a rank of 1, decreases the log odds of admission by 0.675.


Nilai odds

    . logit, or

    Logistic regression                             Number of obs     =        400
                                                    LR chi2(5)        =      41.46
                                                    Prob > chi2       =     0.0000
    Log likelihood = -229.25875                     Pseudo R2         =     0.0829

    ------------------------------------------------------------------------------
           admit | Odds Ratio   Std. Err.      z    P>|z|     [95% Conf. Interval]
    -------------+----------------------------------------------------------------
             gre |   1.002267   .0010965     2.07   0.038      1.00012    1.004418
             gpa |   2.234545   .7414652     2.42   0.015     1.166122    4.281877
                 |
            rank |
              2  |   .5089309   .1610714    -2.13   0.033     .2736922    .9463578
              3  |   .2617923   .0903986    -3.88   0.000     .1330551    .5150889
              4  |   .2119375   .0885542    -3.71   0.000     .0934435    .4806919
                 |
           _cons |   .0185001   .0210892    -3.50   0.000     .0019808    .1727834
    ------------------------------------------------------------------------------
    Note: _cons estimates baseline odds.

Now we can say that for a one unit increase in gpa, the odds of being admitted to graduate school (versus not being admitted) increase by a factor of 2.23. For more information on interpreting odds ratios see our FAQ page How do I interpret odds ratios in logistic regression? .

bila dibaca menggunaan probabiltas


    . margin rank, atmeans

    Adjusted predictions                            Number of obs     =        400
    Model VCE    : OIM

    Expression   : Pr(admit), predict()
    at           : gre             =       587.7 (mean)
                   gpa             =      3.3899 (mean)
                   1.rank          =       .1525 (mean)
                   2.rank          =       .3775 (mean)
                   3.rank          =       .3025 (mean)
                   4.rank          =       .1675 (mean)

    ------------------------------------------------------------------------------
                 |            Delta-method
                 |     Margin   Std. Err.      z    P>|z|     [95% Conf. Interval]
    -------------+----------------------------------------------------------------
            rank |
              1  |   .5166016   .0663153     7.79   0.000     .3866261    .6465771
              2  |   .3522846   .0397848     8.85   0.000     .2743078    .4302614
              3  |    .218612   .0382506     5.72   0.000     .1436422    .2935819
              4  |   .1846684   .0486362     3.80   0.000     .0893432    .2799937
