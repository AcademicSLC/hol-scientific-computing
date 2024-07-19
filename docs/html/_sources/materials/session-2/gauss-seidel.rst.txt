System Linear Equation 
==================================

*System Linear Equation* adalah proses **kalkukalasi** dua atau lebih **suatu persamaan linear** untuk mendapatkan nilai dari suatu variabel. 

Terdapat berbagai cara untuk menyelesaikan *System Linear Equation*, akan tetapi pada mata kuliah Scientific Computing kalkulasi *System Linear Equation* yang dipelajari adalah *Gauss Seidel Linear Equation*. 

*Gauss Seidel Linear Equation*
-------------------------------------

*Gauss Seidel method* adalah proses **kalkulasi persamaan linear** yang menggunakan **iterative method**. Dengan menggunakan *Gauss Seidel Method* kita akan melakukan prediksi kalkulasi suatu nilai variable ``x`` yang dimana nilai akhir yang benar adalah ketika nilai ``x`` lebih kecil dari *threshold*. 

Berikut adalah contoh dari penerapan *Gauss Seidel* dengan contoh penerapan persaamaan linear yang akan digunakan. 

Contoh persamaan:

.. math::

    14x^1 + 1x^2 + 1x^3 = 6 

    3x^1 + 12x^2 + 3x^3 = 5

    7x^1 + 3x^2 + 13x^3 = 3

Proses penyelesaian persamaan linear dengan menggunakan *Gauss Seidel Method*. 

Pertama-tama lakukanlah pengecekan apakah persamaan linear merupakan *Diagonally Dominant*. Sebelum kita melakukan pengecekan *Diagonally dominant* kita harus menyiapkan **matrix** angka terlebih dahulu. 

.. code-block:: python

    Xs = [
        [
            [14, 1, 1], 
            [3, 12, 3], 
            [7, 3, 13]
        ]
    ]

    Ys = [
        [6,5,3]
    ]

Setelah menyiapkan **matrix** angka, selanjutnya adalah kita membuat suatu **function** yang bernama **isDiagonallyDominant**, function ini dibuat untuk melakukan pengecekan apakah data **matrix** yang disiapkan sudah memiliki data yang **diagonally dominant**. 

Di proses ini, kita akan menggunakan **function** ``np.diag`` yang dimana function ini bertujuan untuk mendapatkan nilai **diagonal** dari data matrix yang diberikan. Setelah berhasil mendapatkan nilai **diagonal** dari function tersebut, selanjutnya kita akan melakukan kalkulasi untuk mendapatkan nilai dari ``off_diag`` yang menunjukan berapa nilai angka selain dari ``diag`` tersebut. 

.. code-block:: python 

    def isDiagonallyDominant(x):
        diag = np.diag(np.abs(x))
        print(f"diag: {diag}")
        off_diag = np.sum(np.abs(x), axis = 1) - diag 
        print(f"{off_diag}")
        if np.all(diag > off_diag):
            return True 
        else:
            return False

Selanjut nya setelah function *isDiagonallyDominant* dibuat, buatlah function *Gauss Seidel* untuk melakukan proses validasi antara persamaan linear dengan epsilon. 

.. code-block:: python 

    def gauss_seidel(x, y, max_iter, eps):

        # parse ke array 
        x = np.array(x)
        y = np.array(y)

        init_val = np.zeros(np.shape(x)[0])

        diag = np.diag(x)
        x = -x 
        np.fill_diagonal(x, 0)

        for i in range(max_iter):
            new_val = np.array(init_val)

            for j, row in enumerate(x):
            new_val[j] = (y[j] + np.dot(row, new_val))/diag[j]
            
            ec = np.sqrt(np.dot(new_val-init_val, new_val-init_val))

            print(f"Iter {i}: {new_val}")

            if ec < eps:
            return True 
            
            init_val = new_val

        return False

Pada function *Gauss Seidel* dilakukan iterasi untuk mendapatkan nilai *eucledian distance* yang lebih kecil dari epsilon. Selanjutnya  kita buat variable ``init_val`` yang diisikan dengan ``np,zeros`` sebanyak size yang dimiliki oleh matrix ``x``. Kita isikan nilai ``init_val`` dengan nilai *zeros*.

Setelah itu, kita ambil diagonal dari ``x`` dengan menggunakan ``np.diag``. kemudian pada code ``x = -x`` kita pindah ruas x dari kiri ke kanan. Selanjutnya diagonal pada ``x`` kita rubah menjadi 0 dengan menggunakan ``np.fill_diagonal()``. Yang kemudian kita akan melakukan iterasi pada persamaan Linear

yang sudah diberikan untuk mendapatkan eucledian distance yang akan digunakan untuk melakukan validasi apakah persamaan linear atau matrix tersebut *konvergen* atau tidak. Yang dimana nilai matrix akan divalidasi dengan nilai epsilon atau thresehold. 

Selanjutnya kita akan melakukan print data pada persamaan matrix yang sudah dibuat.

.. code-block:: python

    for i, (x, y) in enumerate(zip(Xs, Ys)):
        if check_diag_dominant(np.array(x)):
            if gauss_seidel(x, y, 10, 0.01):
                print("Converged!")
            else:
                print("Not Converged")

Terakhir, kita akan melakukan iterasi pada matrix dengan menggunakan ``zip()`` untuk menggabungkan dua array dan menjabarkan nya pada variable ``(x, y)`` dan mengeceknya apakah matrix yang kita miliki adalah diagonal dominant yang akan return **True** atau **False**.

Dibawah ini merupakan *full code* dari implementasi proses *kalkulasi* **Gauss Seidel** yang diberikan. 

.. code-block:: python 

    # mempersiapkan dataset
    Xs = [
        [
            [14, 1, 1], 
            [3, 12, 3], 
            [7, 3, 13]
        ]
    ]

    Ys = [
        [6,5,3]
    ]

    # melakukan pengecekan gauss seidel diagonal dominant
    def isDiagonallyDominant(x):
        diag = np.diag(np.abs(x))
        print(f"diag: {diag}")
        off_diag = np.sum(np.abs(x), axis = 1) - diag 
        print(f"{off_diag}")
        if np.all(diag > off_diag):
            return True 
        else:
            return False
    
    # melakukan kalkulasi gauss seidel
     def gauss_seidel(x, y, max_iter, eps):

        # parse ke array 
        x = np.array(x)
        y = np.array(y)

        init_val = np.zeros(np.shape(x)[0])

        diag = np.diag(x)
        x = -x 
        np.fill_diagonal(x, 0)

        for i in range(max_iter):
            new_val = np.array(init_val)

            for j, row in enumerate(x):
            new_val[j] = (y[j] + np.dot(row, new_val))/diag[j]
            
            ec = np.sqrt(np.dot(new_val-init_val, new_val-init_val))

            print(f"Iter {i}: {new_val}")

            if ec < eps:
            return True 
            
            init_val = new_val

        return False
    
    # melakukan looping dengan menggunakan zip untuk mendapatkan setiap data yang digunakan pada matrix 
    for i, (x, y) in enumerate(zip(Xs, Ys)):
        if check_diag_dominant(np.array(x)):
            if gauss_seidel(x, y, 10, 0.01):
                print("Converged!")
            else:
                print("Not Converged")

Berikut adalah **link referensi** yang digunakan untuk `Gauss Seidel <https://pythonnumericalmethods.studentorg.berkeley.edu/notebooks/chapter14.04-Solutions-to-Systems-of-Linear-Equations.html>`_.
