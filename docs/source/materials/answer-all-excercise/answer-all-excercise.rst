Answer All Excercise 
==========================

.. note::

    Semua codingan yang ada disini jika di copy paste sama persis akan dianggap sebagai kecurangan


Dibawah ini merupakan data terkait **answer jawaban** pada setiap **mini practice** yang terdapat pada setiap **session**. 

Answer mini practice session 1
--------------------------------------

.. code:: python 

    # Membuat list mobil dengan data yang diberikan
    mobil = ["Toyota", "Honda", "Toyota", "Wuling"]

    # Menampilkan data list mobil
    print("Data list mobil sebelum menghapus duplikat:", mobil)

    # Menghapus data duplikat dengan mengubah list menjadi set dan kembali menjadi list
    mobil = list(set(mobil))

    # Menampilkan data list mobil setelah menghapus duplikat
    print("Data list mobil setelah menghapus duplikat:", mobil)

.. code:: console 

    Data list mobil sebelum menghapus duplikat: ['Toyota', 'Honda', 'Toyota', 'Wuling']
    Data list mobil setelah menghapus duplikat: ['Honda', 'Wuling', 'Toyota']


Answer mini practice session 2
-------------------------------------

.. code:: python 

        import numpy as np
    matrix_x = [
        [
                [9,1,4],
                [1,2,1], 
                [7,2,8]
            ],
            [
                [10,2,3],
                [5,7,1], 
                [1,3,4]
            ]
    ]

    matrix_y = [
        [10,4,12], 
        [21,9,11]
    ]


    #check diagonally dominant
    def check_diag_dominant(matrix):
    diag = np.diag(np.abs(matrix))
    except_diagonal = np.sum(np.abs(matrix), axis=1) - diag
    print(f"except : {except_diagonal}")
    # 1
    # for i in range(len(diag)):
    #   if diag[i] < except_diagonal[i]:
    #     print("Not diagonally dominant")
    #     return False

    # 2
    if np.all(diag > except_diagonal):
        return True

    print("Not diagonally dominant")
    return False

    # solve using gauss seidel
    def gauss_seidel(matrix_1, matrix_2, iter, epsilon):

    matrix_1 = np.array(matrix_1)
    matrix_2 = np.array(matrix_2)

    inital_value = np.zeros(np.shape(matrix_1)[0])

    diagonals = np.diag(matrix_1)
    matrix_1 = -matrix_1
    np.fill_diagonal(matrix_1, 0)

    for i in range(iter):
        new_value = np.array(inital_value)

        for j, row in enumerate(matrix_1):
        new_value[j] = (matrix_2[j] + np.dot(row, new_value))/diagonals[j]

        euclidian_dist = np.sqrt(np.dot(new_value - inital_value, new_value - inital_value))
        print(f"dist {np.dot(new_value - inital_value, new_value - inital_value)}")
        print(f"iteration {i} : {new_value}")
        if euclidian_dist < epsilon:
        return True

        inital_value = new_value

    return False

    for i, (matrix_x, matrix_y) in enumerate(zip(matrix_x, matrix_y)):
    if check_diag_dominant(np.array(matrix_x)):
        if gauss_seidel(matrix_x, matrix_y, 10, 0.01):
        print("Converged!")
        else:
        print("Cannot converged at this iteration!")

Answer session mini practice 3 
-------------------------------------

.. code:: python 

    import numpy as np
    from scipy import optimize
    import matplotlib.pyplot as plt

    # least square regression 
    x = [
            10, 2, 11, 
            21, 23, 24, 
            30, 22, 45, 
            46, 50, 1
        ]

    y = [
            1, 2, 3,
            90, 85, 21, 
            43, 31, 21, 
            54, 34, 11
        ]

    x = np.array(x)
    y = np.array(y)

    # assemble matrix A
    A = np.vstack([x, np.ones(len(x))]).T

    # turn y into a column vector
    y = y[:, np.newaxis]

    alpha = np.dot((np.dot(np.linalg.inv(np.dot(A.T,A)),A.T)),y)
    print(alpha)

    # plot the results
    plt.figure(figsize = (10,8))
    plt.plot(x, y, 'b.')
    plt.plot(x, alpha[0]*x + alpha[1], 'r')
    plt.xlabel('x')
    plt.ylabel('y')
    plt.show()


Answer mini practice session 4 
-----------------------------------------

- **excercise 1**

.. code:: python 

    def f(x):
        return 2*x**2 + x - 1

    def g(x):
        return 4*x 

    def newton_raph(x0, tol):
        x1 = x0 - f(x0)/g(x0)

        if(np.abs(f(x1)) < tol ):
            print(f" Root= {x1}")
            return 
    
    newton_raph(x1, tol)

    newton_raph(8,0.1)

- **excercise 2** 

.. code:: python 

    # bisection 
    import numpy as np

    def f(x):
    return x**2 - 5

    def my_bisection(f, a, b, tol=0.1): 
        # approximates a root, R, of f bounded 
        # by a and b to within tolerance 
        # | f(m) | < tol with m the midpoint 
        # between a and b Recursive implementation
        
        # check if a and b bound a root
        if np.sign(f(a)) == np.sign(f(b)):
            raise Exception(
            "The scalars a and b do not bound a root")
            
        # get midpoint
        m = (a + b)/2
        
        if np.abs(f(m)) < tol:
            # stopping condition, report m as root
            return m
        elif np.sign(f(a)) == np.sign(f(m)):
            # case where m is an improvement on a. 
            # Make recursive call with a = m
            return my_bisection(f, m, b, tol)
        elif np.sign(f(b)) == np.sign(f(m)):
            # case where m is an improvement on b. 
            # Make recursive call with b = m
            return my_bisection(f, a, m, tol)

    result = my_bisection(f, 2, 4)
    print(result)

Answer mini practice session 5 
------------------------------

.. code:: python 

    # riemann
    def f(x):
    return 2*x**5+1

    a = 2
    b = 5
    n = 10

    lebar_kotak = (b-a)/(n-1)

    x = np.linspace(a,b,n)
    y = f(x)

    left_riemann = lebar_kotak * sum(y[:n-1])
    right_riemann = lebar_kotak * sum(y[1:])

    x_mid = (x[:n-1] + x[1:])/2
    y_mid = f(x_mid)
    mid_riemann = lebar_kotak * sum(y_mid)

    print(f"left riemann: {left_riemann}")
    print(f"right riemann: {right_riemann}")
    print(f"mid riemann: {mid_riemann}")



