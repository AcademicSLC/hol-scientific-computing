Data structure di Python 
===============================

.. note::

    Semua codingan yang ada disini jika di copy paste sama persis akan dianggap sebagai kecurangan


Python memiliki beberapa **struktur data** yang bersifat `built-in function`, **struktur data** tersebut dapat digunakan untuk menampung berbagai macam data 

berdasarkan jumlah memori yang digunakan untuk menampung berbagai macam data tersebut. `Jenis-jenis` **struktur data** yang terdapat pada **python** antara lain 

`list`, `set`, `tuple` dan `dictionary`. Ke-empat **struktur data** tersebut adalah yang cukup sering digunakan, berikut adalah penjelasan dari **struktur data** tersebut.

- **list**

**List** adalah **struktur data** yang digunakan untuk menyimpan urutan elemen. List bersifat dinamis, artinya Anda dapat menambahkan, menghapus, dan memodifikasi elemen di dalamnya. List juga bersifat terurut dan memungkinkan duplikasi elemen.

contoh implementasi dari **list** sebagai berikut: 

.. code:: python 

    # Membuat sebuah list
    my_list = [1, 2, 3, 4, 5]

    # Menambahkan elemen
    my_list.append(6)

    # Mengakses elemen
    print(my_list[0])  # Output: 1

    # Mengubah elemen
    my_list[1] = 10

    # Menghapus elemen
    del my_list[2]

    print(my_list)  # Output: [1, 10, 4, 5, 6]

Dari implementasi kode **list** diatas akan menghasilkan output sebagai berikut. 

.. code:: console 

    [1, 10, 4, 5, 6]

- **set**

**Struktur data** selanjutnya adalah **set**, ``Set`` adalah **struktur data** yang digunakan untuk menyimpan koleksi elemen unik yang tidak terurut. ``Set`` tidak memungkinkan duplikasi elemen dan tidak mendukung pengindeksan seperti ``list``.

Berikut adalah contoh implementasi dari ``set`` **struktur data**. 

.. code:: python 

    # Membuat sebuah set
    my_set = {1, 2, 3, 4, 5}

    # Menambahkan elemen
    my_set.add(6)

    # Menghapus elemen
    my_set.remove(3)

    # Mengecek keberadaan elemen
    print(4 in my_set)  # Output: True

    print(my_set)  # Output: {1, 2, 4, 5, 6}

Hasil output dari dari implementasi **struktur data** diatas adalah sebagai berikut. 

.. code:: console

    {1, 2, 4, 5, 6}

- **Dictionary** 


**Dictionary** adalah **struktur data** yang digunakan untuk menyimpan pasangan *key-value*. **Dictionary** bersifat tidak terurut sampai Python 3.7 (di mana mulai dari versi ini, dict mempertahankan urutan berdasarkan saat elemen dimasukkan). Kunci harus bersifat unik dan tidak dapat diubah (immutable), seperti **string** atau **angka**.

Berikut adalah implementasi dari **struktur data** ``set`` pada python. 

.. code:: python 

    # Membuat sebuah dictionary
    my_dict = {"name": "Alice", "age": 25, "city": "New York"}

    # Menambahkan pasangan key-value
    my_dict["email"] = "alice@example.com"

    # Mengakses nilai berdasarkan kunci
    print(my_dict["name"])  # Output: Alice

    # Mengubah nilai
    my_dict["age"] = 26

    # Menghapus pasangan key-value
    del my_dict["city"]

    print(my_dict)  # Output: {'name': 'Alice', 'age': 26, 'email': 'alice@example.com'}

Berikut adalah hasil **output** yang diberikan dari implementasi kode diatas. 

.. code:: console 

    Alice
    {'name': 'Alice', 'age': 26, 'email': 'alice@example.com'}

- **Tuple** 

``Tuple`` adalah **struktur data** yang mirip dengan list, tetapi bersifat tidak dapat diubah (immutable). Setelah sebuah ``tuple`` dibuat, Anda **tidak dapat** mengubah, menambahkan, atau menghapus elemen di dalamnya. **Tuple** biasanya digunakan untuk **menyimpan data yang tidak boleh berubah**.

.. code-block:: python 

    # Membuat sebuah tuple
    my_tuple = (1, 2, 3, 4, 5)

    # Mengakses elemen
    print(my_tuple[0])  # Output: 1

    # Tuple tidak dapat diubah, jadi operasi seperti berikut tidak diizinkan:
    # my_tuple[1] = 10  # Ini akan menghasilkan TypeError

    # Namun, Anda dapat melakukan operasi seperti penggabungan
    new_tuple = my_tuple + (6, 7, 8)

    print(new_tuple)  # Output: (1, 2, 3, 4, 5, 6, 7, 8)

Maka hasil dari **output** diatas adalah sebagai berikut. 

..  code:: console 

    1
    (1, 2, 3, 4, 5, 6, 7, 8)
