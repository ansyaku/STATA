# Charting

# Histogram

    . histogram bmi
    (bin=33, start=14.014952, width=1.4993336)

![Histogram](https://github.com/ansyaku/STATA/blob/main/img/BMI.png)
<br>
    . histogram bmi, frequency normal
    (bin=33, start=14.014952, width=1.4993336)

![Histogram Normal](https://github.com/ansyaku/STATA/blob/main/img/BMINormal.png)


# Box Plot
    .  graph box sad, over(gender)
![Boxplot](https://github.com/ansyaku/STATA/blob/main/img/Boxplot.png)

# QQ Plot

    . qnorm bmi
![QQPlot](https://github.com/ansyaku/STATA/blob/main/img/QQplot.png)
