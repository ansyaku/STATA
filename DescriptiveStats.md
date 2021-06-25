
    . list in 1/5

         +------------------------------------------------------------------------------------------------------------------+
         | ids   gender         faith1           body         sad   relretrt     crelder   kidwntmn   agecats           bmi |
         |------------------------------------------------------------------------------------------------------------------|
      1. | 214     Male           Very     Very happy      Rarely          0    A little          3        20   25.63020897 |
      2. | 220     Male   Not importan     Very happy       Never          0    Somewhat          2        18   21.92470551 |
      3. | 455   Female           Very   Somewhat hap   Sometimes          0   Very much          3        20    21.2547245 |
      4. | 560   Female   Extremely im     Very happy      Rarely          3   Very much          5        21    23.5650959 |
      5. | 794   Female       Not very   Somewhat hap       Never          0    Somewhat          3        19   20.98025703 |
         +------------------------------------------------------------------------------------------------------------------+


Untuk membuat distribusi frekuensi, gunakan **tab body**

    . tab body

      (body_w3) P:3. |
     In general, how |
    happy or unhappy |
        are you with |
       your body and |
               physi |      Freq.     Percent        Cum.
    -----------------+-----------------------------------
        Very unhappy |         68        2.70        2.70
    Somewhat unhappy |        389       15.42       18.11
             Neither |        234        9.27       27.39
      Somewhat happy |        953       37.77       65.16
          Very happy |        879       34.84      100.00
    -----------------+-----------------------------------
               Total |      2,523      100.00

di sorted berdasarkan frekuensi terbesar ke frekuensi terkecil dengan opsi **sort**

    . tab body, sort

      (body_w3) P:3. |
     In general, how |
    happy or unhappy |
        are you with |
       your body and |
               physi |      Freq.     Percent        Cum.
    -----------------+-----------------------------------
      Somewhat happy |        953       37.77       37.77
          Very happy |        879       34.84       72.61
    Somewhat unhappy |        389       15.42       88.03
             Neither |        234        9.27       97.30
        Very unhappy |         68        2.70      100.00
    -----------------+-----------------------------------
               Total |      2,523      100.00

mencari distribusi frekuensi beberapa variabel sekaligus :

    . tab1 body faith1

    -> tabulation of body  

      (body_w3) P:3. |
     In general, how |
    happy or unhappy |
        are you with |
       your body and |
               physi |      Freq.     Percent        Cum.
    -----------------+-----------------------------------
        Very unhappy |         68        2.70        2.70
    Somewhat unhappy |        389       15.42       18.11
             Neither |        234        9.27       27.39
      Somewhat happy |        953       37.77       65.16
          Very happy |        879       34.84      100.00
    -----------------+-----------------------------------
               Total |      2,523      100.00

    -> tabulation of faith1  

    (faith1_w3) F:1. How |
            important or |
          unimportant is |
      religious faith in |
            shaping how  |      Freq.     Percent        Cum.
    ---------------------+-----------------------------------
     Extremely important |        472       18.68       18.68
                    Very |        605       23.94       42.62
                Somewhat |        744       29.44       72.06
                Not very |        370       14.64       86.70
    Not important at all |        336       13.30      100.00
    ---------------------+-----------------------------------
                   Total |      2,527      100.00

menggunakan conditional di dalam tab

hanya yang gender
    . tab body if gender==0

      (body_w3) P:3. |
     In general, how |
    happy or unhappy |
        are you with |
       your body and |
               physi |      Freq.     Percent        Cum.
    -----------------+-----------------------------------
        Very unhappy |         21        1.71        1.71
    Somewhat unhappy |        143       11.65       13.37
             Neither |        117        9.54       22.90
      Somewhat happy |        442       36.02       58.92
          Very happy |        504       41.08      100.00
    -----------------+-----------------------------------
               Total |      1,227      100.00


hanya yang gender
    .  tab body if gender==1

      (body_w3) P:3. |
     In general, how |
    happy or unhappy |
        are you with |
       your body and |
               physi |      Freq.     Percent        Cum.
    -----------------+-----------------------------------
        Very unhappy |         47        3.63        3.63
    Somewhat unhappy |        246       18.98       22.61
             Neither |        117        9.03       31.64
      Somewhat happy |        511       39.43       71.06
          Very happy |        375       28.94      100.00
    -----------------+-----------------------------------
               Total |      1,296      100.00