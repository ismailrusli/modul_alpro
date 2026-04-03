# Modul 4: Iterabel dan Pengulangan

<!-- ![Status](https://img.shields.io/badge/Status-On_Progress-yellow?style=flat-square) -->
![Status](https://img.shields.io/badge/Status-Finish-brightgreen?style=flat-square)


## **Capaian Pembelajaran Mata Kuliah**

Mampu menggunakan elemen-elemen pemrograman, yaitu variabel,
percabangan, dan pengulangan untuk membuat algoritma sederhana.

---

## **Materi**

### **Iterabel**
Kita sudah mengenal berbagai macam tipe data, misalnya
`int`, `float`, dan `string`.
Setiap data tersebut menampung hanya satu value.
Ada juga data yang menampung banyak value sekaligus. 
Contohnya adalah `list`, `tuple`, `set`, dan `dictionary`.
Berikut contohnya.
```python linenums="1" 
daftar_nama = ["Budi", "Wati", "Dudi"]        # list
koordinat = (1,3)                             # tuple
buah_buahan = {"apel", "semangka", "jeruk"}   # set
data_mahasiswa = {"nama": "Budi", umur: 21}   # dictionary
```

Di modul ini, kita tidak membahas detail tipe-tipe data tersebut.
Kita hanya menunjukkan data tersebut dalam kaitannya sebagai sebuah iterabel.
Iterabel adalah

1. Data yang dapat menampung banyak value
2. Yang setiap datanya dapat dibaca satu per satu
    atau dengan kata lain kita dapat melakukan iterasi
    ke setiap data di dalamnya.

`list`, `tuple`, `set`, dan `dictionary` adalah iterabel.
Tapi selain itu, ada juga satu iterabel penting, yaitu 
data yang dihasilkan fungsi `range()`.

`range()` adalah fungsi yang dapat menerima tiga argumen.
```
range(awal, akhir, step) ->  ini akan menghasilkan urutan yang
                             dimulai dari awal,
                             berakhir di bilangan sebelum akhir,
                             dan loncat sebesar step.
```

Sebagai contoh:
```python linenums="1"
data = range(1,10,2)

data = list(data) # ubah ke list untuk diprint
print(data)
```

Hasilnya adalah
```
[1, 3, 5, 7, 9]
```

Kita juga bisa hanya memasukkan satu atau dua argumen ke
dalam `range`
```python linenums="1"
data1 = range(10)    # mulai = 0 (default), akhir = 9, step = 1 (default)
data2 = range(1,10)  # mulai = 1, akhir = 9, step = 1 (default)

data1 = list(data1)
data2 = list(data2)

print(data1)
print(data2)
```

yang masing-masing hasilnya adalah sebagai berikut.

```
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
[1, 2, 3, 4, 5, 6, 7, 8, 9]
```

**Coba**

1. Berikut adalah program untuk mencetak hasil dari fungsi `range`.
    ```python
    data = range(# kode di sini)
    data = list(range)
    print(data)
    ```

    Buatlah agar program tersebut menghasilkan
    urutan-urutan bilangan berikut.
    Ubah kode hanya di dalam kurung fungsi `range`. 

    ``` linenums="1"
    [1, 2, 3, 4, 5]
    [0, 2, 4, 6, 8, 10]
    [4, 5, 6, 7, 8, 9]
    [20, 40, 60, 80, 100]
    [-2, -1, 0, 1, 2]

    [9, 8, 7, 6, 5, 4, 3, 2]    # Gunakan step = -1
    [100, 90, 80, 70, 60]
    [3, 2, 1, 0, -1, -2]
    [0, -5, -10, -15, -20]
    ```

1. Buatlah iterabel menggunakan fungsi `range()` dengan
    ketentuan sebagai berikut.
    -  Terdiri dari 10 elemen (awal, akhir, dan step bebas)
    -  Terdiri dari 8 elemen, awal di -2, dan loncat 3
    -  Terdiri dari 10 elemen, mulai dari 9, mundur 1 step = [9, 8, ...]

---

### **Pengulangan**
Perhatikan kode berikut.
```python linenums="1"
print("Budi")
print("Budi")
print("Budi")
print("Budi")
print("Budi")
print("Budi")
print("Budi")
print("Budi")
print("Budi")
print("Budi")
```

Program tersebut, menuliskan kata `Budi` sebanyak 10 baris.
Ada cara yang lebih baik untuk itu, yaitu dengan
menggunakan pengulangan.


#### **Pengulangan Menggunakan `for`** 
Jika kita ingin mengulang-ulang suatu baris kode dalam Python, kita
harus 'membungkusnya' dalam suatu blok pengulangan.
Di kode berikut, `print("Budi")` diulang 10 kali.
```python
for i in range(10):
    print("Budi")
```

Secara umum, sintaks untuk pengulangan menggunakan `for`
adalah:
```
for <variabel> in <iterabel>:
    kode yang akan dijalankan
    berulang-ulang
```

<br> <br>
![for loop](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/for_sintaks.png)
<br> <br>

Secara detail, proses pengulangan adalah sebagai berikut.

<br> <br>
![for loop](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/for_detail.png)
<br> <br>

!!! Catatan
    Setelah statement `for <variabel> in <iterabel>:`
    Python mewajibkan kita menuliskan kode yang akan diulang.
    Jika tidak, program akan error.
    Jika kita belum mau menuliskan kode namun
    ingin mencoba menjalankan program yang kita buat,
    gunakan kata kunci `pass` yang artinya perintah
    kosong (tidak melakukan apa-apa).

    ```python
    for i in range(10):
        pass
    ```


**Coba**

1. Tulis kode berikut dan jalankan. Apa yang terjadi?

    ```python
    for i in range(10):
        print(i)
    ```

    ```python
    for i in range(10):
        print(i, end = ' ')
    ```

    ```python
    for i in range(10, 0, -1):
        print(i)
    ```

    ```python
    for i in range(1, 20, 2):
        print(i)
    ```

1. Oleh karena `list` adalah iterabel, sintaks berikut valid.
    ```  
    for <variabel> in <list>:
        kode
    ```
    Sebagai contoh:

    ```python linenums="1"
    data = ['bandung', 'jakarta', 'surabaya']

    for kota in data:
        print(kota)
    ```

1. Contoh iterabel yang sudah pernah kita temui namun belum
    kita sebutkan sebagai iterabel adalah `string`.
    Perhatikan kode berikut.

    ```python
    matakuliah = "algoritma dan pemrograman"

    for huruf in matakuliah:
        print(huruf)
    ```

    Bandingkan dengan kode berikut.

    ```python
    matakuliah = "algoritma dan pemrograman"

    for huruf in matakuliah:
        print(huruf, end = ' ')
    ```

---

#### **Pengulangan Menggunakan `while`**

Selain menggunakan perintah `for`, pengulangan dalam Python
juga dapat menggunakan `while`.
Sintaks pengulangan menggunakan `while` adalah sebagai berikut.

```
while (<ekspresi boolean>):
    # kode yang akan diulang-ulang
    # selama ekspresi boolean bernilai True
```

!!! Catatan
    Tanda kurung dalam `(<ekspresi boolean>)`
    adalah opsional.

Berikut adalah contoh pengulangan menggunakan `while`.

```python
while (True):
    print("*", end = "")
```

Program tersebut akan terus-terusan menuliskan bintang.
Untuk menghentikannya, tekan Ctrl-c. 

Tidak seperti pengulangan menggunakan `for`, pengulangan menggunakan `while`
tidak memiliki kendali jumlah pengulangan.
Akan tetapi, kita dapat membuat sebuah variabel kendali
untuk menentukan jumlah pengulangan menggunakan `while`.
Perhatikan kode berikut.

```python linenums="1"
pengulangan = 0

while (pengulangan < 10):
    print("*", end = "")
    pengulangan = pengulangan + 1
```

Dalam kode tersebut, variabel `pengulangan` akan terus bertambah 1
setiap iterasi melalui baris
```python
pengulangan = pengulangan + 1
```

Pengulangan akan berhenti ketika variabel `pengulangan`
mencapai 10. Mengapa? Karena ketika variabel `pengulangan` mencapai
10, ekspresi boolean `pengulangan < 10` menjadi `False` sehingga
pengulangan berhenti.


**Coba**

1. Kode berikut mencetak angka 1-10, ke samping menggunakan
    `for` dan `while`. Mana yang kamu pilih?
    ```python linenums="1"
    for i in range(10):
        print(i + 1, end = " ")
    ```

    ```python linenums="1"
    angka = 1

    while (angka < 11):
        print (angka, end = " ")
        angka = angka + 1
    ```

1. Jalankan kode berikut dan pahami kodenya.
    ```python linenums="1"
    import random

    angka_acak = random.randint(1,6)
    tebakan = 0

    while (tebakan != angka_acak):
        tebakan = int(input("Masukkan tebakan kamu: "))

    print ("Selamat, tebakan kamu benar")
    ```

---

#### **Kata Kunci `break` dan `continue`**

Salah satu kata kunci penting dalam pengulangan
adalah `break` dan `continue`.

- `break` digunakan untuk **keluar dari loop**.
- `continue` digunakan untuk **lanjut ke iterasi selanjutnya** dalam loop
    dengan mengabaikan kode di sisa loop.

```python linenums="1"
matakuliah = "algoritma dan pemrograman"

for karakter in matakuliah:
    if karakter == ' ':
        break
    print(karakter, end=' ')
```

Kode ini akan menghasilkan output:
```
a l g o r i t m a
```
Sementara kode ini:

```python linenums="1"
matakuliah = "algoritma dan pemrograman"

for karakter in matakuliah:
    if karakter == ' ':
        continue
    print(karakter, end=' ')
```

akan menghasilkan output:
```
a l g o r i t m a d a n p e m r o g r a m a n
```

---

#### **Pengulangan di Dalam Pengulangan**

Jika diperlukan, kita bisa membuat suatu pengulangan di dalam pengulangan.

```python linenums="1"
huruf = "ABC"
angka = "123"

for x in huruf:
    for y in angka:
        karakter = x + y
        print(karakter, end=' ')
```
Kode ini akan menghasilkan output:

```
A1 A2 A3 B1 B2 B3 C1 C2 C3
```

Contoh lain adalah sebagai berikut.

```python linenums="1"
bintang = '*'

for i in range(1, 6):
    for j in range(i):
        print(bintang, end='')
    print('')
```

Kode ini akan menghasilkan output sebagai berikut.
```
*
**
***
****
*****
```
Output yang sama bisa didapatkan dengan memanfaatkan
operator `*` pada string.
```python linenums="1"
bintang = '*'

for i in range(1, 6):
    print(bintang * i, end='')
    print('')
```

**Coba**

Jalankan kode-kode berikut dan pahami algoritmanya.

```python linenums="1"
bintang = '*'

for i in range(5, 0, -1):
    print(bintang * i, end='')
    print('')
```

```python linenums="1"
bintang = '*'

for i in range(1, 10):
    if i < 6: jumlah_bintang = i
    else: jumlah_bintang = 10 - i

    print(bintang * jumlah_bintang, end = '')
    print('')
```

```python linenums="1"
bintang = '*'

for i in range(1, 10):
    if i < 6: jumlah_bintang = 6 - i
    else: jumlah_bintang = i - 4

    print(bintang * jumlah_bintang, end='')
    print('')
```

---

### **Kerjakan**

1. Buat program yang outputnya seperti berikut:
    ```
    *****
    ****
    ***
    **
    *
    $$
    $$$
    $$$$
    $$$$$
    ```

1. Cetak kalimat `Saya senang belajar pemrograman`
    sebanyak `n` kali dengan `n` adalah angka
    yang dimasukkan oleh user.
    Gunakan kerangka program berikut dan hanya ubah
    kode di bagian bertanda `#`.

    ```python linenums="1"
    n = # kode agar user memasukkan input angka

    for # buat statement untuk melakukan loop sebanyak n
        print("Saya senang belajar pemrograman")
    ```

1. Buat program menebak angka acak antara 1–100. User boleh menebak secara berulang-ulang. Setiap kali menebak, program memberi respon **Terlalu besar!** atau **Terlalu kecil!**. Jika benar, program mengeluarkan pesan **Tepat!**. Berikut adalah kerangka programmnya. Ubah kode di bagian yang ditandai tanda `#`.

    ```python linenums="1"
    import random

    angka_acak = random.randint(1,100)

    while (angka_acak != angka_tebakan):
        angka_tebakan =  # Buat input untuk user memasukkan angka

        if # angka_tebakan lebih besar:
            print ("Terlalu besar!")
        elif # angka_tebakan lebih kecil:
            print ("Terlalu kecil!")

    print ("Tepat!")
    ```

1. Tambahkan di kode berikut sehingga di setiap baris terdapat nomor barisnya.
    ```
    1 *
    2 **
    3 ***
    dst.
    ```

    ```python
    bintang = '*'

    for i in range(1, 11):
        print(bintang * i, end = '')
        print('')
    ```

1. Lengkapi program berikut sehingga outpunya seperti berikut.
    Lengkapi dengan menghapus `pass` dan menggantinya
    dengan blok kode yang benar.
    ```
    # ****+
    # ***++
    # **+++
    # *++++
    # **+++
    # ***++
    # ****+
    ```

    ```python
    bintang = '*'
    plus = '+'

    for i in range(1, 8):
        if i < 5:
            print(bintang * (5 - i), end='')
            print(plus * i, end='')
        else:
            pass
        print('')
    ```
