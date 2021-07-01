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
