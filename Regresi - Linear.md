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
