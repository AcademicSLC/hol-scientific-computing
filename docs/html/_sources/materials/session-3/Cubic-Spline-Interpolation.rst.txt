Cubic Spline Interpolation 
====================================

.. note::

    Semua codingan yang ada disini jika di copy paste sama persis akan dianggap sebagai kecurangan


**Cubic Spline Interpolation** adalah salah satu metode interpolasi yang menggunakan *polinomial*(persamaan suku banyak)

**Cubic Spline Interpolation polinomial** dengan suku 3 (cubic) yang menghubungkan dua titik yang bersebalahan. 

.. code-block:: python 

    from scipy.interpolate import CubicSpline
    import numpy as np
    import matplotlib.pyplot as plt

Pada kode diatas terdapat 3 library yang akan digunakan yaitu ``CubicSpline``, ``numpy`` dan ``matplotlib.pyplot``.

``CubicSpline`` digunakan untuk melakukan kalkulasi cubic spline interpolation. Selanjutnya ``numpy`` digunakan untuk melakukan kalkulasi matematika 

dan ``matplotlib`` digunakan untuk melakukan plotting pada data yang sudah dikalkulasi dengan cubic spline interpolation. 

.. code-block:: python 

    x = [0, 1, 2]
    y = [1, 3, 2]

    f = CubicSpline(x, y, bc_type='natural')
    x_new = np.linspace(0, 2, 100)
    y_new = f(x_new)

Pada kode diatas, variable ``x`` merupakan titik koordinat pada x dan variable ``y`` merupakan titik koordinat dari y. 

Selanjutnya kita lakukan kalkulasi untuk CubicSpline dengan menggunakan function ``CubicSpline`` yang diimport dari library ``scipy``. 

Untuk parameter ``bc_type`` untuk menentukan kondisi batas turunan kedua adala 0. 

.. code-block:: python 

    plt.plot(x_new, y_new, 'b')
    plt.plot(x, y, 'ro')
    plt.title('Cubic Spline Interpolation')
    plt.xlabel('x')
    plt.ylabel('y')
    plt.show()

Selanjutnya kita bisa melakukan proses plotting dengan menggunakan variable yang sudah ditentukan pada initial dan 

variable yang didapatkan dari hasil kalkulasi cubic spline interpolation, yatu variable ``x_new`` dan ``y_new``. Dibawah ini merupakan **full code** implementasi dari *Cubic Spline Interpolation*. 

.. code:: python  

    from scipy.interpolate import CubicSpline
    import numpy as np
    import matplotlib.pyplot as plt

    x = [0, 1, 2]
    y = [1, 3, 2]

    f = CubicSpline(x, y, bc_type='natural')
    x_new = np.linspace(0, 2, 100)
    y_new = f(x_new)

    plt.plot(x_new, y_new, 'b')
    plt.plot(x, y, 'ro')
    plt.title('Cubic Spline Interpolation')
    plt.xlabel('x')
    plt.ylabel('y')
    plt.show()

Berikut merupakan **penjelasan lengkap** dari `cubic spline interpolation <https://pythonnumericalmethods.studentorg.berkeley.edu/notebooks/chapter17.03-Cubic-Spline-Interpolation.html>`_.