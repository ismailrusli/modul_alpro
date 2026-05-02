# Modul 6: File 

<!-- ![Status](https://img.shields.io/badge/Status-On_Progress-yellow?style=flat-square) -->
![Status](https://img.shields.io/badge/Status-Finish-brightgreen?style=flat-square)

## **Capaian Pembelajaran Mata Kuliah**

Mampu menggunakan elemen-elemen pemrograman, yaitu fungsi, I/O, dan tipe data buatan sendiri untuk membuat program sederhana berbasis teks.

---

## **Materi**

Sebuah program, kadang butuh menyimpan data ke dalam file atau membaca dari file. File memungkinkan data tetap tersimpan meskipun program sudah selesai dijalankan.
Saat berurusan dengan file, biasanya kita melakukan hal-hal berikut.

1. cek keberadaan file,
1. membuat/menghapus file,
1. membuka/menutup file,
1. membaca isi file, dan
1. menulis data ke file.

### **Cek Keberadaan File**

Untuk menangani file, kita harus memastikan file tersebut ada.
Misalkan kita ingin cek keberadaan file dengan nama `file.txt`.
Untuk itu, kita tuliskan kode berikut.

```python linenums="1"

import os

if os.path.exists("file.txt"):
    print("file.txt ada")
else:
    print("file.txt tidak ada")
```

**Penjelasan:**

1. `import os` artinya kita memanggil modul `os` (operating system).
2. `os.path.exists("file.txt")` memeriksa apakah file dengan nama tersebut ada di direktori saat ini.
    Di sini kita menggunakan fungsi `exists` yang disediakan modul `os`.

    !!! Catatan
        `os` adalah nama modul, `path` adalah nama submodul, dan `exists` adalah nama fungsi yang ada di dalam submodul `path`.


### **Membuat File**

Ada beberapa cara membuat file di Python.

**Menggunakan mode create (x)**

```py linenums="1"
import os

print("Sebelum membuat file:")
if os.path.exists("file.txt"):
    print("file.txt ada")
else:
    print("file.txt tidak ada")

try:
    f = open("file.txt", "x")
    f.close()
    print("File berhasil dibuat dengan mode 'x'")
except FileExistsError:
    print("File sudah ada, tidak bisa membuat dengan mode 'x'")
```

!!! Catatan
    block `try` dan `except` digunakan untuk menghindari program berhenti (crash)
    karena error yang diakibatkan file sudah ada saat kita memerintahkan
    pembuatan file menggunakan mode `x`.

!!! Catatan
    Setelah selesai menggunakan file (open, write, atau read), tutuplah file
    tersebut dengan memanggil fungsi `close` agar file tidak korup jika program
    tiba-tiba berhenti. Selain itu, menutup file berarti mengosongkan memori
    agar dapat digunakan untuk yang lain.

**Menggunakan mode write (w)**

```py linenums="1"
import os

print("Sebelum membuat file:")
if os.path.exists("file.txt"):
    print("file.txt ada")
else:
    print("file.txt tidak ada")

f = open("file_baru.txt", "w")
f.write("Ini adalah file baru")
f.close()
print("File berhasil dibuat dengan mode 'w'")
```

Sebagai rangkuman, tabel berikut menunjukkan mode dalam pembuatan
file dan efeknya.

| Mode | Arti | File Exist? | Output |
| --- | --- | --- | --- |
| `x` | create | Ya | Error (tangani dengan blok `try-except` ) |  
| `x` | create | Tidak | File dibuat |  
| `w` | write | Ya | File dibuka untuk ditulis |  
| `w` | write | Tidak | File dibuat |  

### **Menghapus File**

Untuk menghapus sebuah file, perhatikan kode berikut.

```python linenums="1"
import os

if os.path.exists("file.txt"):
    print("file.txt ada dan akan dihapus")
    os.remove("file.txt")
    print("File berhasil dihapus")
else:
    print("file.txt tidak ada")
```

### **Membuka File**

Untuk membuka file, gunakan fungsi `open` sesuai
dengan tujuan dibukanya file tersebut.
Jika tujuannya untuk

- dibaca, gunakan `open(namafile, 'r')`
- ditulis, gunakan `open(namafile, 'w')`
- ditambah, gunakan `open(namafile, 'a')`
- dibuat baru jika tidak ada, gunakan `open(namafile, 'x')`

```py linenums="1"
namafile = "file.txt"

# f = open(namafile, 'r')  # Membaca file
# f = open(namafile, 'w')  # Menulis (menimpa)
# f = open(namafile, 'a')  # Menambah (append)
# f = open(namafile, 'x')  # Membuat file baru
```

### **Membaca File**

Misalkan kita memiliki file teks dengan nama `file.txt`.
Isinya adalah sebagai berikut.

``` title="file.txt" linenums="1"
budi
wati
ina
hamid
```
Bagaimana cara program kita membaca nama-nama itu?
Perhatikan kode berikut.

```py linenums="1"
namafile = "file.txt"

f = open(namafile, 'r')  # Mode READ
isi = f.read()
print(isi)
f.close()
```

### **Menulis File**

Masih dengan `file.txt` yang sama.

``` title="file.txt" linenums="1"
budi
wati
ina
hamid
```
Bagaimana cara kita menambahkan nama ke dalam
file tersebut? Perhatikan kode berikut.

```py linenums="1"
namafile = "file.txt"

f = open(namafile, 'a')  # Mode APPEND
f.write("dodo")
f.close()
```

**Coba**

1. Misalkan kita punya file dengan nama `file.txt`.

    ``` title="file.txt" linenums="1"
    budi
    wati
    ina
    hamid
    ```

    Kita lalu menuliskan nama baru ke dalam file
    menggunakan mode `w` seperti berikut.

    ```py linenums="1"
    namafile = "file.txt"

    f = open(namafile, 'w')  # Mode APPEND
    f.write("dodo")
    f.close()
    ```

    Apa yang terjadi?

1. Saat membaca suatu file dengan perintah `isi = f.read()`,
    semua isinya dibaca dan disimpan ke variabel `isi`.
    Selain fungsi `read` ada juga fungsi `readline`.
    Sesuai namanya, `readline` hanya membaca satu baris
    dari isi di dalam file.

    ``` title="file.txt" linenums="1"
    budi
    wati
    ina
    hamid
    ```

    ```py linenums="1"
    namafile = "file.txt"

    f = open(namafile, 'r')
    baris = f.readline()
    print(baris)
    f.close()
    ```

    Apa outputnya?

    Kode tersebut hanya akan membaca satu baris teratas dari `file.txt`.
    Bagaimana jika kita ingin membaca semua baris dalam file tersebut?
    Untuk itu, gunakan perulangan.

    ```py linenums="1"
    namafile = "file.txt"

    f = open(namafile, 'r') 

    for baris in f:  # f adalah sebuah iterabel!!
        print(baris)
    f.close()
    ```

    Seperti apa outputnya? Apakah ada yang aneh?

    !!! Catatan
        Dalam `file.txt`, ketika kita membaca
        baris `budi`, terdapat invisible character dalam
        baris itu, yaitu `\n`.
        Jadi, setelah statement `baris = f.readline()`,
        isi dari `baris` adalah string `"budi\n"`.

    Selain `readline()` ada juga fungsi `readlines()`.
    Coba dan jelaskan beda antara keduanya.

1. Perhatikan kode berikut.
    ```py linenums="1"
    print("=== tanpa strip ===")
    f = open("file.txt", 'r')
    for baris in f:
        print(baris)
    f.close()

    print()

    print("=== dengan strip ===")
    f = open("file.txt", 'r')
    for baris in f:
        print(baris.strip())
    f.close()
    ```

    Apa fungsi `strip()`?

1. Pembukaan dan pembacaan file dalam program Python, biasanya
    dibungkus dalam blok `with`.
    Blok ini digunakan sebagai isolasi agar setelah blok
    ini selesai, file langsung ditutup. 
    Sebagai contoh:

    ```py linenums="1"
    with open("file.txt", 'r') as f:
        for baris in f:
            print(baris)
    ```

    Buatlah kode yang sama dengan tujuan menambahkan
    baris baru ke dalam file.

1. Berikut adalah `file.txt`.
    ``` title="file.txt" linenums="1"
    budi
    wati
    ina
    ```

    Tuliskan kode untuk menambah 2 nama di bawah ina,
    yaitu hamid dan santi sehingga file tersebut menjadi
    seperti berikut.

    ``` title="file.txt" linenums="1"
    budi
    wati
    ina
    hamid
    santi
    ```

### **JSON**

Menuliskan sesuatu ke dalam file dalam baris-baris seperti `file.txt` sangat mudah.
Sayangnya, saat kita baca ulang atau edit, tidak terlalu mudah.
Tentu repot menukar urutan `hamid` dan `wati`, misalnya.
Selain itu, lebih repot lagi jika data yang kita ingin simpan berbentuk data gabungan.
Misalnya, biodata (nama, umur, hobi, alamat).
Menyimpannya dalam bentuk teks polos sepertinya tidak terlalu bagus. 

Untuk itu, kita akan menggunakan format JSON (Javascript Object Notation) dalam menyimpan data ke file teks.
Contoh JSON adalah sebagai berikut.

```json linenums="1"
{
    "nama": "Andi",
    "umur": 25,
    "hobi": ["membaca", "berenang"],
    "alamat": {
        "jalan": "Jl. Merdeka No. 10",
        "kota": "Jakarta"
    }
}
```

Nanti kita akan belajar bahwa di Python, terdapat juga data yang diformat seperti JSON,
yaitu dictionary.

Untuk menggunakan JSON di Python, kita dapat menggunakan modul `json`.
Misalnya kita memiliki file teks dengan nama `data.json`.

```json title="data.json" linenums="1"
{
    "nama": "Budi",
    "umur": 30,
    "pekerjaan": "programmer"
}
```

Perhatikan kode berikut untuk melihat cara membaca
file JSON tersebut.

```py linenums="1"
import json

# Membaca file JSON
with open('data.json', 'r') as file:
    data = json.load(file)  # load = membaca JSON dari file

print(data)
print("Nama:", data['nama'])
print("Umur:", data['umur'])
print("Pekerjaan:", data['pekerjaan'])
```

Output dari program tersebut adalah sebagai berikut.

```
{'nama': 'Budi', 'umur': 30, 'pekerjaan': 'programmer'}
Nama: Budi
Umur: 30
Pekerjaan: programmer
```

Bagaimana jika kita ingin mengubah data dalam file tersebut?
Misalnya kita ingin mengubah umur menjadi 31.
Berikut caranya.

```py linenums="1"
import json

with open('data.json', 'r') as f:
    data = json.load(f) 

data['umur'] = 31

with open('data.json', 'w') as f:
    json.dump(data, f, indent=4)  # dump untuk menulis 
```

Untuk menambah data di `data.json`,
perhatikan kode berikut.

```json title="data.json" linenums="1"
{
    "nama": "Budi",
    "umur": 31,
    "pekerjaan": "programmer"
}
```


```py linenums="1"
import json

# Perhatikan tanda kurung siku. Ini adalah list.
# Kita mau mengubah data JSON kita menjadi kumpulan data nama-nama.
# [
#   {"nama": "Budi", "Umur": 31, "Pekerjaan": "programmer"},
#   {"nama": "Wati", "Umur": 28, "Pekerjaan": "guru"}
# ]

data_baru = {
    "nama": "Wati",
    "umur": 28,
    "pekerjaan": "guru"
}


with open('data.json', 'r') as f:
    data = [json.load(file)]  # kita ubah menjadi list

data.append(data_baru)  # append digunakan untuk menambah data di list

with open('data.json', 'w') as f:
    json.dump(data, f, indent=2)
```

`data.json` sekarang menjadi berisi seperti berikut.

```json title="data.json" linenums="1"
[
  {
    "nama": "Budi",
    "umur": 31,
    "pekerjaan": "programmer"
  },
  {
    "nama": "Wati",
    "umur": 28,
    "pekerjaan": "guru"
  }
]
```

**Coba**

Berikut adalah contoh program manajemen kontak menggunakan JSON.
Tulis dan jalankan kode ini dan bereksprerimenlah dengan
mengubah-ubahnya.

```python
import json
import os

KONTAK_FILE = "kontak.json"

def load_kontak():
    """Memuat data kontak dari file JSON"""
    if os.path.exists(KONTAK_FILE):
        with open(KONTAK_FILE, 'r') as file:
            return json.load(file)
    return []  # Return empty list jika file belum ada

def save_kontak(kontak_list):
    """Menyimpan data kontak ke file JSON"""
    with open(KONTAK_FILE, 'w') as file:
        json.dump(kontak_list, file, indent=4)

def tambah_kontak():
    """Menambah kontak baru"""
    kontak = load_kontak()
    
    nama = input("Nama: ")
    telepon = input("Nomor telepon: ")
    email = input("Email: ")
    
    kontak_baru = {
        "id": len(kontak) + 1,
        "nama": nama,
        "telepon": telepon,
        "email": email
    }
    
    kontak.append(kontak_baru)
    save_kontak(kontak)
    print(f"Kontak {nama} berhasil ditambahkan!")

def lihat_kontak():
    """Menampilkan semua kontak"""
    kontak = load_kontak()
    
    if not kontak:
        print("Belum ada kontak.")
        return
    
    print("\n=== DAFTAR KONTAK ===")
    for k in kontak:
        print(k['id'], ".", k['nama'])
        print("Telepon:", k['telepon'])
        print("Email:", k['email'])
        print()

def cari_kontak():
    """Mencari kontak berdasarkan nama"""
    kontak = load_kontak()
    keyword = input("Masukkan nama yang dicari: ").lower()
    
    hasil = [k for k in kontak if keyword in k['nama'].lower()]
    
    if hasil:
        print("\nDitemukan", len(hasil), "kontak:")
        for k in hasil:
            print("-", k['nama'], "(" + str(k['telepon']) + ")")
    else:
        print("Tidak ada kontak dengan nama", keyword)

def main():
    while True:
        print("\n=== MANAJEMEN KONTAK ===")
        print("1. Tambah kontak")
        print("2. Lihat semua kontak")
        print("3. Cari kontak")
        print("4. Keluar")
        
        pilihan = input("Pilih menu (1-4): ")
        
        if pilihan == '1':
            tambah_kontak()
        elif pilihan == '2':
            lihat_kontak()
        elif pilihan == '3':
            cari_kontak()
        elif pilihan == '4':
            print("Terima kasih!")
            break
        else:
            print("Pilihan tidak valid!")

if __name__ == "__main__":
    main()
```

## **Tugas Praktikum**

Buatlah program untuk **Sistem Manajemen Perpustakaan Digital**.
Tiru logika kode dari program manajemen kontak sebelumnya.

1. **Manajemen Buku**
    - Tambah, edit, hapus buku
    - Data buku: ID, Judul, Pengarang, Penerbit, Tahun, Stok, Kategori
    - Simpan dalam format JSON (`buku.json`)

2. **Manajemen Anggota**
    - Tambah, edit, hapus anggota
    - Data anggota: ID Anggota, Nama, Alamat, Telepon
    - Simpan dalam format JSON (`anggota.json`)


Contoh struktur JSON untuk buku.

```json linenums="1"
[
    {
        "B001": {
            "judul": "Python Programming",
            "pengarang": "Andi Wijaya",
            "penerbit": "Gramedia",
            "tahun": 2023,
            "stok": 5,
            "kategori": "Teknologi"
        }
    },
]
```
