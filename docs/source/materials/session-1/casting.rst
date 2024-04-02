**Casting** 
=====================

Casting digunakan untuk melakukan perubahan dari tipe data lama menjadi tipe data yang baru.

cara menggunakan casting adalah dengan dengan memanggil *function constructor* dari python.

function constructor yang terdapat pada python adalah sebagai berikut:
 - int()
  + function constructor ``int()`` bisa digunakan untuk mengubah menjadi tipe data ``int``.
 - str()
  + function constructor ``str()`` bisa digunakan untuk mengubah menjadi tipe data ``str``.
 - float()
  + function constructor ``float()`` bisa digunakan untuk mengubah menjadi tipe data ``float``.


contoh penggunaan casting ada dibawah ini: 

.. code:: python 
    a_str = "1" // angka bertipe data string 
    b_int = 10 // angka bertipe data int 
    c_str = "1.24" // angka bertipe data string 

    a_int = int(a_str) // mengubah dari `string` ke `int`
    b_str = str(b_int) // mengubah dari `int` ke `string` 
    c_float = float(c_str) // mengubah dari `string` ke `float`

    print(a_int) 
    print(b_str)
    print(c_float)

.. console:: 
    1 // sekarang bertipe `int`
    10 // sekarang bertipe `str`
    1.24 // sekarang bertipe `float`

