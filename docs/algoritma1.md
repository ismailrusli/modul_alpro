# **Modul A1: Latihan Asesmen 1**

<!-- ![Status](https://img.shields.io/badge/Status-On_Progress-yellow?style=flat-square) -->
![Status](https://img.shields.io/badge/Status-Finish-brightgreen?style=flat-square)

## **Capaian Pembelajaran Mata Kuliah**

Mampu menggunakan elemen-elemen pemrograman, yaitu variabel,
percabangan, dan pengulangan untuk membuat algoritma sederhana.

---
## **Materi**

Materi ini untuk persiapan asesmen 1.
Di asesmen 1, mahasiswa diminta membuat program sederhana
yang menggabungkan percabangan dan pengulangan.
Berikut contoh tipe program yang harus dibuat di asesmen 1.

Buatlah program yang menerima input dari user berupa bilangan.
Misal user memasukkan bilangan 8.
Lalu, program harus mencetak ke layar sebanyak 8 baris kata berikut.

- Jika barisnya ganjil (baris 1, 3, 5, dst.), tulis kata `ganjil`
- Jika barisnya genap, tulis kata `genap`

  ```
  ganjil
  genap
  ganjil
  genap
  ganjil
  genap
  ganjil
  genap
  ```

Untuk membuat program seperti itu, apa yang harus kita lakukan?

**Pertama**, tentukan hal-hal yang sudah jelas.

1. User harus bisa memasukkan input berupa bilangan bulat (integer). 
```python linenums="1"
bilangan = int(input("Masukkan angka: "))
```

1. Program harus mencetak baris sejumlah bilangan yang dimasukkan user.
```python linenums="2"
for i in range(bilangan): 
    print("ganjil")
```

Lewat kedua poin ini, kita tahu bahwa program sudah bisa menerima input
dan mencetak baris sejumlah input.
Hanya saja, program ini baru mencetak kata yang sama untuk setiap baris, yaitu `ganjil`
karena memang yang diulang adalah perintah `print("ganjil")` (baris ke-3).
Padahal, kita ingin setiap barisnya berbeda bergantung pada
baris tersebut ganjil atau genap.

**Kedua**, tentukan polanya.

1. Jika baris ganjil, print `ganjil`
1. Jika baris genap, print `genap`

Bagaimana cara mendeteksi suatu baris itu ganjil atau genap?

Jika kita ingat, variabel `i` berisi elemen-elemen dari suatu iterabel.
Iterabel yang digunakan di program ini adalah iterabel yang dihasilkan
fungsi `range(bilangan)`.
Jika `bilangan` sama dengan 8, iterabel yang dihasilkan
fungsi `range(8)` adalah

```
0, 1, 2, 3, 4, 5, 6, 7
```
Dengan demikian, untuk setiap baris, variabel `i` nya
```
baris ke-1, i = 0
baris ke-2, i = 1
baris ke-3, i = 2
baris ke-4, i = 3
baris ke-5, i = 4
baris ke-6, i = 5
baris ke-7, i = 6
baris ke-8, i = 7
```
Dari pengetahuan ini, kita bisa membuat suatu pola.

1. `i + 1` sama dengan posisi barisnya. 
1. Jika `i + 1` ganjil, kita berada di baris ganjil
  dan jika `i + 1` genap, kita berada di baris genap.

Jika kita ingin nilai `i` benar-benar sama dengan posisi barisnya,
kita bisa menggunakan `range(1, bilangan + 1)` daripada `range(bilangan)`.
Dengan demikian, iterabel yang dihasilkan sama dengan posisi barisnya
(untuk contoh `bilangan` = 8).

```  
1, 2, 3, 4, 5, 6, 7, 8
```

**Ketiga** kita lakukan abstraksi:
Kita cari persamaan dari setiap baris dengan mengabaikan detail.
Dalam hal ini, untuk setiap baris, kita pasti punya variabel, `i` yang isinya
bilangan baris tersebut.
Terhadap `i` bisa kita cek ganjil/genapnya.

!!! Catatan
    Cara cek suatu bilangan ganjil/genap adalah dengan menggunakan
    operator modulus (%).

    - Jika `i % 2` sama dengan 0, maka `i` genap
    - Jika `i % 2` tidak sama dengan 0, maka `i` ganjil 

**Terakhir**, kita terjemahkan abstraksi ini menjadi sebuah algoritma.
```python linenums="1"
bilangan = int(input("Masukkan angka: "))

for i in range(1, bilangan + 1):
  if (i % 2 == 0):
    print("genap")
  else:
    print("ganjil")
```

## **Kerjakan**
Buatlah program yang outputnya seperti berikut.
Untuk setiap program, jumlah baris ditentukan
bilangan yang dimasukkan user.

1. 
  ```python
  1 ganjil
  2 genap
  3 ganjil
  4 genap
  5 ganjil
  # dst sampai bilangan dimasukkan user
  ```

1. 
  ```python
  1 *
  2 *
  3 *
  4 *
  5 *
  6 +
  7 +
  # cetak simbol + terus sampai bilangan dimasukkan user
  ```

1. 
  ```python
  1 *
  2 **
  3 ***
  4 ****
  5 *****
  6 ++++++
  7 +++++++
  # cetak simbol + terus sampai bilangan dimasukkan user
  ```

1. 
  ```python
  # Misal user memasukkan angka 9
  9 *********
  8 ********
  7 *******
  6 ******
  5 *****
  4 ****
  3 ***
  2 **
  1 *
  ```

1. 
  ```python
  # Misal user memasukkan angka 7 yang adalah ganjil
  # Maka setiap baris ganjil mucul nomor baris dan kata ganjil
  # Sementara baris genap muncul nomor baris dan *
  1 ganjil
  2 *
  3 ganjil
  4 *
  5 ganjil
  6 *
  7 ganjil
  ```

    !!! Petunjuk
        Kita harus cek ganjil genap dua kali, yaitu
        terhadap bilangan input user dan terhadap `i`
        (baris).

Buatlah program yang outputnya seperti berikut.
Untuk setiap program, jumlah baris tetap tapi
pola output ditentukan bilangan yang dimasukkan user.


1. 
  ```python
  # Program mencetak 5 baris.
  # Jika user input angka ganjil, outputnya
  1 ganjil
  2 ganjil
  3 ganjil
  4 ganjil
  5 ganjil

  # Jika user input angka genap, outputnya
  1 genap
  2 genap
  3 genap
  4 genap
  5 genap
  ```

1. 
  ```python
  # Jika user input angka ganjil,
  # program mencetak 5 baris berikut  
  1 ganjil
  2 ganjil
  3 ganjil
  4 ganjil
  5 ganjil

  # Jika user input angka genap, 
  # program mencetak 6 baris berikut
  1 genap
  2 genap
  3 genap
  4 genap
  5 genap
  6 genap
  ```

1. 
  ```python
  # Jika user input angka ganjil,
  # program mencetak 5 baris berikut  
  1 ganjil
  3 ganjil
  5 ganjil
  7 ganjil
  9 ganjil

  # Jika user input angka genap, 
  # program mencetak 5 baris berikut
  2 genap
  4 genap
  6 genap
  8 genap
  10 genap
  ```

1. 
  ```python
  # Jika user input angka ganjil,
  # program mencetak 5 baris berikut  
  1 *
  2 *
  3 *
  4 *
  5 *

  # Jika user input angka genap, 
  # program mencetak 6 baris berikut
  6 +
  7 +
  8 +
  9 +
  10 +
  ```

1. 
  ```python
  # Jika user input angka ganjil,
  # program mencetak 5 baris berikut  
  1 *
  2 *
  3 *
  4 *
  5 *

  # Jika user input angka genap, 
  # program mencetak 5 baris berikut  
  5 +
  4 +
  3 +
  2 +
  1 +
  ```
