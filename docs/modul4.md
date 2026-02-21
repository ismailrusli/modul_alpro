# Modul 4: Pengulangan

![Status](https://img.shields.io/badge/Status-On_Progress-yellow?style=flat-square)
<!-- ![Status](https://img.shields.io/badge/Status-Finish-brightgreen?style=flat-square) -->

## Capaian

Mampu menggunakan elemen-elemen dasar pemrograman, seperti inisialisasi variabel untuk berbagai macam tipe data, menggunakan percabangan, menggunakan pengulangan, membuat dan menggunakan fungsi, serta membuat dan menggunakan tipe data bentukan sendiri.

## Alat dan Bahan

1. Laptop/komputer
2. Internet
3. Python 3.8+
4. Visual Studio Code (atau editor sejenis)

## Materi

### Pengulangan Menggunakan `for .. in range()`

Satu fitur penting dalam pemrograman adalah pengulangan.
Pengulangan digunakan untuk mengulangi baris-baris kode secara berulang-ulang.

```python
# Pengulangan 10 kali

for i in range(10):
    print("ini diprint 10 x")
```

Di Kode 4.1, baris 1 adalah perintah untuk melakukan pengulangan sebanyak 10 kali. Apa yang diulang? Yang diulang adalah baris 2 (baris yang menjorok ke dalam). Coba kerjakan Kode 4.2.

**Kerjakan**
```python
# Minta user memasukkan angka
# Lalu print "Kalimat ini diprint berulang"
# sebanyak angka yang dimasukkan user
```

---

### 4.3.2 Counter

Di Kode 4.1, variabel `i` adalah variabel counter yang nilainya akan berubah setiap kali pengulangan. Untuk jelasnya, perhatikan Kode 4.3.

**Kode 4.3: Variabel i berfungsi sebagai counter**
```python
pengulangan = 10

for i in range(pengulangan):
    print(i)
```

---

### 4.3.3 Variasi Fungsi `range()`

Fungsi `range()` dapat diikuti dengan 1 angka, 2 angka, atau 3 angka (data yang mengikuti fungsi disebut argumen atau parameter).

- Jika diisi **1 parameter** (`range(x)`) maka counter akan bergerak dari `0` sampai `x`.
- Jika diisi **2 parameter** (`range(x, y)`) maka counter akan bergerak dari `x` sampai `y`.
- Jika diisi **3 parameter** (`range(x, y, z)`) maka counter akan bergerak dari `x` sampai `y` dengan counter loncat sebesar `z`.

Perhatikan Kode 4.4 dan Kode 4.5 untuk lebih jelasnya.

**Kode 4.4: Variasi dalam `for .. in range()`**
```python
for i in range(10, 0, -1):  # (awal, akhir, step)
    print(i)
```

**Kode 4.5: Variasi dalam `for .. in range()`**
```python
for i in range(1, 20, 2):
    print(i)
```

**Kode 4.6: Kerjakan**
```python
for i in range(10):
    # Print angka 1 sampai 10
```

**Kode 4.7: Kerjakan**
```python
# Buatlah program yang menerima 3 angka dari user
# Gunakan angka pertama sebagai awal
# Gunakan angka kedua sebagai akhir
# Gunakan angka ketiga sebagai langkah (step)
# Misal: 1, 20, 3
# Maka program akan mencetak angka 1, 4, 7, 10, 13, 16, 19
# yang diprint ke bawah
```

---

### 4.3.4 Pengulangan untuk List, Tuple, dan Dictionary

Pengulangan juga dapat digunakan untuk memanggil setiap item yang ada di dalam list, tuple, atau dictionary. Sebagai contoh, perhatikan Kode 4.8–4.10.

**Kode 4.8: Pengulangan dalam list**
```python
daftar = [1, 2, 3, 4, 5]

for angka in daftar:
    print(angka)
```

**Kode 4.9: Pengulangan dalam tuple**
```python
posisi = (1, 2, 3)

for x in posisi:
    print(x)
```

**Kode 4.10: Pengulangan dalam dictionary**
```python
daftar = {'nama': 'ismail',
          'umur': 45,
          'alamat': 'bandung'}

for key, value in daftar.items():
    print(key, value)
```

Sebagai latihan, kerjakan Kode 4.11–4.13.

**Kode 4.11: Kerjakan**
```python
daftar1 = [1, 2, 3, 4, 5]

for angka in daftar:
    # buatlah list baru yang isinya adalah
    # setiap angka di daftar1 + 5
    # --> [6, 7, 8, 9, 10]
```

**Kode 4.12: Kerjakan**
```python
daftar1 = [1, 2, 3, 4, 5]

for angka in daftar:
    # buatlah list baru yang isinya
    # hanyalah 3 item pertama
    # dari daftar1, yaitu [1, 2, 3]
    # gunakan 'if'
```

**Kode 4.13: Kerjakan**
```python
daftar1 = [1, 2, 3, 4, 5]

for angka in daftar:
    # buatlah list baru yang isinya
    # kata ganjil atau genap
    # sesuai dengan angka di daftar1:
    # ['ganjil', 'genap', 'ganjil', 'genap', 'ganjil']

    # gunakan operator modulus
    # untuk cek ganjil genap
    # angka % 2 == 0 maka genap
    # angka % 2 != 0 maka ganjil
```

---

### 4.3.5 Pengulangan untuk String

Pengulangan juga dapat dilakukan untuk string. Perhatikan Kode 4.14–4.15.

**Kode 4.14: Pengulangan**
```python
matakuliah = "algoritma dan pemrograman"

for huruf in matakuliah:
    print(huruf)
```

**Kode 4.15: Pengulangan**
```python
matakuliah = "algoritma dan pemrograman"

for huruf in matakuliah:
    print(huruf, end=' ')
```

---

### 4.3.6 `break` dan `continue`

Salah satu perintah penting dalam pengulangan adalah `break` dan `continue`.

- `break` digunakan untuk **keluar dari loop**.
- `continue` digunakan untuk **lanjut ke iterasi selanjutnya** dalam loop dengan mengabaikan kode di sisa loop.

Perhatikan Kode 4.16–4.18.

**Kode 4.16: Pengulangan**
```python
matakuliah = "algoritma dan pemrograman"

for karakter in matakuliah:
    if karakter == ' ':
        break
    print(karakter, end=' ')

print('')
```

**Kode 4.17: Pengulangan**
```python
matakuliah = "algoritma dan pemrograman"

for karakter in matakuliah:
    if karakter == ' ':
        continue
    print(karakter, end=' ')

print('')
```

**Kode 4.18: Kerjakan**
```python
nama = input("Silakan masukkan nama panjang: ")

vokal = []
konsonan = []

# lakukan loop
# kumpulkan vokal ke list vokal
# kumpulkan konsonan ke list konsonan
# lalu hitung ada berapa vokal
# dan ada berapa konsonan
```

---

### 4.3.7 Pengulangan di Dalam Pengulangan

Jika diperlukan, kita bisa membuat suatu pengulangan di dalam pengulangan. Perhatikan Kode 4.19–4.23.

**Kode 4.19: Pengulangan**
```python
angka = [1, 2, 3, 4, 5]
huruf = ['a', 'b', 'c', 'd', 'e']

for x in angka:
    for y in huruf:
        karakter = str(x) + y
        print(karakter, end=' ')

    print('')
```

**Kode 4.20: Pengulangan**
```python
bintang = '*'

for i in range(1, 11):
    for j in range(i):
        print(bintang, end=' ')
    print('')
```

**Kode 4.21: Pengulangan**
```python
bintang = '*'
baris_max = 11

for i in range(1, 11):
    for j in range(baris_max - i):
        print(bintang, end=' ')
    print('')
```

**Kode 4.22: Pengulangan**
```python
bintang = '*'
baris = 10

for i in range(1, baris):
    if i < 6:
        for j in range(i):
            print(bintang, end=' ')
    else:
        for j in range(baris - i):
            print(bintang, end=' ')

    print('')
```

**Kode 4.23: Pengulangan**
```python
bintang = '*'
baris = 10

for i in range(1, baris):
    if i < 6:
        for j in range(6 - i):
            print(bintang, end=' ')
    else:
        for j in range(i - 4):
            print(bintang, end=' ')

    print('')
```

Sebagai latihan, kerjakan Kode 4.24.

**Kode 4.24: Kerjakan**
```python
# tambahkan kode berikut sehingga di setiap baris
# terdapat nomor barisnya
# 1 *
# 2 **
# 3 ***
# dst.

bintang = '*'

for i in range(1, 11):
    for j in range(i):
        print(bintang, end=' ')
    print('')
```

**Kode 4.25: Kerjakan**
```python
bintang = '*'
plus = '+'

for i in range(1, 8):
    if i < 5:
        for j in range(5 - i):
            print(bintang, end=' ')
        for j in range(i):
            print(plus, end=' ')
    else:
        # lengkapi bagian else ini
        # sehingga outputnya seperti berikut
        # ****+
        # ***++
        # **+++
        # *++++
        # **+++
        # ***++
        # ****+

    print('')
```

---

### 4.3.8 Pengulangan Menggunakan `while`

Selain menggunakan perintah `for`, pengulangan dalam Python juga dapat menggunakan perintah `while`. Perhatikan Kode 4.26.

**Kode 4.26: Pengulangan menggunakan perintah `while`**
```python
iterasi = 1
while iterasi < 5:
    print("***")
    iterasi = iterasi + 1
```

---

### 4.3.9 Kerjakan

**1. Program Menu Interaktif**

Buat program yang menampilkan menu seperti berikut:

```
#######################
1. Pilihan 1
2. Pilihan 2
3. Pilihan 3
4. Keluar
#######################
Masukkan pilihan Anda:
```

Jika user menekan `1`, keluar tulisan *"Anda memilih angka 1. Tekan Enter untuk melanjutkan"*. Setelah menekan Enter, layar kembali ke menu utama. Jika user menekan `4` (keluar), tuliskan *"Terima kasih"*.

**Kode 4.28: Kerangka program**
```python
import os

# perintah untuk membersihkan layar
os.system('clear')

# untuk Windows, ganti 'clear' dengan 'cls'

print('#######################')
print('1. Pilihan 1')
print('2. Pilihan 2')
print('3. Pilihan 3')
print('4. Keluar')
print('#######################')

pilihan = input("Masukkan pilihan Anda: ")

if pilihan == '1':
    pass
    # print sesuatu
    input()  # program berhenti sebentar menunggu user menekan enter
elif pilihan == '2':
    pass
    # print sesuatu
elif pilihan == '3':
    pass
    # print sesuatu
elif pilihan == '4':
    print("Keluar")
else:
    print("Anda tidak memilih dengan benar")
```

---

**2. Program Kelompokkan Nama**

Buat program yang meminta input 10 nama dari user, lalu kelompokkan berdasarkan huruf awalnya.

**Kode 4.29: Kerangka program**
```python
daftar_nama = {}

for i in range(10):
    nama = input("Masukkan nama ke-" + str(i + 1) + ": ")
    huruf_awal = nama[0]

    if huruf_awal in daftar_nama:
        # jika sudah ada nama berawalan huruf_awal
        # gunakan append
    else:
        # jika belum ada nama berawalan huruf_awal
        daftar_nama[huruf_awal] = [nama]

# print hasilnya dengan rapi (gunakan pengulangan)
```

---

**3. Program Pola Bintang dan Dollar**

Buat program yang outputnya seperti berikut:

**Kode 4.30: Output**
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

---

**4. Program Tebak Angka**

Buat program menebak angka acak antara 1–100. User boleh menebak secara berulang-ulang. Setiap kali menebak, program memberi respon *"terlalu besar"* atau *"terlalu kecil"*. Jika benar, program mengeluarkan pesan *"Tepat!"*.
