# **Modul 7: Tipe Data Komposit dan Tipe Data Kustom**

<!-- ![Status](https://img.shields.io/badge/Status-On_Progress-yellow?style=flat-square) -->
![Status](https://img.shields.io/badge/Status-Finish-brightgreen?style=flat-square)

## **Capaian Pembelajaran Mata Kuliah**

Mampu menggunakan elemen-elemen pemrograman, yaitu fungsi, I/O, dan tipe data buatan sendiri untuk membuat program sederhana berbasis teks.

---

## **Materi 1: Tipe Data Komposit**

Kita sudah belajar 4 tipe data dasar dalam Python, yaitu integer, string, float, dan boolean.
Setiap data dengan tipe ini hanya bisa menampung satu value.

Selain tipe data dasar, Python juga memiliki tipe data komposit.
Satu tipe data komposit dapat menampung nol, satu, atau lebih dari satu value.
Kita akan belajar dua data komposit di modul ini, yaitu list dan dictionary.
Selain list dan dictionary, Python juga sebenarnya memiliki tipe data komposit
lain, yaitu set dan tuple.

### **List**

List dapat dianggap sebagai daftar. Untuk membuat list, perhatikan kode berikut.

```py
daftar_nama = ['budi', 'wati', 'rudi', 'santi']
```

![List](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/list.png)


Terhadap suatu list, biasanya kita melakukan hal-hal berikut.

1. Mengambil satu nilai dari list
1. Mengambil beberapa nilai sekaligus dari list
1. Mengganti satu nilai dari list
1. Menghitung jumlah nilai dalam list
1. Menambah nilai ke dalam list
1. Menghapus nilai di dalam list

**Mengambil Satu Nilai dari List**

Untuk mengambil hanya satu nilai dari list, kita gunakan indexing.
Setiap nilai dalam list diurutkan dan diberi indeks.
Nilai pertama diberi index 0.
Nilai kedua diberi index 1 dan seterusnya.

```py linenums="1"
daftar_nama = ['budi', 'wati', 'rudi', 'santi']

nama1 = daftar_nama[0] # indeks ke-0 adalah "budi"
 
print(nama1) 
```

Masih ingat dengan konsep [iterabel](modul4.md#iterabel)?
List adalah sebuah iterabel.
Oleh karen itu, kita bisa menggunakannya dalam sebuah `for` loop
untuk mengambil nilai yang ada di dalam list satu per satu.

```py linenums="1"
daftar_nama = ['budi', 'wati', 'rudi', 'santi']

for nama in daftar_nama:
    print(nama)
```

**Mengambil Beberapa Nilai Sekaligus dari List**

Di beberapa kasus, kita ingin mengambil tidak satu nilai dari list,
tapi sebagian. Misalnya, kita ingin mengambil nilai dari awal (indeks ke-0)
hingga indeks ke-2. Kita bisa gunakan cara pemotongan list (slicing) seperti dalam kode berikut.

```py linenums="1"
daftar_nama = ['budi', 'wati', 'rudi', 'santi', 'sinta', 'dudi', 'dede', 'andi']

beberapa_nama = daftar_nama[:3]  # sama dengan [0:3]
print(beberapa_nama)
```

Bagaimana jika kita ingin mengambil nama dari `"wati"` (indeks 1) hingga `"dudi"`
(indeks 5)? 

```py linenums="1"
daftar_nama = ['budi', 'wati', 'rudi', 'santi', 'sinta', 'dudi', 'dede', 'andi']

beberapa_nama = daftar_nama[1:6]
print(beberapa_nama)
```

Bagaimana jika kita ingin mengambil nilai dari `"sinta"` (indeks 4) hingga nilai terakhir?


```py linenums="1"
daftar_nama = ['budi', 'wati', 'rudi', 'santi', 'sinta', 'dudi', 'dede', 'andi']

beberapa_nama = daftar_nama[4:]
print(beberapa_nama)
```

**Mengganti Satu Nilai di List**

Untuk mengganti satu nilai di List, perhatikan kode berikut.

```py linenums="1"
daftar_siswa = ["budi", "wati", "rudx", "santi"]

# sebelum diganti
print(daftar_siswa)

#setelah diganti
daftar_siswa[2] = "rudi"  # rudi adalah nilai ke-3, berarti indeks-nya 2
print(daftar_siswa)
```

**Menghitung Jumlah Nilai Dalam List**

Untuk menghitung jumlah data dalam list, gunakan fungsi
`len()` yang merupakan fungsi bawaan dari Python.

```py linenums="1"
daftar_siswa = ["budi", "wati", "rudi", "santi"]

jumlah_siswa = len(daftar_siswa)
print(jumlah_siswa)
```

**Menambah Nilai ke List**

Untuk menambah data ke dalam list, kita bisa menggunakan
fungsi `append` atau `insert`. 

Fungsi `append` digunakan untuk menambahkan nilai di akhir list.
Sementara fungsi `insert` digunakan untuk menambahkan nilai
di sembarang urutan.

```py linenums="1" title="Menambah nilai menggunakan fungsi append"
daftar_siswa = ["budi", "wati", "rudi", "santi"]

daftar_siswa.append("doni")
print(daftar_siswa)
```

```py linenums="1" title="Menambah nilai menggunakan fungsi insert"
daftar_siswa = ["budi", "wati", "rudi", "santi"]

daftar_siswa.insert(0, "doni")  # artinya "doni" akan disimpan di indeks 0
print(daftar_siswa)
```

**Menghapus Nilai di List**

Untuk menghapus nilai dari sebuah list, kita gunakan fungsi
`remove`, `pop`, atau `del`.

```py linenums="1" title="Menghapus nilai menggunakan fungsi remove"
daftar_siswa = ["budi", "wati", "rudi", "santi"]

daftar_siswa.remove("wati")
print(daftar_siswa)
```

```py linenums="1" title="Menghapus nilai menggunakan fungsi pop"
daftar_siswa = ["budi", "wati", "rudi", "santi"]

daftar_siswa.pop(1) # hapus indeks ke-1 ("wati")
print(daftar_siswa)
```

```py linenums="1" title="Menghapus nilai menggunakan fungsi del"
daftar_siswa = ["budi", "wati", "rudi", "santi"]

del daftar_siswa[2]  # hapus indeks ke-2 ("rudi")
print(daftar_siswa)
```

**Menggabungkan Dua atau Lebih List**

Kita bisa menggabungkan dua atau lebih list menjadi satu list.

```py linenums="1"
angka1 = [1, 2, 3]
angka2 = [4, 5, 6]
angka3 = [7, 8, 9]

angka = angka1 + angka2 + angka3
print(angka)

```


!!! Catatan
    List dapat juga dibuat dengan mendaftarkan variabel. Akan tetapi,
    isi list adalah isi dari variabelnya (value-nya).

    ```py linenums="1"
    a = 1, b = 2, c = 3

    x = [a, b, c]
    print(x)

    a = 5
    print(x)
    ```

### **Dictionary**

Tipe data lain adalah dictionary.
Jika list seperti daftar,
dictionary seperti kamus.

Setiap item dalam list terdiri satu nilai.
Sementara, satu item dalam dictionary terdiri dari
sepasang nilai, yaitu `key` dan `value`. 
`key` adalah seperti entri dalam kamus
sementara `value` adalah definisinya.

```py linenums="1"
biodata = {
    "nama" : "budi",
    "umur": 25,
    "pekerjaan": "mahasiswa"
}
```

![List](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/dictionary.png)

Pasangan `key`:`value` dalam `biodata` adalah sebagai berikut.

| Key | Tipe data | Value | Tipe data |
| --- | --- | --- | --- |
| "nama" | string |  "budi" | string |
| "nama" | string | 25 | integer |
| "pekerjaan" | string |  "mahasiswa" | string |

Proses yang biasanya kita lakukan terhadap dictionary adalah
sebagai berikut.

1. Mengambil `value` berdasarkan `key`
1. Mengganti `value` untuk suatu `key` tertentu
1. Menghitung jumlah item (`key`:`value`) dalam suatu dictionary
1. Mengambil semua `key` atau `value` dalam dictionary
1. Menghapus item

**Mengambil `value` berdasarkan `key`**

```py linenums="1"
biodata = {
    "nama": "budi",
    "umur": 25,
    "pekerjaan": "mahasiswa"
}

nama_anggota = biodata["nama"]
umur_anggota = biodata["umur"]
pekerjaan_anggota = biodata["pekerjaan"]

print(nama_anggota)
print(umur_anggota)
print(pekerjaan_anggota)
```

Jika list adalah sebuah iterabel, apakah dictionary juga?
Jawabannya adalah iya.
Untuk dapat melakukan iterasi terhadap sebuah dictionary,
perhatikan kode berikut.

```py linenums="1"
biodata = {
    "nama": "budi",
    "umur": 25,
    "pekerjaan": "mahasiswa"
}

for item in biodata:
    print(item)
```

Akan tetapi, kode di atas hanya melakukan iterasi terhadap `key` saja.
Jika kita ingin melakukan iterasi terhadap `key` dan `value`,
perhatikan kode berikut.

```py linenums="1"
biodata = {
    "nama": "budi",
    "umur": 25,
    "pekerjaan": "mahasiswa"
}

for key, value in biodata.items():
    print(key, value)
```



**Mengganti `value` untuk suatu `key` tertentu**

```py linenums="1"
biodata = {
    "nama": "budi",
    "umur": 25,
    "pekerjaan": "mahasiswa"
}

biodata["umur"] = 26
print(biodata)

```

**Menghitung jumlah item (`key`:`value`) dalam suatu dictionary**

Untuk menghitung jumlah item dalam suatu dictionary, kita
gunakan fungsi `len`.

```py linenums="1"
biodata = {
    "nama": "budi",
    "umur": 25,
    "pekerjaan": "mahasiswa"
}

print(len(biodata))

```

**Mengambil semua `key` atau `value` dalam dictionary**

Terkadang kita ingin mengetahui semua `key` atau `value` yang
ada di dalam suatu dictionary. Untuk itu, kita bisa gunakan
fungsi `keys()` dan `values()`.

Agar daftar `key` dan `value` yang dihasilkan disimpan dalam bentuk
list, kita bisa gunakan fungsi `list()`.

```py linenums="1"
biodata = {
    "nama": "budi",
    "umur": 25,
    "pekerjaan": "mahasiswa"
}

datakey = biodata.keys()
datavalue = biodata.values()

# ubah menjadi list agar mudah diubah-ubah
datakey = list(datakey)
datavalue = list(datavalue)

print(datakey)
print(datavalue)

```

Tanpa mengubahnya ke list, output dari fungsi `keys()` dan `values()`
juga adalah sebuah iterabel. Jadi, kita bisa melakukan hal yang
seperti berikut.

```py linenums="1"
biodata = {
    "nama": "budi",
    "umur": 25,
    "pekerjaan": "mahasiswa"
}

for key in biodata.keys():
    print(key)

for value in biodata.values():
    print(value)
```

**Menghapus item**

Untuk menghapus item di dictionary, kita bisa menggunakan
fungsi `del` atau `pop`.

```py linenums="1" title="Menghapus item menggunakan del"
biodata = {
    "nama": "budi",
    "umur": 25,
    "pekerjaan": "mahasiswa"
}

del biodata["pekerjaan"]
print(biodata)

```


```py linenums="1" title="Menghapus item menggunakan pop"
biodata = {
    "nama": "budi",
    "umur": 25,
    "pekerjaan": "mahasiswa"
}

biodata.pop("pekerjaan")
print(biodata)

```

**Coba**

1. Apa hasil dari kode-kode berikut?

    ```py linenums="1"
    a = [1, 2, 3, 4, 5]
    b = [5, 4, 3, 2, 1]
    c = (a == b)

    # Apa isi variabel c?
    ```

    ```py linenums="1"
    a = [1, 2, 3, 4, 5]
    b = [a[1], a[3]]

    # Apa isi variabel b?
    ```

    ```py linenums="1"
    a = [1, 2, 3, 4, 5, 6, 7, 8, 9 ,10]
    b = [:3]
    c = [3:]
    d = [3:6]

    # Apa isi b + c + d?
    ```

    ```py linenums="1"
    a = [1, 2, 3]
    b = [4, 5, 6]
    c = [a, b]

    # Apa isi c, c[0], dan c[0][0]
    ```

    ```py linenums="1"
    a = [1, 2, 3, 4, 5, 6, 7, 8, 9 ,10]
    a.pop(1)

    b = a[3]

    c = b + a[2]

    a.insert(3, c)

    # Apa isi a?
    ```

    ```py linenums="1"
    a = [1, 2, 3, 4, 5, 6, 7, 8]
    b = a + [1]

    # Apa isi b?
    ```

1. Perhatikan dictionary berikut.
```py linenums="1"

daftar = {
    "budi": {
        "umur": 25,
        "alamat": "bandung",
        "menikah": False
    },
    "wati": {
        "umur": 29,
        "alamat": "jakarta",
        "menikah": True
    },
    "rudi": {
        "umur": 18,
        "alamat": "medan",
        "menikah": False
    },
}

# Apa isi dari daftar["budi"]?
# Buat kode untuk mengambil data alamat Budi?
# Buat kode untuk menghitung rata-rata umur budi, wati, dan rudi?
```


## **Materi 2: Tipe Data Kustom**

Jadi, tipe data apa saja yang sudah kita pelajari?
Ada tipe data dasar, yaitu `int`, `float`, `string` dan `boolean`.
Ada juga tipe data komposit, contohnya `list` dan `dictionary`.

Sebagai seorang programer, kita sebenarnya bisa membuat tipe data sendiri.
Misalnya, kita membuat program untuk pengelolaan data mahasiswa.
Untuk setiap mahasiswa, kita simpan data: nama, NIM, gender, umur, dan alamat.
Dalam tipe data apa data ini kita simpan?

```py title="Menggunakan tipe data dasar"
nama_mhs1 = "Budi"
nim_mhs1 = 123
gender_mhs1 = "L"
umur_mhs1 = 19
alamat_mhs1 = "Bandung"

nama_mhs2 = "Wati"
nim_mhs2 = 321
gender_mhs2 = "P"
umur_mhs2 = 18
alamat_mhs2 = "Jakarta"
```

```py title="Menggunakan list"
mhs1 = ["budi", 123, "L", 19, "Bandung"]
mhs2 = ["wati", 321, "P", 18, "Jakarta"]

mahasiswa = [mhs1, mhs2]  # list of list

# Cetak nama mahasiswa
print("Nama ke-1: ", mhs1[0])
print("Nama ke-2: ", mhs2[0])
```

```py title="Menggunakan dictionary"
mhs1 = {
    "nama": "Budi",
    "nim": 123,
    "gender": "L",
    "umur": 19,
    "alamat": "Bandung"
}

mhs2 = {
    "nama": "Wati",
    "nim": 321,
    "gender": "P",
    "umur": 18,
    "alamat": "Jakarta"
}

mahasiswa = [budi, wati]  # list of dictionary

# Cetak nama mahasiswa
print("Nama ke-1: ", mhs1["nama"])
print("Nama ke-2: ", mhs2["nama"])
```

Manakah yang lebih efisien untuk menampung data mahasiswa?
Untuk kasus ini, sepertinya list atau dictionary cukup cocok.
Akan tetapi, kita sebenarnya bisa membuat tipe data baru
agar sesuai kebutuhan kita.
Untuk itu, perhatikan kode berikut.

```py linenums="1"
class mahasiswa:
    def __init__(self, nama, nim, umur, gender, alamat):
        self.nama = nama
        self.nim = nim
        self.umur = umur
        self.gender = gender
        self.alamat = alamat


mhs1 = mahasiswa("Budi", 123, 19, 'L', 'Bandung')
mhs2 = mahasiswa("Wati", 321, 18, 'P', 'Jakarta')

print("Nama ke-1:", mhs1.nama)
print("Nama ke-2:", mhs2.nama)
```

Untuk membuat tipe data baru, kita menggunakan kata kunci `class`.
`class` adalah seperti template dari tipe data baru yang akan kita buat.
Setiap kita membuat data yang memiliki tipe data baru ini (baris 10 dan 11),
fungsi `__init__` dipanggil.
Di fungsi inilah kita bisa menginisialisasi (memberikan nilai baru)
terhadap data yang baru kita buat.
Fungsi `__init__` disebut sebagai **fungsi konstruktor**.


![Definisi Class](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/def_class.png)

![Konstruktor](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/konstruktor.png)

Selain fungsi konstruktor, ke dalam class juga dapat kita tambahkan fungsi-fungsi lain.
Misalnya, kita ingin menghitung tahun kelahiran seseorang dari umurnya.
Untuk itu kita buat fungsi `hitung_tahun_lahir` di dalam kelas `mahasiswa`.
Untuk menghitung tahun lahir, kita perlu memasukkan data tahun sekarang ke dalam fungsi.

```py linenums="1"
class mahasiswa:
    def __init__(self, nama, nim, umur, gender, alamat):
        self.nama = nama
        self.nim = nim
        self.umur = umur
        self.gender = gender
        self.alamat = alamat

    def hitung_tahun_lahir(self, tahun_sekarang):
        tahun_lahir = tahun_sekarang - self.umur
        return tahun_lahir

mhs1 = mahasiswa("Budi", 123, 19, 'L', 'Bandung')
lahir = mhs1.hitung_tahun_lahir(2026)

print("tahun lahir", mhs1.nama, "adalah", lahir)
```

!!! Catatan
    Apa fungsi parameter `self` baik dalam fungsi `_init__` ataupun fungsi `hitung_tahun_lahir`?
    Perhatikan bahwa definisi `class`, berlaku seperti template.
    Kode dalam template, hanya disimpan di satu tempat.
    Ketika kita punya dua variabel dengan tipe sama, yaitu `mhs1` dan `mhs2`,
    bagaimana komputer tahu bahwa ketika kita memanggil fungsi `hitung_tahun_lahir`,
    itu kita sedang menghitung tahun lahir Budi dam bukan Wati?

    Jawabannya adalah karena parameter `self`.

    Saat memanggil `mhs1.hitung_tahun_lahir(self, 2026)`, Python mengubahnya menjadi:
    `Mahasiswa.hitung_tahun_lahir(mhs1, 2026)`

    Artinya, `self` merujuk ke objek real (bukan template) dari kelas `mahasiswa`.
    
    

**Coba**

Misalkan kita akan membuat game pertarungan antara jago bela diri.
Pertama, kita bisa membuat tipe data baru berupa petarung.
Mari kita namakan tipe data ini `Petarung`.
Apa sajakah yang dimiliki oleh seorang petarung?

```py linenums="1"
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

```
Naruto
Kesehatan = 100
Kekuatan = 98
Kecerdasan = 94
Kelincahan = 51
Senjata = 45
```

Mari sekarang kita bikin Sasuke.

```py linenums="1" title="pertarungan.py"
# saya pindahkan class Petarung ke file petarung.py
# (hapus pula baris 20 dan 21)
# lalu saya import

from petarung import Petarung

naruto = Petarung("Naruto")
sasuke = Petarung("Sasuke")

naruto.print_data()
print("----------------------")
sasuke.print_data()
```

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

Sekarang, mari kita tandingkan Naruto dan Sasuke.
Untuk itu, kita buat tipe data `Tanding`.

```py linenums="1" title="tanding.py"
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

```py linenums="1" title="pertarungan.py"
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

## **Tugas Praktikum**

1. Lengkapi `tanding.py` dengan bagian perhitungan
    untuk **kecerdasan**, **kelincahan**, dan juga **senjata**.

2. Lengkapi class `Petarung` dengan data **skor**.

3. Buatlah program pertarungan ini agar dilakukan berulang-ulang
    sampai pemain memutuskan untuk keluar program. Tambahkan menu seperti berikut:
    - Lihat petarung
    - Edit petarung
    - Tambah petarung
    - Hapus petarung
    - Bertanding
    - Keluar

    Untuk menu **Lihat petarung**, tampilkan datanya juga.
    Selain itu, simpan data setiap petarung dalam file (Gunakan JSON).
    Untuk menu **Bertanding**, ketika dipilih menu dilanjutkan dengan pemilihan 2 nama petarung.

4. Tambahkan data jumlah **kalah**, **menang**, dan **seri** dalam class `Petarung`.

5. Buatlah agar **kesehatan** setiap petarung yang kalah dikurangi **5 poin**.

6. Buatlah agar setiap kali seorang petarung menang, **kekuatannya bertambah** secara acak antara **1–5 poin**.

7. Buatlah satu fungsi di class `Petarung` untuk **men-generate ulang** nilai-nilai kekuatan, kecerdasan, kelincahan, dan senjatanya namun dengan biaya **kesehatannya dikurangi 10 poin**.
