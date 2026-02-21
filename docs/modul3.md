# Modul 3: Percabangan

![Status](https://img.shields.io/badge/Status-On_Progress-yellow?style=flat-square)
<!-- ![Status](https://img.shields.io/badge/Status-Finish-brightgreen?style=flat-square) -->

## 3.1 Capaian

Mampu menggunakan elemen-elemen dasar pemrograman, seperti inisialisasi variabel untuk berbagai macam tipe data, menggunakan percabangan, menggunakan pengulangan, membuat dan menggunakan fungsi, serta membuat dan menggunakan tipe data bentukan sendiri.

---

## 3.2 Alat dan Bahan

1. Laptop/komputer
2. Internet
3. Python 3.8+
4. Visual Studio Code (atau editor sejenis)

---

## 3.3 Materi

### 3.3.1 `if .. else`

Salah satu fitur dalam Python adalah percabangan. Percabangan digunakan untuk menentukan baris yang dikerjakan selanjutnya. Perhatikan Kode 3.1 lalu lengkapi Kode 3.2.

**Kode 3.1: Percabangan dalam Python**

```python
nilai = 81

if nilai >= 80:
    print("A")
else:
    print("tidak A")
```

Di Kode 3.1 di baris 3, terdapat suatu percabangan. Kode akan terpecah tergantung dari suatu kondisi, yaitu:

1. Jika variabel `nilai` isinya lebih atau sama dengan 80, program dilanjutkan ke baris 4.
2. Jika kebalikannya (artinya kurang dari 80), program dilanjutkan ke baris 6.

**Kode 3.2: Percabangan dalam Python** *(Latihan — lengkapi sendiri)*

```python
nilai = 100

# jika nilai lebih dari 100
# tulis "nilai lebih dari 100"
# jika nilai tidak lebih dari 100
# tulis "nilai tidak lebih dari 100"
```

---

### 3.3.2 `if .. elif .. else`

Jika percabangannya banyak, bisa digunakan perintah `if ... elif ... else` seperti di Kode 3.3.

**Kode 3.3: Percabangan dalam Python**

```python
nilai = 75

if nilai >= 80:   print("A")
elif nilai >= 70: print("AB")
elif nilai >= 65: print("B")
elif nilai >= 60: print("BC")
elif nilai >= 50: print("C")
elif nilai >= 40: print("D")
else:             print("E")
```

Kode 3.3 dapat digambarkan sebagai diagram alir (flowchart) seperti ditunjukkan di Gambar 3.1.

**Kode 3.4: Percabangan dalam Python** *(Latihan — lengkapi sendiri)*

```python
umur = 45

# jika umur lebih dari 40 disebut dewasa,
# jika antara 20 - 40 disebut muda,
# jika antara 10 - 20 disebut remaja
# di bawah 10 disebut anak-anak
```

Perhatikan Kode 3.5 dan Kode 3.6. Coba tulis dan bandingkan hasilnya. Adakah perbedaan kedua kode tersebut?

**Kode 3.5: Percabangan dalam Python**

```python
kuliah = 'alpro'

if kuliah == 'alpro':
    print(kuliah)
elif kuliah == 'pbo':
    print('bukan alpro tapi juga ngoding')
elif kuliah == 'agama':
    print('sama sekali gak ngoding')
```

**Kode 3.6: Percabangan dalam Python**

```python
kuliah = 'alpro'

if kuliah == 'alpro':
    print(kuliah)
if kuliah == 'pbo':
    print('bukan alpro tapi juga ngoding')
if kuliah == 'agama':
    print('sama sekali gak ngoding')
```

---

### 3.3.3 Blok

Setiap pilihan kondisi dalam percabangan, mengarahkan program untuk mengeksekusi suatu blok (sebaris program). Dalam Python, satu blok program dicirikan dengan **indentasi**. Sebagai contoh, perhatikan Kode 3.7.

**Kode 3.7: Blok ditandai dengan indentasi**

```python
nama   = "ismail"
umur   = 45
gender = "L"

if nama == "ismail":
    print(nama)
    print(umur)
    print(gender)
else:
    print("nama tidak dikenal")
    print("umur tidak dikenal")
    print("gender tidak diketahui")
```

Di Kode 3.7, jika variabel `nama` isinya `"ismail"`, maka setelah baris 5, program akan mengeksekusi baris 6–8. Sementara jika `nama` isinya bukan `"ismail"`, setelah baris 5, program akan loncat ke baris 10–12.

---

### 3.3.4 `if .. in list`

Kata kunci `if` dapat digunakan untuk mencari item di dalam list. Perhatikan Kode 3.8.

**Kode 3.8: `if` untuk mencari item di dalam list**

```python
buahbuahan = ['mangga', 'jeruk', 'duren', 'pepaya', 'jambu']

if 'mangga' in buahbuahan:
    print('ada mangga dalam list')
else:
    print('tidak ada mangga dalam list')

if 'semangka' in buahbuahan:
    print('ada semangka dalam list')
else:
    print('tidak ada semangka dalam list')
```

---

### 3.3.5 Contoh Program

Untuk lebih memahami percabangan, tuliskan dan pahami kode-kode berikut.

**Kode 3.9: Percabangan dalam Python**

```python
a = 100
b = 200

if a > b:
    print("A lebih besar dari B")
elif a < b:
    print("A kurang dari B")
else:
    print("A sama dengan B")
```

**Kode 3.10: Percabangan dalam Python**

```python
a = 100
b = 200

c = (a == b)  # apa isi C? True atau False?

if c:
    print("A sama dengan B")
else:
    print("A tidak sama dengan B")
```

**Kode 3.11: Percabangan dalam Python**

```python
import random

angka   = random.randint(1, 5)
tebakan = input("Tebak angka yang di-generate komputer: ")
tebakan = int(tebakan)

if (tebakan == angka):
    print("Anda hebat, tebakan anda benar!!")
else:
    print("Tebakan anda tidak tepat")
    print("Angka yang benar adalah " + str(angka))
```

Ada beberapa hal di Kode 3.11 yang perlu diperhatikan:

1. **Baris 5:** variabel `tebakan` yang tadinya berisi data string, diubah menjadi data integer.
2. **Baris 7:** ekspresi setelah `if` boleh diberi kurung.
3. Untuk setiap blok kode (misal blok `if` dan juga blok `else`), baris-baris dalam kode dituliskan menjorok. Jadi, jika blok `if` yang dijalankan, maka jalankan baris 8. Sementara jika blok `else` yang dijalankan, maka jalankan baris 10 dan 11.

---

## 3.3.6 Kerjakan

1. Buatlah program berikut. User input 10 nama, lalu kelompokkan berdasarkan huruf awal. Masukkan setiap kelompok ke dalam list.
2. Tebak angka. Jika selisih di bawah 10, tulis **"menang"**. Jika di antara 10–30, tulis **"hampir"**. Jika di atas 30, tulis **"jauh"**.
3. Tampilkan 10 barang, lalu minta user memilih barang dengan memasukkan angka. Setelah itu, tunjukkan harga barang. Jika memasukkan angka yang tidak sesuai, beri peringatan.
4. Buat kalkulator. User memasukkan dua angka, lalu memilih operasi. Keluarkan hasilnya.
5. Minta user memasukkan 3 angka. Munculkan ke-3 angka secara terurut.
6. Buat sebuah list nama. Minta user memasukkan nama. Lalu cari apakah nama yang dimasukkan ada dalam list atau tidak.
7. Buat tampilan menu makanan dan minuman dengan harga. Minta user memilih 1 makanan dan 1 minuman. Totalkan harganya.

---

*Gambar 3.1: Diagram alir (flowchart) untuk menjelaskan Kode 3.3 — lihat dokumen asli.*
