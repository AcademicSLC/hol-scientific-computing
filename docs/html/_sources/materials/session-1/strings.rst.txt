String
==================

.. note::

    Semua codingan yang ada disini jika di copy paste sama persis akan dianggap sebagai kecurangan


String digunakan untuk merepresentasikan suatu value yang bersifat kata atau kalimat. String berisikan banyak character yang ketika digabung menjadi satu kata atau kalimat yang solid. Inisialisasi *string* pada python menggunakan tanda ``'`` atau ``"``.

contoh dari aplikasi `string` pada python sebgaia berikut: 

.. code:: python 

    x_str = "Budi Wijaya"

.. code:: python  

    print(x_str) // "Budi wijaya"


Multiline String
--------------------

Multiline string bisa digunakan untuk menulis string dalam bentuk beberapa baris. 

contoh aplikasi `multiline string` pada python adalah sebagai berikut:

.. code:: python 

    x_row = """
    Saya suka naik odong-odong, 
    ketika naik odong-odong saya merasa bahagia. 
    """

.. code:: python  

    print(x_row)


String adalah kumpulan dari character
-----------------------------------------
String terbentuk dari kumpulan banyak character yang terkumpul menjadi satu kesatuan kata atau kalimat. 

Berikut saya contohkan bagaimana cara mengambil satu character dari String yang diinisialisasi.

.. code:: python 

    a = "Jordy Wira"
    print(a[1]) // mengambil string `a` pada index pertama 

.. code:: python 
    o // hasil print index 



Slicing pada String 
-----------------------

Slicing merupakan proses pengambilan index python dari start index tertentu ke index akhir yang ditentukan.


.. code:: python 

    name = "Budiman"
    print(name[0:3])

.. code:: python  

    Bud // hasil output 



Concatenate String 
-------------------------

Concatenate adalah proses menambahkan satu String dengan String baru lainnya.

.. code:: python 

    a = "Gajah"
    b = "Air"
    print(a+b)

.. code:: python  

    Gajah Air // hasil dari concatenate antara `String` a dan b 


String format
----------------------

String format adalah proses dimana kita melakukan formatting String pada value String yang sudah ada. 

.. code:: python 

    quantity = 12
    productName = "Book"
    myproduct = "I have {}, with the quantity {}"
    print(myproduct.format(productName, quantity))

.. code:: python
    
    I have book, with the quantity 12 // result


Method - method yang terdapat pada String Python
----------------------------------------------------

Method - method pada String python merupakan method bawaan yang telah disediakan dari python dan dikhususkan untuk penggunaan String. 

Berikut ada beberapa contoh method String yang akan dibahas:
    * count()
    * endswith()
    * islower()


- count()
-------------------

``count()`` merupakan method yang digunakan untuk menghitung berapa kali jumlah kata atau huruf yang dicari itu muncul di dalam **string** yang kita deklarasi. 

contoh penggunaan ``count()`` dijelaskan dibawah ini:

.. code:: python 

    text = "I love orange and orange pie"
    print(text.count("orange")) // count berapa kali orange keluar


.. code:: python  

    2 


- **endswith()**
---------------------

``endswith()`` merupakan method yang digunakan untuk melakukan validasi, apakah **string** yang dinisiasi diakhiri dengan **string** yang dicari. Data yang di return adalah **boolean**.

contoh penggunaan ``endswith()`` dijelaskan dibawah ini:

.. code:: python

    text = "Hello, Dims."
    print(text.endswith(".")) // return true 


.. code:: python 

    True 


- islower()
-------------------

``islower()`` merupakan method yang digunakan untuk melakukan validasi apakah **string** yang diinisiasi seluruhnya merupakan lower case.

contoh penggunaan ``islower()`` dijelaskan dibawah ini:

.. code:: python 

    txt1 = "hello world"
    txt2 = "Hello world"
    print(txt1)
    print(txt2)

.. code:: python 

    True 
    False 