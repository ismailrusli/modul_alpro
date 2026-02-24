# **Modul 1: Halo, Dunia!**

![Status](https://img.shields.io/badge/Status-Finish-brightgreen?style=flat-square)

<!-- <img src="https://readthedocs.org/projects/manimce/badge/?version=latest" alt="Documentation Status"> -->

## **Capaian Pembelajaran Mata Kuliah**

Mampu menggunakan elemen-elemen pemrograman, yaitu variabel,
percabangan, dan pengulangan untuk membuat algoritma sederhana.

---
## **Materi**
### **Program Pertama**

Program pertama yang kita buat adalah program "Halo Dunia".
Program ini menuliskan kata-kata "Halo Dunia!" ke layar monitor.
Caranya adalah, tuliskan satu baris kode berikut ke dalam Python Interpreter, lalu tekan Enter.
Bisa juga, tuliskan di suatu file teks.
Simpan sebagai `halo.py`.
Lalu, di terminal, ketikkan `python halo.py`, Enter.

``` python
print("Halo, Dunia!")
```

Program pertama kita terdiri dari komponen-komponen berikut.

1. Kata `print`,
1. kurung buka dan kurung tutup `()`,
1. tanda kutip `""`, dan
1. teks `Halo, Dunia!`.

<br> <br>
![Bagian-bagian kode dalam program pertama, Halo, Dunia!](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/halo_dunia.png)
<br> <br>

Kata `print` dalam program pertama kita adalah sebuah fungsi.
Dalam pemrograman, fungsi adalah bagian kode yang punya tugas tertentu.
Fungsi `print` tugasnya mencetak (*print*) sesuatu ke layar.

Setiap fungsi dalam Python, selalu diikuti tanda kurung `()`.
Di dalam kurung, dituliskan input data untuk fungsi tersebut.
Dalam contoh kita, yang diinputkan ke fungsi `print` adalah kata `"Halo, Dunia!"`.

Kata `Halo, Dunia!` harus dituliskan memakai petik untuk menunjukkan bahwa
input ke dalam `print` adalah teks (string) atau kumpulan karakter.

<br><br>
![Blok diagram fungsi dalam Python](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/blok_print.png)
<br><br>

<!-- Setiap fungsi, dapat memiliki 0 atau lebih input yang disebut dengan argumen. -->
<!-- Secara umum, cara penulisan fungsi dalam Python adalah seperti dalam gambar berikut. -->

<!-- <br><br> -->
<!-- ![Anatomi fungsi dalam Python](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/anatomi_fungsi.png) -->
<!-- <br><br> -->

---
**Coba**

1. Tuliksan nama kamu ke layar monitor.
1. Gunakan fungsi `print` dan input kata `Halo, Bandung!` tanpa tanda kutip. Apa yang terjadi?
1. Gunakan fungsi `print` dan input kata `Halo, Bandung!` namun dengan satu kutip `'Halo, Bandung!'`
Apa yang terjadi?
1. Tuliskan 2 fungsi `print` secara berurutan seperti berikut. Apa yang terjadi?
```python
print("Halo,") print("Dunia!")
```
1. Tuliskan 2 fungsi `print` secara berurutan di 2 baris yang berbeda seperti berikut. Apa yang terjadi?
```python
print("Halo,")
print("Dunia!")
```
1. Apa yang terjadi jika kita menuliskan fungsi `print` tanpa argumen (tanpa input)?
```python
print("Halo,")
print()
print("Dunia!")
```

!!! Catatan
    Python hanya membolehkan kita menulis maksimal satu instruksi per baris. Memanggil fungsi `print` kita anggap sebagai 1 instruksi. Jika ingin menuliskan 2 instruksi dalam 1 baris, pisahkan instruksi dengan tanda titik koma (`;`).

---

### **Escape Characters**
Perhatikan program berikut.
```python
print("Halo, Dunia!\nNama saya, Budi.")
```

Jika dijalankan, program tersebut akan menghasilkan luaran seperti berikut.
```
Halo, Dunia!
Nama saya, Budi.
```

Karakter *backslash* (`\`) disebut sebagai *escape character*. Karakter setelah `\` tidak dianggap sebagai karakter yang harus dicetak. Akan tetapi, dianggap sebagai karakter untuk memformat teks. Dalam hal ini, karakter `n` adalah karakter untuk membuat baris baru (*newline*).

---
**Coba**

1. Apa output dari program berikut?
```python
print('\\')
```
1. Apa output dari program berikut? Apa fungsi dari `\t`?
```python
print('No\tNama')
print('1\tBudi')
print('2\tWati')
```
---

### **Fungsi `print` dengan Banyak Argumen**
Fungsi `print` dapat menerima banyak input (argumen).
Setiap input dipisahkan koma.
Sebagai contoh adalah kode berikut.

```python
print('Nama', 'saya', 'Budi')
```
Jika dijalankan, kode tersebut akan mengeluarkan output seperti berikut.

```
Nama saya Budi
```
Setiap argumen, akan dituliskan dalam 1 baris sesuai posisinya dan dipisahkan spasi.
Karena `Nama` dituliskan pertama, kata tersebut muncul terlebih dulu,
diikuti `saya` dan `Budi`.

Cara menuliskan input ke dalam suatu fungsi berdasarkan posisinya, disebut
sebagai **positional argument**.
Ada cara lain, yaitu **keyword argument**.
Keyword argument digunakan jika suatu fungsi menerima beberapa jenis input.

Sebagai contoh, fungsi `print` sebenarnya tidak hanya menerima input berupa teks
yang akan dicetak ke layar, tapi juga menerima input
berupa karakter terakhir untuk setiap output. 
Secara default, karakter terakhir ini adalah escape character `\n`.
Aka tetapi, kita bisa mengubahnya dengan memasukkan karakter baru menggunakan
keyword argument.

```python
print("Halo,", end = ' ')
print("Dunia!")
```

Jika dijalankan, kode tersebut akan mengeluarkan output berikut di layar.
```
Halo, Dunia!
```

Dalam kode tersebut, `Halo` dicetak diikuti spasi.
Lalu Python menjalankan perintah selanjutnya, yaitu mencetak `Dunia!`.

`end` dalam kode tersebut adalah nama argumen.
Sementara `' '` (spasi) adalah nilai atau data yang kita inputkan untuk argumen `end`.
Nama argumen dan nilainya kita pisahkan menggunakan tanda `=`.

---
**Coba**

1. Tulis dan jalankan kode berikut. Apa yang terjadi?
```python
print("Halo,", end = '***')
print("nama saya Budi")
```

1. Tulis dan jalankan kode berikut. Apa yang terjadi?
```python
print(end = '**', "Halo,") 
print("nama saya Budi")
```
!!! Catatan
    Positional argument harus selalu dituliskan terlebih dahulu sebelum keyword argument

1. Tulis dan jalankan kode berikut. Apa yang terjadi?
```python
print("Halo,", end = '\n\n') 
print("nama saya Budi")
```

1. Tulis dan jalankan kode berikut. Apa yang terjadi? 
```python
print("Halo,", "nama", "saya", "Budi", sep = '/')
```

1. Tuliskan dan jalankan kode berikut. Apa yang terjadi?
```python
print("Halo,", "nama", "saya", "Budi", end = '*', sep = '/')
print("Saya lahir di Bandung")
```
Adakah perbedaan dengan kode berikut?
```python
print("Halo,", "nama", "saya", "Budi", sep = '/', end = '*')
print("Saya lahir di Bandung")
```

!!! Catatatn
    `sep` adalah nama argumen yang merupakan singkatan dari separation
    atau pemisah antarargumen. Defaultnya, `sep = ' '`.
    Peletakkan keyword argument bebas, selama diletakkan setelah positional argument.
    Fungsi tahu bahwa `'/'` adalah argumen untuk `sep` dan `'*'` untuk `end`
    karena penulisannya menyertakan nama argument atau keyword.

---

## **Tugas Praktikum**
1. Tambahkan keyword argument `sep` dan `end` ke baris pertama kode ini
```python
print("Programming","Essentials","in")
print("Python")
```
sehingga outputnya menjadi seperti berikut.
```
Programming***Essentials***in...Python
```

1. Tulis dan jalankan kode berikut.
```python
print("    *")
print("   * *")
print("  *   *")
print(" *     *")
print("***   ***")
print("  *   *")
print("  *   *")
print("  *****")
```
Lalu, kerjakan perintah berikut.
    - Buat kode menjadi 1 baris dengan memanfaatkan escape character newline (`\n`)
    - Buat ukuran panah menjadi 2x lipat lebih besar dengan proporsi yang tetap.
    - Buat menjadi 2 panah yang sama yang diletakkan bersampingan
     (Teks dapat diulang dengan mengalikan teks tersebut dengan bilangan.
      Misalnya: `print('halo ' * 2)` akan menghasilkan `halo halo`). 
    - Hapus salah satu tanda kutip `"`, lalu jalankan. Baca pesan error
    dari Python. Apakah Python memberi tahu letak kesalahan dalam kode?
    Lakukan hal yang sama untuk tanda kurung.
    - Ganti salah satu kata `print` menjadi `Print` (P huruf kapital).
    Apa yang terjadi?
    - Ganti beberapa tanda kutip `"` dengan petik satu `'`. Apa yang terjadi?

