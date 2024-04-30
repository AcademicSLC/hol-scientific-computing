Trapezoid 
=================

Trapezoid rule adalah salah satu metode untuk kalkulasi suatu integral dengan menggunakan pendekatan trapesium 

untuk mendapatkan nilai area dibawah kurva fungsi. Penjabaran dari trapezoid adalah sebagai berikut. 

diberikan suatu fungsi ``f(x) = x**2`` dengan interval [0, 2]. Implementasi langkah-langkah akan kita jabarkan 

sebagai berikut. 

 - bagi interval [0,2] menjadi beberapa bagian yang lebarnya sama.
 - hitung nilai fungsi tiap nilai pembagi interval. 
 - hitung luas trapesium untuk tiap interval. 
 - jumlahkan luas trapesium tiap tiap blok untuk mendapatkan nilai integral. 

Implementasi dari trapezoid adalah sebagai berikut. 

.. code-block:: python 
    import numpy as np 

kita bisa melakukan import library numpy terlebih dahulu. 

selanjutnya kita bisa melakukan inisialisasi variable dari numpy yang kita punya, kita akan menggunakan inisialisasi variable dan fungsi integral yang sebelumnya kita pakai

pada Riemann integral.

.. code-block:: python 
    a = 0
    b = 1
    n = 5 
    h = (b-a) / (n-1)
    x = np.linspace(a,b,n)
    f = x**2

Berikut adalah inisialisasi dan fungsi yang kita gunakan sebelumnya pada Riemann integral. kita akan menggunakannya juga pada trapezoid. 

.. code-block:: python 
    trapezoid = 2 * sum(f[0]+f[1:n-1] + f[n-1]) * (h/2)

Maka dari rumus berikut, kita sudah bisa mendapatkan nilai integral dengan menggunakan trapezoid rule. 