Newton Raphson Method 
=============================

.. note::

    Semua codingan yang ada disini jika di copy paste sama persis akan dianggap sebagai kecurangan


**Newton raphson** adalah sebuah teknik yang digunakan untuk memecahkan permasalahan dari nilai 

**akar-akar** pada suatu *persamaan*. **Newton raphson** ditemukan oleh **Sir Isaac Newton** dan **Joseph Raphson**. 

**Newton raphson** adalah *algoritma* untuk menentukan nilai akar pada suatu *persamaan*. dengan menggunakan nilai 

**initial** untuk menentukan *akar-akar* selanjutnya. Rumus untuk *menentukan akar* pada **Newton Raphson** adalah sebagai berikut. 

.. code-block:: python 

    x1 = x0 - f(x0)/f'(x0)

x0 = initial value 
f = adalah persamaan initial 
f' = adalah turunan dari persamaan intial

Selanjutnya kita akan menjelaskan implementasi dari Newton raphson sebagai berikut. 

.. code-block:: python

    import numpy as np 

Pertama-tama kita bisa import library numpy terlebih dahulu. 

Kemudian masukkan intial persamaan yang sudah ditentukan sebagai berikut. 

untuk persamaannya adalah ``x^2 - 2 = 0``.

.. math:: 

    x^2-2=0


.. code-block:: python 

    def f(x):
        return x**2 - 2

Setelah kita memasukkan *initial persamaannya*, selanjutnya adalah menyiapkan

*persamaan turunan* dari persamaan initial sebagai berikut. 

.. code-block:: python 
    
    def g(x): 
        return 2*x

Selanjutnya adalah siapkan function dengan nama ``newton_raph`` sebagai berikut.

.. code-block:: python 

    def newton_raph(x0, tol):
        x1 = x0 - f(x0) / g(x0)

        if np.abs(f(x1)) < tol: 
            print(x1)
            return 
        
        newton_raph(x1, tol)

Selanjutnya adalah kita masukkan rumus dari newton raphson untuk menentukan root nya yaitu dengan rumus 

``x0 - f(x0) / g(x0)`` kemudian kita dapat melakukan validasi apakah nilai absolute dari ``f(x1)`` memiliki 

nilai lebih kecil dari tolerance, jika iya maka akan kita print nilai root nya dan kemudian kita return. 

Jika tidak maka akan kita panggil function ``newton_raph`` secara recursive. 

Terakhir tinggal kita panggil fucntion **newton_raph** sebagai berikut.

.. code-block:: python 

    newton_raph(2, 0.1)

Maka hasilnya adalah sebagai berikut. 

.. code-block:: python 

    1.4166666666666667

Selanjutnya, kita akan menampilkan implementasi **full code** dari **Newton Raphson** berikut. 

.. code:: python 

    import numpy as np 

    def newton_raph(x0, tol):
        x1 = x0 - f(x0) / g(x0)

        if np.abs(f(x1)) < tol: 
            print(x1)
            return 
        
        newton_raph(x1, tol)
    
    newton_raph(2, 0.1)

Berikut adalah **penjelasan lengkap** dari `Bisection method <https://pythonnumericalmethods.studentorg.berkeley.edu/notebooks/chapter19.03-Bisection-Method.html>`_.