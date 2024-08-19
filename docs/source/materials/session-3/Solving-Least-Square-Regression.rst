Solving Problem dengan Menggunakan Persamaan Least Square Regression
===============================================================================

.. note::

    Semua codingan yang ada disini jika di copy paste sama persis akan dianggap sebagai kecurangan


Sekarang, saatnya kita melakukan penyelesaian permasalahan persamaan dengan menggunakan metode Least Square Regression.

Terdapat 2 cara penyelesaian dengan metode Least Square Regression, yaitu sebagai berikut: 
    - direct inverse 
    - pseudo inverse 

Berikut adalah 2 metode yang bisa menyelesaiakan persamaan dengan menggunakan metode Least Square Regression, kita akan membahas dari ``direct inverse`` terlebih dahulu.

.. code-block:: python 

    import numpy as np 
    import matplotlib.pyplot as plt 

yang akan kita lakukan pertama kali adalah melakukan import library yang dibutuhkan untuk melakukan least square regression. Berikut adalah library yang dibutuhkan yaitu
``numpy`` dan ``matplotlib``. 

selanjutnya kita siapkan terlebih dahulu variable ``x`` yang berisikan matrix dan juga variable ``y``. 

selanjutnya kita ubah setiap nilai array yang sudah disediakan menjadi numpy array dengan menggunakan ``np.array``. 

.. code-block:: python 

    x = [1,3,5,7,9,11,13,15]
    y = [2,4,6,8,10,12,14,16]
    x = np.array(x)
    y = np.array(y)

selanjutnya kita siapkan nilai initial dari variable ``A`` yang berisikan nilai 1 dengan menggunakan ``np.ones`` sepanjang ``length`` array dari x. 

yang kita kombinasikan dengan ``np.vstack``, ``vstack`` ini bisa digunakan untuk mengubah stack array menjadi vertical dalam bentuk row (baris). yang kemudian array yang sudah kita operasikan dengan ``vstack`` 

kita lakukan proses *transpose* dengan menggunakan symbol ``.T``

.. code-block:: python 

    A = np.vstack([x, np.ones(len(x))]).T 

Selanjutnya kita bentuk array ``y`` menjadi kolom vector dengan menggunakan ``np.newaxis``.

.. code-block:: python 

    y = y[:, np.newaxis]

Setelah kita mempersiapkan variable ``x`` dan ``y`` menjadi bentuk kolom vector, kita lakukan proses 

analisis dan kalkukalasi dengan menggunakan proses *direct inverse* dari formula sebagai berikut ``(A^T*A)^-1 * A^T*A``.

.. code-block:: python 
    alpha = np.dot((np.dot(np.linalg.inv(np.dot(A.T,A)),A.T)),y)
    print(alpha)

hasil dari kalkulasi *direct inverse* mendapatkan hasil sebagai berikut.

.. code-block:: python 

    [[1.]
     [1.]]

hasil dari kalkulasi *direct inverse* berisikan 2 index array, index ke-0 menandakan gradien dari garis persamaan dan index ke-1 dari dari array menandakan sebagai konstanta.

Selanjutnya setelah kita mendapatkan kedua data tersebut, langkah selanjutnya adalah melakukan visualisasi garis persamaan dengan menggunakan metode Least Square Regression (direct inverse). 

.. code-block:: python 
    
    plt.plot(x, y, 'b.')
    plt.plot(x, alpha[0]*x + alpha[1], 'r')
    plt.xlabel('x')
    plt.ylabel('y')
    plt.show()

Selanjutnya kita bisa melakukan proses plotting dengan menggunakan variable ``x`` dan ``y`` beserta persamaan garis larus 

dengan mengganti variable ``y`` pada proses plot kedua dengan formula ``y = mx + b``, variable ``m`` ditandakan dengan **alpha** variable index ke-0, dan **alpha** index ke-1. 

Selanjutnya kita bisa memanggil ``plt.show()`` untuk menampilkan hasil plotting. 

.. image:: /images/result_least_square.png 
    :width: 300 


