## 1.3 MEMBUAT VARIABEL BARU DENGAN **DESCRIBE**  
--------------------------------------------------------------

Di sini, kita akan gunakan database **auto**

    . sysuse auto, clear
    (1978 Automobile Data)
    . describe

    Contains data from C:\Program Files\Stata16\ado\base/a/auto.dta
      obs:            74                          1978 Automobile Data
     vars:            12                          13 Apr 2018 17:45
                                                  (_dta has notes)
    -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
                  storage   display    value
    variable name   type    format     label      variable label
    -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
    make            str18   %-18s                 Make and Model
    price           int     %8.0gc                Price
    mpg             int     %8.0g                 Mileage (mpg)
    rep78           int     %8.0g                 Repair Record 1978
    headroom        float   %6.1f                 Headroom (in.)
    trunk           int     %8.0g                 Trunk space (cu. ft.)
    weight          int     %8.0gc                Weight (lbs.)
    length          int     %8.0g                 Length (in.)
    turn            int     %8.0g                 Turn Circle (ft.)
    displacement    int     %8.0g                 Displacement (cu. in.)
    gear_ratio      float   %6.2f                 Gear Ratio
    foreign         byte    %8.0g      origin     Car type
    -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
    Sorted by: foreign


Di sini, kita akan melakukan pembuatan suatu variabel baru bernama **len_cm** yang merupakan variabel konversi antara length dalam inci ke sentimeter.

    . summarize length

        Variable |        Obs        Mean    Std. Dev.       Min        Max
    -------------+---------------------------------------------------------
          length |         74    187.9324    22.26634        142        233

    . generate len_cm = length*2.54

    . summarize len_cm

        Variable |        Obs        Mean    Std. Dev.       Min        Max
    -------------+---------------------------------------------------------
          len_cm |         74    477.3484     56.5565     360.68     591.82


























    . tabulate mpg

        Mileage |
          (mpg) |      Freq.     Percent        Cum.
    ------------+-----------------------------------
             12 |          2        2.70        2.70
             14 |          6        8.11       10.81
             15 |          2        2.70       13.51
             16 |          4        5.41       18.92
             17 |          4        5.41       24.32
             18 |          9       12.16       36.49
             19 |          8       10.81       47.30
             20 |          3        4.05       51.35
             21 |          5        6.76       58.11
             22 |          5        6.76       64.86
             23 |          3        4.05       68.92
             24 |          4        5.41       74.32
             25 |          5        6.76       81.08
             26 |          3        4.05       85.14
             28 |          3        4.05       89.19
             29 |          1        1.35       90.54
             30 |          2        2.70       93.24
             31 |          1        1.35       94.59
             34 |          1        1.35       95.95
             35 |          2        2.70       98.65
             41 |          1        1.35      100.00
    ------------+-----------------------------------
          Total |         74      100.00














































Di sini kita gunakan data **mpg**,

    . decribe mpg
    command decribe is unrecognized
    r(199);

    . describe

    Contains data from C:\Program Files\Stata16\ado\base/a/auto.dta
      obs:            74                          1978 Automobile Data
     vars:            14                          13 Apr 2018 17:45
                                                  (_dta has notes)
    -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
                  storage   display    value
    variable name   type    format     label      variable label
    -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
    make            str18   %-18s                 Make and Model
    price           int     %8.0gc                Price
    mpg             int     %8.0g                 Mileage (mpg)
    rep78           int     %8.0g                 Repair Record 1978
    headroom        float   %6.1f                 Headroom (in.)
    trunk           int     %8.0g                 Trunk space (cu. ft.)
    weight          int     %8.0gc                Weight (lbs.)
    length          int     %8.0g                 Length (in.)
    turn            int     %8.0g                 Turn Circle (ft.)
    displacement    int     %8.0g                 Displacement (cu. in.)
    gear_ratio      float   %6.2f                 Gear Ratio
    foreign         byte    %8.0g      origin     Car type
    len_cm          float   %9.0g
    isibaru         float   %9.0g
    -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
    Sorted by: foreign
         Note: Dataset has changed since last saved.

    . replace isibaru = 100 if(mpg<18)
    (18 real changes made)

    . replace isibaru = 200 if(mpg>=19)&(mpg<=23)
    (24 real changes made)

    . replace  isibaru    = 300 if (mpg >= 24)
    (23 real changes made)

    . tabulate isibaru

        isibaru |      Freq.     Percent        Cum.
    ------------+-----------------------------------
            100 |         18       27.69       27.69
            200 |         24       36.92       64.62
            300 |         23       35.38      100.00
    ------------+-----------------------------------
          Total |         65      100.00

    . tabulate mpg isibaru

       Mileage |             isibaru
         (mpg) |       100        200        300 |     Total
    -----------+---------------------------------+----------
            12 |         2          0          0 |         2
            14 |         6          0          0 |         6
            15 |         2          0          0 |         2
            16 |         4          0          0 |         4
            17 |         4          0          0 |         4
            19 |         0          8          0 |         8
            20 |         0          3          0 |         3
            21 |         0          5          0 |         5
            22 |         0          5          0 |         5
            23 |         0          3          0 |         3
            24 |         0          0          4 |         4
            25 |         0          0          5 |         5
            26 |         0          0          3 |         3
            28 |         0          0          3 |         3
            29 |         0          0          1 |         1
            30 |         0          0          2 |         2
            31 |         0          0          1 |         1
            34 |         0          0          1 |         1
            35 |         0          0          2 |         2
            41 |         0          0          1 |         1
    -----------+---------------------------------+----------
         Total |        18         24         23 |        65
