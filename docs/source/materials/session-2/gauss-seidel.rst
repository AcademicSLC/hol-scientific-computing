System Linear Equation 
==================================

*System Linear Equation* adalah proses kalkukalasi dua atau lebih suatu persamaan linear untuk mendapatkan nilai dari suatu variabel. 

Terdapat berbagai cara untuk menyelesaikan *System Linear Equation*, akan tetapi pada mata kuliah Scientific Computing kalkulasi *System Linear Equation* yang dipelajari adalah *Gauss Seidel Linear Equation*. 

*Gauss Seidel Linear Equation*
-------------------------------------

*Gauss Seidel method* adalah proses kalkulasi persamaan linear yang menggunakan **iterative method**. Dengan menggunakan *Gauss Seidel Method* kita akan melakukan prediksi kalkulasi suatu nilai variable *x* yang dimana nilai akhir yang benar adalah ketika nilai *x* lebih kecil dari *threshold*. 

Berikut adalah contoh dari penerapan *Gauss Seidel* dengan contoh penerapan persaamaan linear yang akan digunakan. 

Contoh persamaan:

14x1 + 1x2 + 1x3 = 6 

3x1 + 12x2 + 3x3 = 5

7x1 + 3x2 + 13x3 = 3

Proses penyelesaian persamaan linear dengan menggunakan *Gauss Seidel Method*. 

Pertama-tama lakukanlah pengecekan apakah persamaan linear merupakan *Diagonally Dominant*. 

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
Setelah itu, kita ambil diagonal dari ``x`` dengan menggunakan ``np.diag``. kemudian pada code ``x = -x`` kita pindah ruas x dari kiri ke kanan. Selanjutnya