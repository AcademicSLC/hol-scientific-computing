Least Square Regression 
=================================

.. note::

    Semua codingan yang ada disini jika di copy paste sama persis akan dianggap sebagai kecurangan


Least Square Regression adalah suatu teknik analisis data yang cukup sering digunakan dalam penelitian. 

Least square regression dikaitkan erat dengan regresi linear. Least square regression bisa digunakan untuk melakukan analisis antara variable dependent dan independent pada suatu proses analisis data. 

Least square regression digunakan untuk memprediksi suatu data di masa mendatang. Contohnya seperti memprediksi data penjualan, hasil panen suatu perkebunan, dan pengeluaran yang dibutuhkan pada suatu periodik waktu tertentu. 

Least square regression digunakan untuk menentukan nilai koefisien pada model regresi. Pada intinya, Least square regression digunakan untuk menentukan data model regresi yang memiliki nilai error terkecil.


Misalkan kita diberikan suatu persamaan linear sebagai berikut. 

.. code-block:: python 

    yi = mx + b + c

dan persamaan regresi linear dari least square regression adalah sebagi berikut.

.. code-block:: python
    
    yi = mx + b 

persamaan untuk menentukan error antara kedua persamaan diatas adalah sebagai berikut.

.. code-block:: python 

    e = yi - yi 

Untuk menyelasaikan suatu persamaan dengan menggunakan least square regression kita bisa menggunakan formula dibawah berikut.

.. math::

    𝛽=(𝐴^𝑇 \times 𝐴)^−1 \times 𝐴^𝑇 \times 𝑌 

``(A^T*A)^-1 * A^T*A`` disebut sebagai pseudoinverse, variable ``A`` sendiri merupakan matriks yang digunakan. 

``A^T`` digunakan untuk melakukan *transpose* matrix dari ``A``. Berikut adalah **penjelasan lengkap** dari `Least Square Regression <https://pythonnumericalmethods.studentorg.berkeley.edu/notebooks/chapter16.00-Least-Squares-Regression.html>`_.



