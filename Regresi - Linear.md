# Regresi Linear Sederhana



### Example

__Sweetness of orange juice.__ <br>
The quality of the orange juice produced by a manufacturer (e.g., Minute Maid, Tropicana) is constantly monitored. <br>
There are numerous sensory and chemical components that combine to make the best tasting orange juice. For example, one manufacturer has developed a quantitative index of the ‘‘sweetness’’ of orange juice. (The higher the index, the sweeter the juice.) <br>
Is there a relationship between the sweetness index and a chemical measure such as the amount of water-soluble pectin (parts per million) in the orange juice?
<br><br>
Suppose a manufacturer wants to use simple linear regression to predict the sweetness __(y)__ from the amount of pectin __(x)__.
* Find the least squares line for the data.
* Interpret βˆ0 and βˆ1 in the words of the problem.
* Predict the sweetness index if amount of pectin in the orange juice is 300 ppm.
[Note: A measure of reliability of such a prediction is discussed in Section 3.9.]




      . regress SWEET PECTIN

            Source |       SS           df       MS      Number of obs   =        24
      -------------+----------------------------------   F(1, 22)        =      6.52
             Model |  .301401891         1  .301401891   Prob > F        =    0.0181
          Residual |  1.01693144        22  .046224156   R-squared       =    0.2286
      -------------+----------------------------------   Adj R-squared   =    0.1936
             Total |  1.31833333        23  .057318841   Root MSE        =      .215

      ------------------------------------------------------------------------------
             SWEET |      Coef.   Std. Err.      t    P>|t|     [95% Conf. Interval]
      -------------+----------------------------------------------------------------
            PECTIN |  -.0023106   .0009049    -2.55   0.018    -.0041872    -.000434
             _cons |   6.252068    .236622    26.42   0.000     5.761344    6.742792
      ------------------------------------------------------------------------------

Dari hasil regresi di atas dapat dibuat persamaan regresi <br>
__SWEET = 6.252068 -(0.0023106*PECTIN)__<br>
artinya :<br>
* Setiap peningkatan 1 ppm pectin akan mengakibatkan penurunan indeks kemanisan sebesar  0.0023106 (tanda negatif menunjukkan hubungan negatif/penurunan)
* Saat tidak ada pectin sama sekali, persamaan di atas menunjukkan tingkat kemanisan orange juice sebesar 6.252068
* Dari hasil regresi di atas, terlihat juga bahwa __R-squared       =    0.2286__ artinya pectin hanya berkontribusi sebesar 22.86 persen untuk menjelaskan tingkat kemanisan orange juice
* Dari __F(1, 22)        =      6.52__ dengan derajat kebebasan 1 dan 22 dan __Prob > F        =    0.0181__ (dalam hal ini p < .05), kita gagal menolak hipotesis Ho dengan kata lain __PECTIN dapat secara reliabel memprediksi nilai SWEET__



## Pengecekan Asumsi

A Summary of Steps to Follow in a Residual Analysis of the Simple Linear Regression Model
1. Check for a misspecified model by plotting the residuals against the independent variable in the model. A curvilinear trend detected in a plot implies that a quadratic term for that particular x variable will probably improve model adequacy (see Chapter 12).
2. Check for unequal variances (or, heteroscedasticity) by plotting the residuals against the predicted values . If you detect a pattern similar to one of those shown in Figure 10.22, refit the model using the appropriate variance-stabilizing transformation on y (see Table 10.8).
3. Check for nonnormal errors by constructing a stem-and-leaf display (or histogram) for the residuals.† If you detect extreme skewness in the data, then apply one of the transformations listed in Table 10.8 (see step 4).

### Example

__Sound waves from a basketball__ <br>
Journal of Physics (June 2010) study of sound waves in a spherical cavity, Exercise 10.7 (p. 496). You fit a straightline model relating frequency of sound waves (y) to number of resonances (x). <br>
Evaluate the adequacy of the model for predicting frequency of sound waves.
* Use the model to predict the sound wave frequency for the 10th resonance.
* Form a 90% confidence interval for the prediction, part Interpret the result.
* Suppose you want to predict the sound wave frequency for the 30th resonance. What are the dangers in making this prediction with the fitted model?
* Use the least squares prediction equation to calculate the residuals for the model.
* Plot the residuals against number of resonances (x). Do you detect a trend?
* Based on the residual plot, which assumption appears to be violated?
* What model modification do you recommend?

Hasil Regresi
    . regress Frequency Resonance

          Source |       SS           df       MS      Number of obs   =        24
    -------------+----------------------------------   F(1, 22)        =    885.28
           Model |  51085273.4         1  51085273.4   Prob > F        =    0.0000
        Residual |  1269508.44        22  57704.9292   R-squared       =    0.9758
    -------------+----------------------------------   Adj R-squared   =    0.9746
           Total |  52354781.8        23  2276294.86   Root MSE        =    240.22

    ------------------------------------------------------------------------------
       Frequency |      Coef.   Std. Err.      t    P>|t|     [95% Conf. Interval]
    -------------+----------------------------------------------------------------
       Resonance |   210.7652   7.083657    29.75   0.000     196.0746    225.4558
           _cons |   1469.351   101.2162    14.52   0.000     1259.442    1679.261
    ------------------------------------------------------------------------------

Pengujian Terhadap Nilai residual
***
    .  predict Frequencyhat
    (option xb assumed; fitted values)

    . label variable Frequencyhat "Frequency predicted from Resonance"

    . predict Frequencyres, resid

    . label variable Frequencyres "Residuals, Frequency predicted from Resonance"

    . summarize Frequency*

        Variable |        Obs        Mean    Std. Dev.       Min        Max
    -------------+---------------------------------------------------------
       Frequency |         24    4103.917    1508.739        979       6339
    Frequencyhat |         24    4103.917    1490.335   1680.117   6527.717
    Frequencyres |         24    6.76e-07    234.9383  -701.1166   275.5268

    . sktest Frequencyres

                        Skewness/Kurtosis tests for Normality
                                                              ------ joint ------
        Variable |        Obs  Pr(Skewness)  Pr(Kurtosis) adj chi2(2)   Prob>chi2
    -------------+---------------------------------------------------------------
    Frequencyres |         24     0.0150        0.0795        7.75         0.0207


Plotting Residuals
***
Opsi pertama tanpa smoothness, kedua dengan smoothness
    . graph twoway scatter Frequencyres Frequencyhat, yline(0)
    . graph twoway scatter Frequencyres Frequencyhat || lowess Frequencyres Frequencyhat ||, yline(0)
