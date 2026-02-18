# **Modul 2: Variabel dan Tipe Data**

## **Capaian**

Mampu menggunakan elemen-elemen dasar pemrograman, seperti inisialisasi variabel untuk berbagai macam tipe data, menggunakan percabangan, menggunakan pengulangan, membuat dan menggunakan fungsi, serta membuat dan menggunakan tipe data bentukan sendiri.

## **Alat dan Bahan**

1. Laptop/komputer
1. Internet
1. Python 3.8+
1. Visual Studio Code (atau editor sejenis)

## **Materi**

Secara abstrak, program komputer dapat dilihat seperti gambar berikut.

<br><br>
![Program komputer](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/proses.png)
<br><br>


Program komputer memiliki input dan output. Ke dalam input, dimasukkan data. Dari output, keluar data. Jadi, tugas program komputer adalah memproses data. Dengan kata lain: dari data menjadi data.

Oleh karena program berkaitan erat dengan data, kita mulai juga dengan data. Ada 3 istilah penting dalam pemrograman terkait data, yaitu:

1. Literal
1. Jenis/tipe data
1. Operator

### **Literal**

Literal adalah nilai/isi data.
Contohnya bilangan `5`.
Contoh lain adalah huruf atau sekumpulan karakter (string), misalnya `"a"` dan `"Bandung"`.
Keduanya ditulis dalam tanda petik untuk membedakan dengan perintah yang dipakai dalam bahasa pemrograman.
Di kode berikut, kata `print` yang pertama adalah perintah dan kata `"print"` di dalam tanda petik adalah literal.

```python
print("print")
```

Kita bisa menuliskan literal ke dalam Python Interpreter. Sebagai contoh, ketikkan literal-literal berikut dan tekan Enter setiap kali selesai mengetikkan satu literal.

1. `5`
1. `5.03`
1. `'a'`
1. `'algoritma'`
1. `True`
1. `[1,2,3]`

Sekarang, coba ketikkan `a` (tanpa tanda petik). Apa yang terjadi? Mengapa demikian?

### **Jenis/Tipe Data**

Data tentu bermacam-macam.
Ada data berupa bilangan bulat (Contoh `5`).
Ada data berupa bilangan riil (Contoh `5.03`).
Ada data berupa karakter (Contoh `"a"`).
Ada data berupa rangkaian karakter (Contoh `"algoritma"`).
Ada data berupa nilai kebenaran suatu ekspresi/logika (Contoh `True`).
Ada juga data berupa kumpulan bilangan (Contoh `[1,2,3]`).

Dalam pemrograman, setiap tipe data biasanya ada namanya.
Sebagai contoh, untuk data berupa bilangan bulat, biasanya tipe datanya disebut **integer**.
Untuk data berupa bilangan riil, disebut **float** atau **double**.
Untuk karakter biasanya disebut **char**.
Untuk serangkaian karakter biasanya disebut **string**.
Untuk kumpulan bilangan bisa disebut sebagai **array** atau **list** atau **set** atau lainnya.
Setiap bahasa pemrograman menentukan sendiri tipe datanya.
Pemrogram dapat juga membuat tipe data kustom sesuai kebutuhan.

Coba ketikkan setiap baris berikut ke dalam Python Interpreter (Enter setelah mengetikkan satu baris).

1. `type(5)`
1. `type(5.03)`
1. `type('a')`
1. `type('algoritma')`
1. `type(True)`
1. `type([1,2,3])`

> **Catatan:** Dalam bahasa pemrograman Python, tidak dibedakan antara tipe data `char` dan `string`.
Keduanya dianggap sebagai string.

### **Mendefinisikan Variabel**

Satu komponen penting dari sebuah program adalah variabel.
Variabel digunakan untuk menampung data.
Variabel memiliki nama agar mudah dipanggil.
Contohnya adalah program berikut.

```python
a = 100 # Variabel dengan nama `a`
print(a)
```

Di kode sebelumnya, variabel dengan nama `a` diisi dengan data berupa bilangan `100`.
Kita bisa melambangkannya seperti ini: `a ← 100`.
Baris ketiga adalah baris untuk mencetak isi dari variabel `a` ke layar (via terminal).
Jika kamu menjalankan kode tersebut, hasilnya adalah munculnya angka `100` di terminal.
Berapakah bilangan yang muncul di kode-kode berikut?

```python
a = 100
b = 50
a = b

print(a)  # bilangan berapa yang akan muncul?
```

```python
a = 100
b = 50
a = b
print(b)  # bilangan berapa yang akan muncul?
```

```python
a = 100
b = a
print(b)  # bilangan berapa yang akan muncul?
```

```python
a = 100
b = a
a = a + b
print(a)  # bilangan berapa yang akan muncul?
```

```python
a = 100
b = a + b
print(b)  # bilangan berapa yang akan muncul?
```

```python
a = 100
b = a
a = b + 100
print(a)  # bilangan berapa yang akan muncul?
```

```python
a = 100
b = 50
print(a + b)  # bilangan berapa yang akan muncul?
```

```python
a = 100
b = 50
c = 25
d = a + b + c

print(d)  # bilangan berapa yang akan muncul?
```

```python
a = 100
b = a
c = a + b
a = 30
d = c + a + b
print(d)  # bilangan berapa yang akan muncul?
```

### **Tipe Data Dasar**

Jika kita perhatikan kode-kode sebelumnya, variabel-variabel di sana diisi bilangan bulat atau integer.
Tentu saja variabel bisa diisi selain dari integer.
Misalnya diisi dengan string, float, atau boolean.
Integer, string, float, dan boolean disebut sebagai tipe data.
Lebih jauh, keempatnya merupakan **tipe data dasar** dalam Python.

```python
nama = "ismail" # string
print(nama)
```

```python
a = 1.4 # float
print(a)
```

```python
hujan = True # boolean
print(hujan)
```

```python
nama_depan = "Ismail"
nama_belakang = "Rusli"
nama_lengkap = nama_depan + " " + nama_belakang
print(nama_lengkap)
```

```python
a = 1.5
b = 3.4
c = a * b  # a dikali b
d = a / b  # a dibagi b
print(a, b)
```

```python
a = 1    # integer
b = 2.3  # float
c = a + b  # apa tipe data c?
print(c)
```

```python
a = 2
b = 3
c = a < b
print(c) # Apa hasilnya?
```

```python
a = 4
b = 4
c = (a == b)
d = (a != b)
print(c, d) # Apa hasilnya?
```

Untuk mengetahui tipe data yang terdapat dalam sebuah variabel,
kita dapat menggunakan perintah `type`. 

```python
nama = "budi"
umur = 20
laki_laki = True
ipk = 3.9

print(type(nama))
print(type(umur))
print(type(laki_laki))
print(type(ipk))
```

Python adalah bahasa pemrograman yang cukup fleksibel.
Saat membuat variabel, kita tidak perlu menentukan tipe data dari variabel tersebut.
Bahkan, sebuah variabel dapat menampung tipe data yang berbeda-bedar.

```python
x = "budi"  # tipe data string
print(x)

x = 100  # tipe data integer
print(x)
```

### **Tipe Data Lanjut**

Selain tipe data dasar, seperti integer, float, string, dan boolean, terdapat juga tipe data lanjut.
Berikut adalah beberapa contoh tipe data lanjut.

#### **List**

List dapat dianggap sebagai daftar.
Sebuah list dapat berisi daftar integer, string, float, atau boolean.
List juga dapat berisi daftar campuran.

```python
# variabel a berisi tipe data list
# yang berisi 6 integer

a = [1,2,3,4,5,6]
print(a)
```

```python
a = [1.5, 2.3, 0.1, 7.9, -3.2]
print(a)
```

```python
a = ['aku', 'adalah', 'indonesia']
print(a[0], a[1], a[2])
```

```python
a = [True, False, False, True]
print(a)
```

```python
a = [1, "nama", 3.7, True]
print(a)
```

Untuk mengambil satu data dari list, gunakan kurung siku. 

```python
a = [1,2,3,4,5]
print(a[0], a[1])
```

Untuk mengakses data pertama dalam list, gunakan indeks `0`.

```python
a = ['aku', 'adalah', 'indonesia']
print(a[0], a[1], a[2])
```

Untuk mengakses data terakhir dalam list,
gunakan indeks `-1` jika kita tidak tahu ada berapa elemen di dalam list tersebut.

```python
a = [1,2,3,4,5]
print(a[-1])
```

Untuk menambahkan data ke akhir list, gunakan perintah `append`.

```python
a = [1,2,3,4,5]
a.append(6)
print(a)
```

Sementara untuk menambah data di sembarang posisi, gunakan perintah `insert`.

```python
a = ["nama", "ismail"]
a.insert(1, "saya")
print(a)
```

Untuk menghapus data di list, gunakan perintah `remove`, `pop`, atau `del`.

```python
a = [21,22,23,24,25]
a.remove(21)  # hapus 21
print(a)

a = [21,22,23,24,25]
a.pop(2)  # hapus indeks ke-2, yaitu 23
print(a)

a = [21,22,23,24,25]
del a[1]  # hapus indeks ke-1, yaitu 22
print(a)
```

Dua list juga bisa digabungkan.

```python
a = [1,2,3]
b = [4,5,6]
c = a + b
print(c)
```

Untuk mengetahui jumlah data dalam list, gunakan perintah `len`.

```python
a = [1,2,3,4,5,6]
panjang_a = len(a)

print(panjang_a)
```

Sebagai latihan, coba pahami kode-kode berikut.

```python
a = [1,2,3,4,5]
b = [5,4,3,2,1]
c = (a == b)
print(c) # Apa hasilnya?
```

```python
a = [1,2,3,4,5]
b = [a[1], a[3]]
print(b) # Apa hasilnya?
```

```python
a = [1,2,3,4,5,6,7,8,9,10]
b = a[:3]
c = a[3:]
d = a[3:6]
print(b, c, d) # Apa hasilnya?
```

```python
a = [1,2,3]
b = [4,5,6]
c = [a, b]
print(c)
print(c[0])
print(c[0][0]) # Apa hasilnya?
```

```python
a = [1,2,3,4,5,6,7,8,9,10]
a.pop(1)
b = a[3]
c = b + a[2]
a.insert(3, c)
print(a) # Apa hasilnya?
```

```python
a = [1,2,3,4,5,6,7,8]
b = a + [1]
print(b) # Apa hasilnya?
```

#### **Tuple**

Tuple mirip seperti list hanya saja elemen di dalam tuple tidak dapat diubah.
Tuple juga dituliskan dalam kurung biasa sementara list dituliskan dalam kurung siku.

```python
a = (1,2,3,4,5)
print(a)     # print tuple
print(a[0])  # akses data tuple

a[0] = 100   # error, element tuple tidak dapat diubah
print(a[0])
```

Dua tuple dapat digabungkan dengan menggunakan simbol `+`.

```python
a = (1,2,3)
b = (4,5,6)

print(a + b)
```

Tuple digunakan untuk merepresentasikan data yang ukurannya sudah diketahui,
misalnya posisi objek dalam ruang 3 dimensi → `(x, y, z)`.

#### **Dictionary**

Dictionary, seperti artinya yaitu kamus.
Dictionary adalah tipe data yang terdiri dari pasangan **key** dan **value**.
Dalam kamus, misalnya kamus Indonesia-Inggris, setiap entri terdiri dari 2 item, yaitu kata dan artinya.
Dalam dictionary juga sama.

```python
daftar_nama_umur = {
    'budi': 30,
    'wati': 35,
    'amran': 35
}

print(daftar_nama_umur)
print(daftar_nama_umur['budi'])
```

Di kode tersebut, kita lihat pasangan datanya bertipe string dan integer (`'budi' : 30`).
Setiap pasang dalam satu dictionary tidak harus memiliki tipe data yang sama dan key tidak harus string.

```python
data_anggota = {
    'nama': 'budi',          # string : string
    'umur': 30,              # string : integer
    'berat': 59.6,           # string : float
    'gender': True,          # string : bool
    'nilai': [9, 8.5, 8, 7.7, 10],  # string : list
    'posisi': (3.5, 2.0, 45.3)      # string : tuple
}

print(data_anggota)
```

Untuk menambah, mengganti, atau menghapus data di dictionary, perhatikan kode berikut.

```python
data_anggota = {
    'nama': 'budi',
    'umur': 30,
    'ttl': 'bandung, 20 januari 1900',
    'alamat': 'jl. dimanapun no. 100'
}
```
 
Di Kode 2. 5, ditunjukkan dua cara untuk menghapus data dari dictionary, yaitu menggunakan perintah `del` dan `pop`.
Selain dari kedua perintah tersebut, terdapat perintah lain juga.
Kamu dapat mengetahui perintah-perintah yang ada di Python dengan mencarinya di [Google](https://www.3schools.com/python/default. sp).

```python
print("===== print dictionary =====")
print(data_anggota, '\n')

data_anggota['nama'] = 'dudi'
print("===== ganti nama =====")
print(data_anggota, '\n')

data_anggota['gender'] = 'L'
print("===== tambah gender =====")
print(data_anggota, '\n')

del data_anggota['alamat']
print("===== hapus alamat menggunakan del =====")
print(data_anggota, '\n')

data_anggota.pop('ttl')
print("===== hapus ttl menggunakan pop =====")
print(data_anggota, '\n')

# '\n' digunakan untuk membuat baris baru
```

Untuk mendapatkan semua key dari dictionary, perhatikan kode berikut. 

```python
data_anggota = {
    'nama': 'budi',
    'umur': 30,
    'ttl': 'bandung, 20 januari 1900',
    'alamat': 'jl. dimanapun no. 100'
}

key = data_anggota.keys()
print(type(key))
print(key)
```

### **Operator**

Dua variabel dapat dioperasikan menggunakan operator.

```python
# Operator aritmatika

a = 5
b = 7
c = a + b
d = a - b
e = a / b
f = a * b
g = b % a  # mod

print(a, b, c, d, e, f, g)
```

Kode 2.47 menunjukkan operator aritmatika. Jenis operator lainnya adalah **operator perbandingan**. Operator perbandingan digunakan untuk membandingkan 2 variabel. Perhatikan Kode 2.48.

**Kode 2.48: Operator perbandingan**
```python
a = 5
b = 7
c = a < b   # lebih kecil
d = a > b   # lebih besar
e = a == b  # sama dengan
f = a != b  # tidak sama dengan
g = a <= b  # lebih kecil atau sama dengan
h = a >= b  # lebih besar atau sama dengan

print(a, b, c, d, e, f, g, h)
```

Untuk variabel tipe data string, simbol `+` dapat digunakan untuk menggabungkan dua string atau lebih (concatenation). Perhatikan Kode 2.49.

**Kode 2.49: Penggabungan 2 variabel string menggunakan operator `+`**
```python
nama_depan = "Budi"
nama_belakang = "Kusnadi"
nama_lengkap = nama_depan + " " + nama_belakang
print(nama_lengkap)
```

Selain itu, ada juga **operator logika**. Contohnya di Kode 2.50.

**Kode 2.50: Operator logika**
```python
a = True
b = False

c = a and b
d = a or b
e = not a

print(a, b, c, d, e)
```



### 2.3.7 Input

Salah satu yang membuat sebuah program interaktif adalah program tersebut dapat menerima input dari pengguna. Perhatikan contoh di Kode 2.51. Jalankan program tersebut. Apa yang terjadi?

**Kode 2.51: Program yang dapat menerima input dari pengguna**
```python
nama = input("Siapa nama Anda: ")
print("Salam kenal" + nama)
```

Sekarang perhatikan contoh program input lainnya di Kode 2.52. Jalankan program tersebut dan apa yang terjadi?

**Kode 2.52: Program yang meminta pengguna input angka**
```python
a = input("Masukkkan angka pertama = ")
b = input("Masukkkan angka kedua = ")
c = a + b
print("Jumlah 2 angka yang anda masukkan adalah " + c)
```

Apakah tipe data dari variabel `a`, `b`, dan `c` dalam Kode 2.52? Ya, betul, tipe data ketiga variabel tersebut adalah string. Agar masukan pengguna dapat kita anggap sebagai bilangan, kita harus mengubahnya dulu (**type casting**). Perhatikan Kode 2.53, tulis dan jalankan program tersebut.

**Kode 2.53: Variabel `a` dan `b` diubah ke integer dan `c` diubah ke string**
```python
a = input("Masukkkan angka pertama = ")
b = input("Masukkkan angka kedua = ")
c = int(a) + int(b)
print("Jumlah 2 angka yang anda masukkan adalah " + str(c))
```

Perintah di baris 3 adalah menyuruh komputer untuk mengubah terlebih dahulu variabel `a` ke integer (`int(a)`), lalu variabel `b` ke integer (`int(b)`), kemudian menjumlahkan 2 integer tersebut dan menyimpannya di `c`.



### 2.3.8 Contoh Program

Kode 2.54 adalah contoh program sederhana memilih menu di restoran. Tulis program tersebut dan jalankan. Apa yang terjadi?

**Kode 2.54: Program menu**
```python
print("")
print("====================================")
print("Selamat datang di restoran Sukelezat.")
print("====================================")
print("")

makanan = input("Silakan tuliskan makanan yang kamu pesan: ")

minuman = input("Sekarang, silakan tuliskan minuman yang kamu pesan: ")

print("")
print("Terima kasih, pesanan Anda adalah " + makanan + " dan " + minuman)
```

### 2.3.9 Kerjakan

**1.** Terdapat error di Kode 2.55 – Kode 2.62. Perbaikilah.

**Kode 2.55: Perbaiki program berikut.**
```python
a = 100
b

print(b)
```

**Kode 2.56: Perbaiki program berikut.**
```python
a = 100
b = 200

print(c)
```

**Kode 2.57: Perbaiki program berikut.**
```python
a = 100
b = "seratus"

print(a + b)
```

**Kode 2.58: Perbaiki program berikut.**
```python
a = 3.2
b = 2.0
c = a / (b - 2.0)

print(c)
```

**Kode 2.59: Perbaiki program berikut.**
```python
a = [1,2,3]
a.append(7)

print(a[4])
```

**Kode 2.60: Perbaiki program berikut.**
```python
a = (1,2,3,4,5)
a[0] = 8

print(a)
```

**Kode 2.61: Perbaiki program berikut.**
```python
a = [1,2,3]
b = [4,5,6]
c = [7,8,9,a,b]

print(c[3][1])
print(c[2][1])
```
**Kode 2.62: Perbaiki program berikut.**
```python
a = {"nama": "budi", "umur": 20}
print(a["budi"])
```
**2.** Buatlah program yang menerima input dari user berupa angka 0–9, lalu munculkan string yang bersesuaian. Misalnya, user memasukkan angka 1, maka print string `"satu"`. *Petunjuk: Gunakan list untuk menyimpan kata-katanya.*

**3.** Komputer dapat menghasilkan bilangan acak seperti yang tertulis di Kode 2.63.

**Kode 2.63: Komputer menghasilkan bilangan acak antara 1–100**
```python
import random

r = random.randint(1, 100)
print(r)
r = random.randint(1, 100)
print(r)
r = random.randint(1, 100)
print(r)
r = random.randint(1, 100)
print(r)
```

Buatlah suatu game sederhana. Program men-*generate* angka acak antara 0–100. User menebak angka yang di-*generate* komputer (inputkan angkanya). Munculkan skor tebakannya dengan cara menentukan selisih antara angka komputer dan angka tebakannya. Perhatikan contoh di Kode 2.64.

**Kode 2.64: Contoh program tebak angka.**
```
Tebak angka yang di-generate komputer: 50
Skor anda adalah: 34
Angka yang di-generate komputer adalah: 84
```

**4.** Suatu list dapat diubah menjadi tuple, carilah caranya di Internet lalu buat program contohnya. Buat juga sebaliknya, yaitu dari tuple menjadi list.

**5.** Buat program yang memunculkan nama 5 huruf secara random dengan ketentuan, huruf ke-2 dan ke-4 vokal, sisanya konsonan. *Petunjuk: gunakan dua list, yaitu list untuk vokal dan list untuk konsonan. Lalu gunakan fungsi random untuk mengambil huruf dari kedua list tersebut.*

**6.** Buat seperti program nama acak sebelumnya, tapi minta user untuk memasukkan huruf pertama nama acak tersebut.

**7.** Buat program pertandingan dengan skenario sebagai berikut.

- (a) Ketika program dijalankan, user diminta memasukkan nama pertama, lalu enter.
- (b) Selanjutnya, user diminta memasukkan nama ke-2, lalu enter.
- (c) Lalu program menuliskan nama pertama dan skornya (random antara 0–100) serta nama kedua dan skornya (dalam baris berbeda).

**8.** Buatlah program yang mengacak kata. Skenarionya adalah, user diminta untuk memasukkan kata, lalu tampilkan versi teracak dari kalimat tersebut (kata-katanya diacak). *Petunjuk: gunakan fungsi `split` untuk memisahkan kalimat ke dalam list dari kata-kata. Lalu gunakan `random.shuffle()` untuk mengacak list tersebut. Selanjutnya, gabungkan lagi kata-kata dalam list tersebut menggunakan perintah `" ".join(list)`.*
