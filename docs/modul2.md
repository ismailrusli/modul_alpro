# **Modul 2: Literal dan Variabel**

<!-- ![Status](https://img.shields.io/badge/Status-On_Progress-yellow?style=flat-square) -->
![Status](https://img.shields.io/badge/Status-Finish-brightgreen?style=flat-square)

## **Capaian Pembelajaran Mata Kuliah**

Mampu menggunakan elemen-elemen pemrograman, yaitu variabel,
percabangan, dan pengulangan untuk membuat algoritma sederhana.

---

## **Materi**

Secara abstrak, program komputer dapat dilihat seperti gambar berikut.

<br><br>
![Program komputer](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/proses.png)
<br><br>

Program komputer memiliki input dan output. Ke dalam input, dimasukkan data. Dari output, keluar data. Jadi, tugas program komputer adalah memproses data. Dengan kata lain: dari data menjadi data.

Oleh karena program berkaitan erat dengan data, kita mulai juga dengan data. Ada 3 istilah penting dalam pemrograman terkait data, yaitu:

1. Literal
1. Tipe literal
1. Operator

---

### **Literal**

Literal adalah nilai/isi data.
Contohnya bilangan `5`.
Contoh lain adalah huruf atau sekumpulan karakter (string), misalnya `"a"` dan `"Bandung"`.
Keduanya ditulis dalam tanda petik untuk membedakan dengan perintah yang dipakai dalam bahasa pemrograman.
Di kode berikut, kata `print` yang pertama adalah perintah dan kata `"print"` di dalam tanda petik adalah literal.

```python
print("print")
```

**Coba**

1. Kita bisa menuliskan literal ke dalam Python Interpreter. Sebagai contoh, ketikkan literal-literal berikut dan tekan Enter setiap kali selesai mengetikkan satu literal.

    - `5`
    - `5.03`
    - `'a'`
    - `'algoritma'`
    - `True`
    - `[-2,3]`


1. Coba ketikkan `a` (tanpa tanda petik) di Python Interpreter. Apa yang terjadi? Mengapa demikian?

1. Perhatikan kode berikut. Apa beda antara baris ke-1 dan baris ke-2?
```python
print('2')
print(2)
```
---

### **Tipe Literal**

Data tentu bermacam-macam.
Ada data berupa bilangan bulat (Contoh `5`).
Ada data berupa bilangan riil (Contoh `5.03`).
Ada data berupa karakter (Contoh `"a"`).
Ada data berupa rangkaian karakter (Contoh `"algoritma"`).
Ada data berupa nilai kebenaran suatu ekspresi/logika (Contoh `True`).
Ada juga data berupa kumpulan bilangan (Contoh `[1,2,3]`).

Dalam pemrograman, setiap tipe data biasanya ada namanya.
Sebagai contoh,

1. untuk data berupa bilangan bulat, biasanya tipe datanya disebut **integer**.
1. Untuk data berupa bilangan riil, disebut **float** atau **double**.
1. Untuk karakter biasanya disebut **char**.
1. Untuk serangkaian karakter biasanya disebut **string**.
1. Untuk nilai kebenaran dari suatu ekspresi logika disebut **boolean**.
1. Untuk kumpulan bilangan bisa disebut sebagai **array** atau **list** atau **set** atau lainnya.

Setiap bahasa pemrograman menentukan sendiri tipe datanya.
Pemrogram dapat juga membuat tipe data kustom sesuai kebutuhan.

**Coba**

1. Ketikkan setiap baris berikut ke dalam Python Interpreter (Enter setelah mengetikkan satu baris).

    - `type(5)`
    - `type(5.03)`
    - `type('a')`
    - `type('algoritma')`
    - `type(True)`
    - `type([-2,3])`

    !!! Catatan
        Sebelumnya, kita sudah mengenal fungsi `print`. Di sini, kita mengenal
        fungsi lain yang namanya `type`. Fungsi `type` gunanya mencetak tipe
        dari suatu literal.

    !!! Catatan
        Dalam bahasa pemrograman Python, tidak dibedakan antara tipe data `char` dan `string`.
        Keduanya dianggap sebagai `string`.

1. Mana cara yang benar untuk menuliskan literal integer `seratus ribu lima ratus empat puluh tujuh`?
```python
print(100547)
print("100547")
print(100.547)
print(100 547)
print(100_547)
```
1. Mana cara yang benar untuk menuliskan literal float `lima koma tiga puluh empat`?
```python
print("lima koma tiga puluh empat")
print(lima koma tiga puluh empat)
print(5,34)
print(5.34)
print(5 34)
```

1. Mana cara yang benar untuk menuliskan literal float `nol koma 3`?
```python
print(0.3)
print(0,3)
print(.3)
```

1. Apa beda ketiga baris ini?
```python
print(4)
print(4.0)
print(4.)
```

1. Tuliskan kode berikut. Apa yang terjadi?
```python
print(1000000)
print(1_000_000)
print(1e6)
```

1. Mana cara yang benar untuk menuliskan literal float `negatif nol koma nol nol nol dua`?
```python
print(-0.0002)
print(-.0002)
print(-2e-4)
```

1. Bagaimana cara menuliskan kalimat berikut ke layar (persis seperti ini, termasuk tanda kutipnya)?
    ```
    "Apa kabarmu, Bud?", tanya Surya
    ```

    !!! Petunjuk
        Gunakan escape character `\"` untuk menuliskan tanda kutip.


1. Bagaimana cara menuliskan kalimat berikut ke layar (persis seperti ini, termasuk tanda kutipnya)?
    ```
    "Darma itu panggilannya 'Si Jago Bola'", kata Andi
    ```

1. Apa beda antara baris-baris berikut?
    ```python
    print()
    print('')
    print("")
    ```

    !!! Catatan
        `''` dan `""` adalah string kosong (empty string)

1. Apa bedanya antara 2 baris berikut?
```python 
print(True)
print("True")
```
---
### **Operator**
<!-- Tuliskan kode berikut lalu jalankan. Apa yang terjadi? -->

<!-- ```python -->
<!-- print(2 + 2) -->
<!-- ``` -->

Dua literal dapat dioperasikan menggunakan operator.
Contohnya adalah operator-operator aritmatika berikut.

```python
print(5 + 2)
print(5 - 2)
print(5 * 2)
print(5 / 2)
print(5 % 2)  # modulus
print(3 ** 2) # 3 pangkat 2
```

!!! Catatan
    Spasi tidak berarti apa-apa dalam Python. Dengan demikian, menulis
    `print() atau print ()` adalah sama saja. Begitu juga menulis
    `print(5+2)` dan `print(5 + 2)`.

!!! Catatan
    Tanda hashtag (`#`) dalam Python adalah penanda untuk suatu komentar.
    Tulisan setelah tanda ini, akan dianggap sebagai komentar atau catatan
    dan bukan dianggap sebagai bagian dari kode.

!!! Catatan
    Operator yang mengoperasikan 2 literal disebut binary operator. Ada juga operator yang beroperasi terhadap 1 literal, disebut unary operator. Contohnya adalah operator negatif atau min (`-4`).

Selain operator aritmatika, dua literal juga dapat dibandingkan.
Berikut adalah operator perbandingan.

```python
print(5 < 7)   # kurang dari
print(5 > 7)   # lebih dari
print(5 == 7)  # sama dengan
print(5 != 7)  # tidak sama dengan
print(5 <= 7)  # kurang atau sama dengan
print(5 >= 7)  # lebih atau sama dengan
```

Apakah operator hanya dapat digunakan untuk integer?
Tentu saja tidak.
Berikut contoh operator untuk string.

```python
print("Nama" + "saya" + "Budi")
```

Dan contoh untuk operator boolean.

```python
print(True and False)
print(True or True)
print(not True)
```

**coba**

1. Jalankan kode berikut di Python Interpreter. Apakah tipe literal dari hasilnya?
```python
type(2 + 3.0)
type(3 / 2)
type(3 > 2)
type(2 * 3.)
```

1. Operator apakah ini?
```python
print(5 // 2)
```
Apa bedanya dengan operator pembagian `print(5 / 2)`?

1. Apa hasil berikut?
    ```python
    print(2 + 3 * 5)
    ```

    !!! Catatan
        Setiap operator memiliki prioritas untuk dikerjakan. Dalam hal ini, `*` prioritasnya lebih tinggi dibandingkan `+`.
        Berikut adalah prioritas operator dalam Python.

        | Prioritas | Operator | Unary/Binary |
        | :---: | :---: | :---: |
        | 1 |`**`| binary |
        | 2 |`+`, `-`| unary |
        | 3 | `*`, `/`, `//`, `%` | binary |
        | 4 | `+`, `-` | binary |

        Untuk mengatur operasi yang dikerjakan terlebih dulu,
        dapat digunakan tanda kurung `()`. Operasi di dalam
        tanda kurung akan dikerjakan terlebih dahulu.

        ```python
        print((5 * ((25 % 13) + 100) / (2 * 13)) // 2)
        ```

1. Apa hasil berikut?
    ```python
    print(9 % 6 % 2)
    ```

    !!! Catatan
        Operator modulus `%` adalah *left-binding*. Artinya jika ada `%` berurutan, dikerjakan dari kiri terlebih dahulu.

1. Apa hasil berikut?
    ```python
    print(2 ** 2 ** 3)
    ```

    !!! Catatan
        Operator pangkat `**` adalah *right-binding*. Artinya jika ada `**` berurutan, dikerjakan dari kanan terlebih dahulu.

---

### **Variabel**

Satu komponen penting dari sebuah program adalah variabel.
Variabel digunakan untuk menampung data.
Variabel memiliki nama agar mudah dipanggil.

![Variabel digunakan untuk menampung data](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/variable.jpg)

Cara mengisikan data ke variabel sangat sederhana.
Tuliskan nama variabel, ikuti dengan sama dengan `=`
dan terakhir tuliskan datanya.
Tanda sama dengan `=` ini disebut sebagai **assignment operator**.
Fungsinya adalah meng-*assign* suatu data ke variabel.

```python
num = 5  # Variabel dengan nama a diisi data (literal) 5
print(num)
```
Nama sebuah variabel tidak bisa bebas. Ada aturannya.

1. Nama sebuah variabel hanya dapat terdiri dari huruf kecil, huruf kapital, angka, dan garis bawah atau underscore (`_`).
1. Nama variabel harus diawali dengan huruf.
1. Huruf kecil dan kapital dianggap sebagai 2 karakter yang berbeda. Jadi, variabel dengan nama `budi` dan `Budi` adalah 2 variabel yang berbeda.
1. Nama variabel tidak boleh sama dengan nama yang digunakan di dalam Python (*reserved keyword*. Berikut adalah contoh *reserved keywords*: 
    ```python
    ['False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
    ```

Berikut adalah contoh variabel yang boleh.
```python
MyVariable, i, t34, Exchange_Rate, counter, nama, _
```

Berikut adalah contoh variabel yang tidak boleh.
```python
10t           # Tidak diawali huruf
nama siswa    # Terdapat spasi
lulus?        # Ada tanda tanya
```

Salah satu manfaat dari variabel dapat dilihat dari dua kode berikut.
```python
print("budi")
print("budi")
print("budi")
print("budi")
print("budi")

# Di kode ini, saat kita ingin mengubah budi menjadi wati,
# kita harus mengubah 5 baris perintah.
```

```python
nama = "budi"
print(nama)
print(nama)
print(nama)
print(nama)
print(nama)

# Di kode ini, saat kita ingin mengubah budi menjadi wati,
# kita cukup mengubah baris pertama saja, yaitu menjadi:
# nama = "wati"
```

Kita bisa membuat variabel sebanyak yang dibutuhkan.
Akan tetapi, kita tidak bisa menggunakan variabel yang belum dibuat.
```python
nama = "Budi"
print(Nama)

# Program ini akan error. Kenapa?
```

Operator yang sudah kita pelajari, berlaku juga untuk variabel.
```python
nama = "Budi"
umur = 23

print("Nama saya " + nama)
print("Lima tahun lagi, umur saya adalah", 5 + umur)
```

Untuk mengganti isi sebuah variabel, kita cukup menggunakan
assignment operator.
```python
nama = "budi"
nama = "Budi"

print(nama) # yang muncul adalah Budi
```

Ketika sebuah variabel `a` di-*assign* ke variabel `b`,
artinya adalah isi dari variabel `b`
yang di-*assign*-kan ke variabel `a`.

```python
a = 10
b = a

print(b) # hasilnya 10
```

**Coba**

1. Bilangan berapa yang akan muncul?
    ```python
    a = 100
    b = 50
    a = b

    print(a)
    ```

1. Bilangan berapa yang akan muncul?
    ```python
    a = 100
    b = 50
    a = b
    print(b)  # bilangan berapa yang akan muncul?
    ```

1. Bilangan berapa yang akan muncul?
    ```python
    a = 100
    b = a
    print(b)  # bilangan berapa yang akan muncul?
    ```

1. Bilangan berapa yang akan muncul?
    ```python
    a = 100
    b = a
    a = a + b
    print(a)  # bilangan berapa yang akan muncul?
    ```

1. Bilangan berapa yang akan muncul?
    ```python
    a = 100
    b = a + b
    print(b)  # bilangan berapa yang akan muncul?
    ```

1. Bilangan berapa yang akan muncul?
    ```python
    a = 100
    b = a
    a = b + 100
    print(a)  # bilangan berapa yang akan muncul?
    ```

1. Bilangan berapa yang akan muncul?
    ```python
    a = 100
    b = 50
    print(a + b)  # bilangan berapa yang akan muncul?
    ```

1. Bilangan berapa yang akan muncul?
    ```python
    a = 100
    b = 50
    c = 25
    d = a + b + c

    print(d)  # bilangan berapa yang akan muncul?
    ```

1. Bilangan berapa yang akan muncul?
    ```python
    a = 100
    b = a
    c = a + b
    a = 30
    d = c + a + b
    print(d)  # bilangan berapa yang akan muncul?
    ```

1. Bilangan berapa yang akan muncul?
    ```python
    a = 3.0
    b = 4.0
    c = (a ** 2 + b ** 2) ** 0.5
    print("c =", c)
    ```

---

## **Tugas Praktikum**
1. Perbaiki kode-kode berikut.
    ```python
    a = 100
    b

    print(b)
    ```
    ```python
    a = 100
    b = 200

    print(c)
    ```
    ```python
    a = 100
    b = "seratus"

    print(a + b)
    ```
    ```python
    a = 3.2
    b = 2.0
    c = a / (b - 2.0)

    print(c)
    ```

1. Apa hasil dari program berikut?
    ```python
    nama_depan = "Budi"
    nama_belakang = "Ramdani"
    nama_lengkap = nama_depan + " " + nama_belakang
    print(nama_lengkap)
    ```
    ```python
    a = 1.5
    b = 3.4
    c = a * b  
    d = a / b  
    print(a, b)
    ```
    ```python
    a = 1    
    b = 2.3  
    c = a + b  
    print(c)
    ```
    ```python
    a = 2
    b = 3
    c = a < b
    print(c) 
    ```
    ```python
    a = b = 4
    c = (a == b)
    d = (a != b)
    print(c, d)
    ```

1. Budi punya tiga apel, Wati punya lima apel, dan Danu punya enam apel. Buatlah program berikut.
    - Buat variabel dengan nama `budi`, `wati`, dan `danu`.
    - Isi variabel-variabel tersebut dengan jumlah apel yang masing-masing miliki.
    - Cetak semua isi variabel ke layar dalam satu baris dipisahkan koma.
    - Buat variabel baru dengan nama `total_apel` dan isi variabel ini dengan jumlah apel.
    - Cetak nilai yang ada di `total_apel` ke layar.
    - Saat mencetak ke layar, gabungkan nilai variabel dengan suatu string berisi keterangannya. Misalnya,  gabungkan antara `"Jumlah total apel adalah"` dan `total_apel`.
