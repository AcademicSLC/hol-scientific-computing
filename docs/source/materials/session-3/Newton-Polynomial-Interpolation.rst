Newton Polynomial Interpolation 
======================================

.. note::

    Semua codingan yang ada disini jika di copy paste sama persis akan dianggap sebagai kecurangan


Newton Polynomial Interpolation adalah sebuah cara yang digunakan untuk menentukan dan menyesuaikan 

titik dari sekumpulan data yang tersedia.

Cara melakukan kalkulasi pada Newton Polynomial Interpolation adalah dengan mengkalikan variabel ``a`` dengan hasil kalkulasi ``(x-x0)...(x-xn)``.

Berikut adalah rumus yang digunakan untuk melakukan kalkulasi Newton Polynomial Interpolation.

.. image:: /images/newton_polynomial_interpolation_formula.png 
    :width: 300

Yang berbeda dari Newton Polynomial Interpolation dengan jenis Interpolation lainnya adalah terdapat koefisien ``a``, 

untuk koefisien ``a`` dimulai dari initial value dan akan berubah seiring bertambahnya suku persamaan yang ada. 

.. image:: /images/inital_newton_polynomial.png
    :width: 300

nilai initial pada variabel koefisien ``a0`` adalah nilai ``y0`` atau disebut sebagai nilai initial variabel ``y``.

Selanjutnya seiring bertambahnya suku persamaan, maka nilai koefisien ``a`` akan bertambah juga, yang dimulai dari ``a0`` hingga ``a1... + a2 + an``.

Nilai variable ``a`` terbaru bisa didapat dari rumus berikut. 

.. image:: /images/a1_newton_polynomial_interpolation.png 
    :width: 300 

dari rumus diatas bisa didapatkan bahwa nilai koefisien ``a1`` bisa didapatkan dari ``(y1-y0)``, ``y1`` merupakan nilai y saat ini, dan ``y0`` adalah initial. 

Setelah berhasil kita dapatkan langkah selanjutnya adalah kita bagi antara ``(y1-y0)`` dibagi dengan ``x1-x0``. 

.. image:: /images/a2_newton_polynomial_interpolation.png 
    :width: 300 

Hal tersebut juga berlaku untuk increment koefisien pada ``a2``.


Untuk koefisien ``a3`` hingga ``an``, memiliki struktur kalkulasi yang berbeda pada perhitungan koefisien ``a``, yaitu sebagai berikut. 

.. image:: /images/a3_newton_polynomial_interpolation.png
    :width: 300 

Selanjutnya kita akan melakukan implementasi dari newton polynomial interpolation sebagai berikut. 

.. code-block:: python 

    import numpy as np
    import matplotlib.pyplot as plt

Pertama-tama kita lakukan import library yang dibutuhkan untuk melakukan proses kalkulasi newton polynomial interpolation. 

.. code-block:: python 

    x = np.array([-5, -1, 0, 2])
    y = np.array([-2, 6, 1, 3])

Selanjutnya, kita siapkan data array yang kita panggil dengan menggunakan ``np.array``. 

.. code-block:: python 

    def divided_diff(x, y):
        n = len(y)
        coef = np.zeros([n, n])
        coef[:,0] = y
        
        for j in range(1,n):
            for i in range(n-j):
                coef[i][j] = \
            (coef[i+1][j-1] - coef[i][j-1]) / (x[i+j]-x[i])
                
        return coef

Langkah pertama yang kita lakukan adalah menghitung panjang nilai ``y`` atau salah satu array lainnya. 

Selanjutnya setelah kita berhasil mendapatkan panjang ``n`` kita akan membuat suatu array 2d dengan bentuk ``n*n`` yang dinisialisasi dengan nilai 0. 

Selanjutnya kita masukkan nilai ``y`` untuk mengubah nilai kolom index ke-0 dengan nilai ``y``. 

Sehingga hasil dari ``coef[:, 0] = y`` akan menjadi seperti gambar dibawah ini. 

.. image:: /images/result_coef_calculate.png 
    :width: 300 

Selanjutnya kita akan melakukan kalkulasi untuk mendapatkan nilai koefisien dengan menggunakan teknik pembagian diferensiasi. 

.. code-block:: python 

    def newton_poly(coef, x_data, x):
        n = len(x_data) - 1 
        p = coef[n]
        for k in range(1,n+1):
            p = coef[n-k] + (x -x_data[n-k])*p
        return p

Selanjutnya kita dapat membuat suatu function dengan bernama ``newton_poly`` yang ditujukan untuk menghitung newton polynomial dengan menggunakan rumus 

yang sudah ditujukan dan dibuat dengan menggunakan rumus newton yaitu ``a0 + a1(x-x0)``. 

.. code-block:: python 

    a_s = divided_diff(x, y)[0, :]

Selanjutnya kita dapat memanggil function ``divided_diff`` pada variable yang sudah kita siapkan, pembagian diferensiasi bisa didapatkan dari 

``x`` dan ``y`` array yang sudah diimplementasi dengan menggunakan ``np.array``. yang dimana kita akan menggil pada **row** ke-0 dan seluruh kolom yang tersedia pada 

pada **row** ke-0.

.. code-block:: python 

    x_new = np.arange(-5, 2.1, .1)
    y_new = newton_poly(a_s, x, x_new)

Selanjutnya kita dapat membuat suatu variable **x_new** yang berisikan array yang di-arange dari ``-5`` sampai ``2.1`` dengan 

step jarak sebanyak ``0.1``.

Setelah berhasil kita dapatkan nilai dari ``x_new``, kita bisa melakukan kalkulasi newton polynomial dengan memanggil variable ``newton_poly`` dan ditampung pada variable ``y_new``.

.. code-block:: python 
    
    plt.plot(x, y, 'bo')
    plt.plot(x_new, y_new)
    plt.show()

Selanjutnya kita bisa melakukan plotting pada hasil perhitungan pembagian diferensiasi dan dimasukkan kedalam 

rumus newton polynomial interpolation untuk mendapatkan nilai interpolasi yang sesuai. Berikut adalah **penjelasan lengkap** dari `Newton Polynomial Interpolation <https://pythonnumericalmethods.studentorg.berkeley.edu/notebooks/chapter17.05-Newtons-Polynomial-Interpolation.html>`_.

