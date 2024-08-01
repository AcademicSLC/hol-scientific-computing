**Numpy Method**
============================

Numpy adalah library eksternal yang dapat digunakan untuk melakukan kalkulasi matematika yang lebih advance daripada menggunakan python pada umumnya.

Ketika ingin memanggil function *numpy*, kita diharuskan untuk menginstall terlebih dahulu. 

Untuk melakukan proses install *numpy* dapat mengikuti **commmand prompt** dibawah ini.

.. code-block:: cmd 

    pip install numpy 

Setelah berhasil diinstall, maka *numpy* sudah siap untuk digunakan. 

Method - method pada numpy 
-----------------------------------

Setelah berhasil melakukan instalasi *numpy*, kita dapat menggunakan method - method numpy yang sudah digunakan. Berikut beberapa method pada numpy yang cukup sering digunakan.

* method numpy.
 - sign()
 - dot()
 - sum()
 - ones()
 - shape ()


numpy.sign(x)
-----------------
``numpy.sign()`` dapat digunakan untuk menentukan suatu nilai positif, negatif, atau nol pada parameter ``sign()`` yang dimasukkan. ``sign()`` akan return ``-1`` jika ``x < 0``, akan return ``0`` jika ``x == 0``, akan return ``1`` jika ``x > 1``.

Berikut contoh penerapan dari ``sign()``.

.. code:: python 

    np.sign([-5., 4.5])

.. console::
    
    array([-1.,  1.]) // output 


numpy.dot()
-------------------------

``numpy.dot()`` digunakan untuk melakukan perkalian dua buah bilangan. dengan menggunakan ``dot()`` kita bisa melakukan perkalian biasa ataupun matrix menggunakan ``dot``.

Berikut adalah contoh penerapan dari ``numpy.dot()``.

.. code-block:: python 
    np.dot(2,6)

    a = [[1, 0], [0, 1]]
    b = [[4, 1], [2, 2]]
    np.dot(a,b)

Maka hasil dari code diatas sebagai berikut.

.. console:: 
    12 
    array([[4, 1], [2, 2]]).


numpy.sum()
----------------------

``numpy.sum()`` dapat digunakan untuk melakukan kalkulasi penjumalahan pada array python.

Berikut adalah contoh penerapan dari ``numpy.sum()``.

.. code-block:: python 

    np.sum([0.5, 1.5])
    np.sum([[0, 1], [0, 5]], axis=0)
    np.sum([[0, 1], [0, 5]], axis=1)

Maka hasil dari code diatas adalah sebagai berikut.

.. console:: 

    2.0
    array([0, 6])
    array([1, 5])


numpy.ones()
------------------------

``np.ones()`` digunakan untuk return angka 1 pada field array yang baru. ``np.ones()`` membutuhkan parameter yaitu panjang array yang dibutuhkan.

Berikut adalah contoh dari penerapan ``np.ones()``.

.. code-block:: python

    np.ones(5)

Maka hasil dari code diatas adalah sebagai berikut. 

.. console:: 

    array([1., 1., 1., 1., 1.])


numpy.shape()
-------------------------

``numpy.shape()`` digunakan untuk return shape dari inisialisasi arrya yang sudah di deklarasi. 

Berikut adalah contoh dari penggunaan ``numpy.shape()``.

.. code-block:: python

    np.shape([[1, 3]])
    np.shape([0])

Maka hasil dari code diatas adalah sebagai berikut. 

.. console:: 
    (1, 2)
    (1,)