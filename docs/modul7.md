# Modul 7: Tipe Data Kustom

![Status](https://img.shields.io/badge/Status-On_Progress-yellow?style=flat-square)
<!-- ![Status](https://img.shields.io/badge/Status-Finish-brightgreen?style=flat-square) -->

## 7.1 Capaian

Mampu menggunakan elemen-elemen dasar pemrograman, seperti inisialisasi variabel untuk berbagai macam tipe data, menggunakan percabangan, menggunakan pengulangan, membuat dan menggunakan fungsi, serta membuat dan menggunakan tipe data bentukan sendiri.

---

## 7.2 Alat dan Bahan

1. Laptop/komputer
2. Internet
3. Python 3.8+
4. Visual Studio Code (atau editor sejenis)

---

## 7.3 Materi

Kita sudah belajar 4 tipe data dasar dalam Python, yaitu integer, string, float, dan boolean. Selain itu, ada juga 3 tipe data lanjutan, yaitu list, tuple, dan dictionary.

Sebagai programer, kita sebenarnya bisa membuat tipe data sendiri. Misalnya ketika membuat program untuk pengelolaan data mahasiswa, daripada menggunakan tipe data dasar untuk menampung data nama, nim, umur, gender, dan alamat, kita dapat menggabungkan data tersebut ke dalam satu tipe data kustom yang kita bikin sendiri, misalnya yang kita sebut `biodata`. Perhatikan Kode 7.1.

### Kode 7.1: Cara mendefinisikan tipe data baru

```python
class biodata:
    def __init__(self, nama, nim, umur, gender, alamat):
        self.nama = nama
        self.nim = nim
        self.umur = umur
        self.gender = gender
        self.alamat = alamat

anggota1 = biodata("budi", 1, 18, 'L', 'bandung')
anggota2 = biodata("wati", 2, 19, 'P', 'jakarta')

print(anggota1.nama, anggota1.umur)
print(anggota2.nama, anggota2.umur)
```

Fungsi `__init__(self, nama, nim, umur, gender, alamat)` disebut sebagai **konstruktor**. Fungsi ini dipanggil setiap kali data dengan tipe `biodata` dibuat, contohnya di baris 9 dan 10 dalam Kode 7.1.

Setiap data bertipe `biodata` dibuat, kita menamakannya sebagai proses **instansiasi** (*instantiation*). Jadi, `anggota1` dan `anggota2` adalah hasil instansiasi dari tipe data (class) `biodata`. Variabel `self` adalah variabel yang hanya dapat diakses di dalam kelas dan merujuk ke setiap hasil instansiasi. Contohnya, `self` di `anggota1` mengacu ke `anggota1` itu sendiri dan bukan ke `anggota2`.

### Kode 7.2: Mengubah nama dan umur

```python
class biodata:
    def __init__(self, nama, nim, umur, gender, alamat):
        self.nama = nama
        self.nim = nim
        self.umur = umur
        self.gender = gender
        self.alamat = alamat

anggota1 = biodata("budi", 1, 18, 'L', 'bandung')
print(anggota1.nama, anggota1.umur)

anggota1.nama = "amir"
anggota1.umur = 19

print(anggota1.nama, anggota1.umur)
```

Selain fungsi konstruktor, ke dalam class juga dapat kita tambahkan fungsi-fungsi lain. Misalnya kita ingin menghitung tahun kelahiran seseorang dari umurnya. Untuk itu kita buat fungsi `hitung_tahun_lahir` di dalam kelas `biodata`. Untuk menghitung tahun lahir, kita perlu memasukkan data tahun sekarang ke dalam fungsi. Perhatikan Kode 7.3.

### Kode 7.3: Menambahkan fungsi hitung tahun lahir di class biodata

```python
class biodata:
    def __init__(self, nama, nim, umur, gender, alamat):
        self.nama = nama
        self.nim = nim
        self.umur = umur
        self.gender = gender
        self.alamat = alamat

    def hitung_tahun_lahir(self, tahun_sekarang):
        tahun_lahir = tahun_sekarang - self.umur
        return tahun_lahir

anggota1 = biodata("budi", 1, 18, 'L', 'bandung')

lahir = anggota1.hitung_tahun_lahir(2024)

print("tahun lahir", anggota1.nama, "adalah", lahir)
```

---

### 7.3.1 Contoh Program

Misalkan kita akan membuat game pertarungan antara jago bela diri. Pertama, kita bisa membuat tipe data baru berupa petarung. Mari kita namakan tipe data ini `Petarung`. Apa sajakah yang dimiliki oleh seorang petarung? Perhatikan Kode 7.4 dan hasilnya di Kode 7.5.

#### Kode 7.4: Tipe data Petarung

```python
import random

class Petarung:
    def __init__(self, nama):
        self.nama = nama
        self.kesehatan = 100
        self.kekuatan = random.randint(0, 100)
        self.kecerdasan = random.randint(0, 100)
        self.kelincahan = random.randint(0, 100)
        self.senjata = random.randint(0, 100)

    def print_data(self):
        print(self.nama)
        print("Kesehatan = ", self.kesehatan)
        print("Kekuatan = ", self.kekuatan)
        print("Kecerdasan = ", self.kecerdasan)
        print("Kelincahan = ", self.kelincahan)
        print("Senjata = ", self.senjata)

naruto = Petarung("Naruto")
naruto.print_data()
```

#### Kode 7.5: Naruto adalah instansiasi dari Petarung

```
Naruto
Kesehatan = 100
Kekuatan = 98
Kecerdasan = 94
Kelincahan = 51
Senjata = 45
```

Mari sekarang kita bikin Sasuke.

#### Kode 7.6: Instansiasi Petarung ke 2 objek

```python
# saya pindahkan class Petarung ke file petarung.py
# lalu saya import
from petarung import Petarung

naruto = Petarung("Naruto")
sasuke = Petarung("Sasuke")

naruto.print_data()
print("----------------------")
sasuke.print_data()
```

#### Kode 7.7: Hasil Kode 7.6

```
Naruto
Kesehatan = 100
Kekuatan = 62
Kecerdasan = 94
Kelincahan = 13
Senjata = 44
----------------------
Sasuke
Kesehatan = 100
Kekuatan = 66
Kecerdasan = 49
Kelincahan = 44
Senjata = 51
```

Sekarang, mari kita tandingkan antara Naruto dan Sasuke. Untuk itu, kita buat tipe data `Tanding` seperti di Kode 7.8 dan kita tandingkan seperti di Kode 7.9. Hasilnya dapat dilihat di Kode 7.10.

#### Kode 7.8: Tipe data Tanding

```python
class Tanding:
    def __init__(self, petarung1, petarung2):
        self.petarung1 = petarung1
        self.petarung2 = petarung2
        self.pemenang = ""

    def mulai(self):
        """
        pemenang pertarungan ditentukan dengan cara sbb.
        setiap sifat antara 2 petarung dibandingkan
        yang lebih besar mendapatkan 1 point.
        pemenang adalah petarung yang memiliki
        point paling besar.
        """
        nilai_petarung1 = 0
        nilai_petarung2 = 0

        if (self.petarung1.kekuatan > self.petarung2.kekuatan):
            nilai_petarung1 = nilai_petarung1 + 1
        elif (self.petarung1.kekuatan < self.petarung2.kekuatan):
            nilai_petarung2 = nilai_petarung2 + 1

        # dan seterusnya untuk kecerdasan, kelincahan,
        # dan juga senjata

        if (nilai_petarung1 > nilai_petarung2):
            self.pemenang = self.petarung1.nama
        elif (nilai_petarung1 < nilai_petarung2):
            self.pemenang = self.petarung2.nama
        else:
            self.pemenang = ""

    def print_pemenang(self):
        if (self.pemenang != ""):
            print("Pemenangnya: " + self.pemenang)
        else:
            print("Seri!!")
```

#### Kode 7.9: Naruto dan Sasuke bertanding

```python
from petarung import Petarung
from tanding import Tanding

naruto = Petarung("Naruto")
sasuke = Petarung("Sasuke")
berantem = Tanding(naruto, sasuke)
berantem.mulai()

print("--------------------")
naruto.print_data()
print("--------------------")
sasuke.print_data()
print("--------------------")
berantem.print_pemenang()
print("--------------------")
```

#### Kode 7.10: Hasil pertandingan

```
--------------------
Naruto
Kesehatan = 100
Kekuatan = 58
Kecerdasan = 43
Kelincahan = 95
Senjata = 70
--------------------
Sasuke
Kesehatan = 100
Kekuatan = 28
Kecerdasan = 20
Kelincahan = 16
Senjata = 92
--------------------
Pemenangnya: Naruto
--------------------
```

---

### 7.3.2 Kerjakan

1. Lengkapi Kode 7.8 dengan bagian perhitungan untuk **kecerdasan**, **kelincahan**, dan juga **senjata**.

2. Lengkapi setiap petarung dengan data **skor**.

3. Buatlah program pertarungan ini agar dilakukan berulang-ulang sampai pemain memutuskan untuk keluar program. Tambahkan menu seperti berikut:
   - (a) Lihat petarung
   - (b) Edit petarung
   - (c) Tambah petarung
   - (d) Hapus petarung
   - (e) Bertanding
   - (f) Keluar

   Untuk menu **Lihat petarung**, tampilkan datanya juga. Selain itu, simpan data setiap petarung dalam file (Gunakan 1 file untuk setiap petarung). Untuk menu **Bertanding**, ketika dipilih menu dilanjutkan dengan pemilihan 2 nama petarung.

4. Tambahkan data jumlah **kalah**, **menang**, dan **seri** untuk setiap petarung.

5. Buatlah agar **kesehatan** setiap petarung yang kalah dikurangi **5 poin**.

6. Buatlah agar setiap kali seorang petarung menang, **kekuatannya bertambah** secara acak antara **1–5 poin**.

7. Buatlah satu fungsi di class `Petarung` untuk **men-generate ulang** nilai-nilai kekuatan, kecerdasan, kelincahan, dan senjatanya namun dengan biaya **kesehatannya dikurangi 10 poin**.
