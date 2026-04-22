# **Modul 5: Fungsi**

<!-- ![Status](https://img.shields.io/badge/Status-On_Progress-yellow?style=flat-square) -->
![Status](https://img.shields.io/badge/Status-Finish-brightgreen?style=flat-square)

## **Capaian Pembelajaran Mata Kuliah**

Mampu menggunakan elemen-elemen pemrograman, yaitu fungsi, I/O, dan tipe data buatan sendiri untuk membuat program sederhana berbasis teks.

---

## **Materi**

### **Apa Itu Fungsi?**

Fungsi adalah sebuah program kecil yang menerima input dan menghasilkan output.
Kita sudah menggunakan beberapa fungsi di modul-modul sebelumnya, yaitu

1. `print()`
1. `input()`
1. `type()`
1. `range()`

Contohnya, dalam gambar berikut, fungsi `print()` menerima 2 input dan menghasilkan 1 output,
yaitu `None`. 

<br />

![Fungsi print](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/fungsi_print2.png)

<br />

!!! Catatan
    Fungsi `print()` menghasilkan output berupa nilai yang disebut `None`.
    `None` artinya tidak ada nilai.

!!! Catatan
    Di gambar terlihat ada yang namanya `side effect`.
    Ini adalah efek yang disebabkan fungsi ketika mengubah atau melakukan sesuatu
    di luar dirinya. Dalam hal ini, fungsi `print()` mencetak string ke terminal
    
Sebuah fungsi, dapat menerima nol, satu, atau lebih dari satu input. 
Sementara, sebuah fungsi hanya dapat mengeluarkan satu output.
Jika kita ingin sebuah fungsi mengeluarkan beberapa nilai,
nilai-nilai tersebut harus kita bungkus dalam data yang bisa menampung banyak nilai, seperti
menggunakan list.

Secara umum, untuk menggunakan sebuah fungsi, kita tuliskan seperti berikut.

![Anatomi fungsi dalam Python](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/anatomi_fungsi.png)

Simbol `arg1` dan `arg2` disebut sebagai argumen.
**Argumen** adalah nilai yang kita masukkan ke fungsi sebagai input.
Selain argumen, ada juga istilah parameter.
**Parameter** adalah variabel yang menampung argumen.
Urutan argumen harus sesuai urutan parameter. 

---

### **Dari mana fungsi berasal?**
Fungsi berasal dari 3 sumber.

1. Bawaan Python, contohnya fungsi `print()` dan juga `type()` 
1. Berasal dari modul yang kita import. Misalnya fungsi `randint()` dari modul `random`
1. Kita buat sendiri

Misalkan, kita ingin membuat suatu fungsi yang tugasnya
menentukan sebuah integer itu ganjil atau genap.
Spesifikasinya sebagai berikut.

1. **Nama fungsi**: `genap`
1. **Input**: integer
1. **Output**: `True` atau `False` 
1. **Fungsi**: 
     - Jika input genap, output = `True`
     - Jika input ganjil, output = `False`

Untuk membuatnya, kita tuliskan kode berikut.

```python linenums="1"
def genap(angka):
    if angka % 2 == 0:
        return True
    else:
        return False
```

Sintaks pembuatan suatu fungsi adalah sebagai berikut.

- Diawali dengan Kata kunci `def`. 
- `genap` adalah nama fungsi.
- `angka` dalam tanda kurung adalah **parameter**, yaitu variabel yang menampung input.
- Kata kunci `return` menandai nilai yang dikeluarkan fungsi sebagai output.

![Definisi fungsi](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/def_fungsi.png)

Setelah membuat fungsi `genap`, cara menggunakannya adalah sebagai berikut.
Misal kita diminta membuat program yang outputnya seperti berikut.

![Soal 1](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/soal1.png)

Maka, kita buat programmnya seperti berikut.
Pertama, kita buat dulu definisi fungsinya.

```python linenums="1"
def genap(angka):
    if angka % 2 == 0:
        return True
    else:
        return False
```

Selanjutnya, kita gunakan atau panggil fungsi tersebut
di program utama kita.
Di program berikut, fungsi `genap` kita panggil di baris 8.

```python linenums="6"
n = int(input("Masukkan angka: "))

if genap(n):
    kata = "genap"
else:
    kata = "ganjil"

for i in range(1, n + 1):
    print(i, kata)
```

Ekspresi `genap(n)` di baris 8 disederhanakan menjadi `True` jika `n` genap
sehingga statemen `if genap(n):` berubah menjadi `if True:`.

!!! Catatan
    Fungsi harus didefinisikan sebelum digunakan.

---

**Coba**

1. Buatlah fungsi yang spesifikasinya sebagai berikut.

    - **Nama**: `kata`
    - **Input**: integer
    - **Output**: "ganjil" atau "genap"
    - **Fungsi**:
        - Jika input ganjil, output = "ganjil" (string). 
        - Jika input genap, output = "genap" (string). 

1. Gunakan fungsi `kata` untuk membuat program yang outputnya seperti berikut.

![Soal 2](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/soal2.png)

---

### **Fungsi dengan Banyak Parameter**

Masih ingat dengan istilah positional argument dan keyword argument di
pembahasan [Modul 1](modul1.md#fungsi-print-dengan-banyak-argumen)?
Saat menggunakan atau memanggil fungsi, kita dapat menuliskan argumennya sebagai
berikut (baris 11 dan 12).

```python linenums="1"
def pitagoras(a, b):
    c = a*a + b*b
    print("parameter a = ", a)
    print("parameter b = ", b)
    print("sisi miring = ", c)
    print()

sisi_tegak = 5
sisi_datar = 7
sisi_miring = pitagoras(5, 7)
sisi_miring = pitagoras(a = 5, b = 7)
sisi_miring = pitagoras(b = 7, a = 5)
```

Angka 5 dan 7 di baris 11 dan 12 disebut sebagai keyword argument
karena kita input dengan menuliskan parameternya (keyword).
Sementara, di baris 10, angka 5 dan 7 kita inputkan sebagai positional argument
karena kita tuliskan tanpa disertai parameternya (posisi menentukan
bahwa 5 masuk ke `a` dan 7 masuk ke `b`).

Kita bisa membuat argumen default untuk sebuah fungsi sehingga
saat memanggil fungsi tersebut, kita tidak perlu menuliskan argumennya.

```python linenums="1"
def luas_segitiga(alas, tinggi, satuan = "cm2"):
    luas = (alas * tinggi) / 2
    print(luas, satuan)

alas = 5
tinggi = 3
luas_segitiga(5, 3)
luas_segitiga(5, 3, "m2")
luas_segitiga(5, 3, satuan = "m2")
```

Di kode tersebut, `"cm2"` adalah default argument sehingga saat memanggil
fungsi `luas_segitiga`, kita tidak perlu menginputkan argument-nya (baris 7).
Masih ingat dengan parameter `end` dan `sep` dalam fungsi `print()`?
Yap, betul, keduanya adalah parameter dengan default argument.
Argumen defaultnya masing-masing adalah `end="\n"` dan `sep=" "`.


**Coba**

Buatlah fungsi dengan spesifikasi sebagai berikut.

- **Nama**: `print_karakter`
- **Input**: `n` (integer), karakter `s` (string)
- **Output**: string
- **Fungsi**: mengeluarkan string yang terdiri dari karakter `s` sebanyak `n`  

Contoh, jika dipanggil `print_karakter(5, "%")` akan mengoutputkan data
berupa string `"%%%%%"`.

!!! Catatan
    Fungsi ini mengoutputkan data dan bukan mencetaknya ke terminal.
    Jika ingin mencetak ke terminal, outputnya harus disimpan dalam variabel
    dan variabel ini diinputkan ke fungsi `print`.

---

### **Mengimpor Fungsi dari File Lain**

Kita bisa menulis definisi fungsi di file tersendiri sehingga fungsi tersebut dapat digunakan
program lain. Misalkan kita simpan fungsi `print_karakter` di file bernama `karakter.py`.
Untuk menggunakannya dari file lain, fungsi `print_karakter` harus diimpor terlebih dahulu.

```python
from karakter import print_karakter

cetak = print_karakter(5, "%")
print(cetak)

```

!!! Catatan
    Sintaks untuk mengimpor fungsi dari sebuah file adalah:
    ```
    from <nama_file_tanpa_ekstensi> import <nama_fungsi>
    ```
    File yang diimpor harus berada di direktori yang sama dengan file yang mengimpor.

**Coba**

Tuliskan dua fungsi berikut di satu file dengan nama `aritmatika.py`.
```python linenums="1" title="aritmatika.py"
def tambah(a, b):
    hasil = a + b
    return hasil

def kali(a, b):
    hasil = a * b
    return hasil
```

Buat file baru dengan nama `kalkulator.py`. Lalu lengkapi
program penjumalahan berikut.

```python linenums="1" title="kalkulator.py"
angka1 = 14
angka2 = 15
angka3 = 21
angka4 = 3

# gunakan fungsi tambah untuk menambahkan angka1 dan angka2
# gunakan fungsi kali untuk mengalikan angka3 dan angka4
# cetak kedua hasilnya ke terminal

```

---

### **Variable Scopes**
Salah satu aspek yang sangat penting dalam pembuatan fungsi adalah
cakupan sebuah variabel. Sebagai contoh, tuliskan kode berikut
dan jalankan.

```python linenums="1"
def aneh():
    print(x)
```

Adakah yang aneh? Variabel `x` tidak pernah didefinisikan.
Akan tetapi, ketika kita menjalankan program tersebut, tidak
terjadi error. Kenapa?

Bandingkan dengan program berikut.

```python linenums="1"
def aneh():
    print(x)

aneh()
```
Apakah program ini error?

Bagaimana dengan program berikut.

```python linenums="1"
def aneh():
    print(x)

x = 10
aneh()
```

Bagian kode yang merupakan definisi sebuah fungsi, tidak akan dieksekusi sebelum
fungsi itu dipanggil. Oleh karena itu, variabel `x` yang belum didefinisikan
tidak menyebabkan error, karena memang bagian kode tersebut belum dijalankan.

Di kode terakhir, program tidak error karena definisi `x` ada di baris 4
meskipun `x` pertama kali dituliskan di baris 2.
Dengan kata lain, variabel `x` yang berasal dari luar fungsi dapat dibaca di dalam
fungsi.

!!! Penting
    Variabel yang didefinisikan di luar fungsi, dapat dibaca di dalam fungsi.

Sekarang, perhatikan kode berikut.

```py linenums="1"
def aneh():
    x = 5

print(x)
```

Apa yang terjadi saat program dijalankan?

!!! Penting
    Variabel yang didefinisikan di dalam fungsi, tidak dapat dibaca dari luar fungsi.

Terakhir, coba perhatikan kode berikut.

```py linenums="1"
def aneh():
    x = 5
    print("nilai x di dalam fungsi = ", x)

x = 10
aneh()
```

!!! Penting
    Variabel di luar fungsi, dapat dibaca dari dalam fungsi.
    Akan tetapi, jika di dalam fungsi ada variabel dengan nama yang sama,
    variabel di luar fungsi itu akan tertutupi (shadowed).
    Hal ini disebut dengan variable shadowing.

---

## **Tugas Praktikum**

1. Lengkapi kode berikut sehingga fungsi `kuadrat` mengembalikan nilai kuadrat dari argumennya.

    ```python linenums="1"
    def kuadrat(angka):
        pass  # ganti dengan kode

    a = kuadrat(4)
    print(a)  # hasilnya 16

    b = kuadrat(5)
    print(b)  # hasilnya 25
    ```

1. Buatlah fungsi yang menerima sebuah string lalu mengembalikan jumlah karakter dalam string tersebut.
   **Jangan** gunakan fungsi bawaan `len()`.

    ```python linenums="1"
    def jumlah_karakter(input_string):
        n = 0
        for huruf in input_string:
            if huruf = " ":
                # break atau continue?
                
            n = # tambahkan kode di sini

        return n

    # contoh penggunaan
    x = jumlah_karakter("multimedia")

    # perintah ini harus mencetak angka 10 ke layar
    print(x)
    ```

1. Sebuah robot berada di koordinat x = 0 dan y = 0. Buatlah 4 fungsi:
   `maju()` untuk menambah x satu satuan, `mundur()` untuk mengurangi x satu satuan,
   `kanan()` untuk menambah y satu satuan, dan `kiri()` untuk mengurangi y satu satuan.
   Gunakan kerangka program berikut.

    ```python linenums="1"
    def maju(x, y):
        x = x + 1
        y = y
        return x, y

    def mundur(x, y):
        # kode di sini

    def kanan(x, y):
        # kode di sini

    def kiri(x, y):
        # kode di sini

    selesai = False
    x = 0
    y = 0

    while selesai == False:
        print("---------------")
        print("Pilih perintah untuk robot.")
        print("1. maju")
        print("2. mundur")
        print("3. kanan")
        print("4. kiri")
        print("5. selesai")
        print("---------------")
        perintah = int(input("Masukkan perintah: "))

        if perintah == 1:
            x, y = maju(x, y)
            print(x, y)
        elif perintah == 2:
            x, y = mundur(x, y)
            print(x, y)
        elif perintah == 3:
            x, y = kanan(x, y)
            print(x, y)
        elif perintah == 4:
            x, y = kiri(x, y)
            print(x, y)
        elif perintah == 5:
            selesai = True
            print(x, y)
    ```

1. Ubahlah kode di nomor sebelumnya. Jadikan keempat fungsi menjadi **satu fungsi**
    bernama `gerak(x, y, arah)` yang menerima posisi robot dan arah gerak sebagai argumen.
    Misal, cara memanggilnya adalah `gerak(x, y, "maju")`

1. Buat program kalkulator dengan menu sebagai berikut.
   Setiap operasi dibuat sebagai fungsi tersendiri.

    ```
    (a) Tambah
    (b) Kurang
    (c) Kali
    (d) Bagi
    (e) Keluar
    ```
