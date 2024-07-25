Python Basics
===================

Apa itu Python? 
-------------------

Python adalah bahasa pemrograman yang dibuat oleh Guido van Rossum dan diperkenalkan pada tahun 1991. 

Banyak manfaat yang bisa didapatkan dari pembuatan aplikasi dengan menggunakan python:
 - Membuat web server 
 - Membuat model Artificial Intelligence (Machine Learning, Deep Learning, Natural Language Processing dan lainnya).
 - Backend development 
 - Membuat data visualisasi

Output pada Python
----------------------

Untuk melakukan output pada python bisa menggunakan  keyword ``print()``.

.. code:: python 

    print('Hello world')


.. console:: 

    Hello world


Input pada Python 
-----------------------
Untuk melakukan input pada python bisa menggunakan keyword ``input()``. 

.. code:: python 

    x = input() // data yag dimasukkan: Budi 
    print(x)

.. console:: 

    Budi // output 


Comment pada python 
-----------------------
Comment adalah sebuah syntax yang tidak akan di eksekusi ketika program di eksekusi, syntax comment pada Python adalah ``#``.

.. code:: python 

    # Artificial Intelligence 

.. console::

    // Output tidak keluar karena di comment. 



Tipe data dan variable pada Python
------------------------

Tipe data adalah suatu value yang merepresentasikan nilai dari suatu data. 

Macam-macam tipe data pada python adalah sebagai berikut:
    -  int 
    - float 
    - string 
    - boolean

**Variable**

Variable adalah suatu tempat yang dapat digunakan untuk menampung data pada Python.

Penerapan variable sebagai berikut:

.. code:: python 

    x = "Ahmad" // `x` sebagai variable dan "Ahmad" sebgai nilai string 
    print(x)

.. console:: 

    Ahmad // hasil output 


**Casting**
Casting adalah proses convert nilai data pada Python yang digunakan untuk convert dari suatu tipe data ke tipe data lainnya. 

Penerapan *casting* akan saya contohkan sebagai berikut.

.. code:: python

    number = 1 // variable number menampung int 
    number_str = str(number) // convert nilai int menjadi string 
    print(number_str)

.. console:: 

    1 // dalam bentuk string 


**Get type of value**
Dalam python terdapat *build-in* function yang digunakan untuk mendapatkan data 

.. code:: python 

    x = 10 
    print(type(x))

.. console:: 
    
    <type 'int'>


