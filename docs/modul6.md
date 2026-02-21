# Modul 6: File

![Status](https://img.shields.io/badge/Status-On_Progress-yellow?style=flat-square)
<!-- ![Status](https://img.shields.io/badge/Status-Finish-brightgreen?style=flat-square) -->

## 6.1 Capaian

Mampu menggunakan elemen-elemen dasar pemrograman, seperti inisialisasi variabel untuk berbagai macam tipe data, menggunakan percabangan, menggunakan pengulangan, membuat dan menggunakan fungsi, serta membuat dan menggunakan tipe data bentukan sendiri.

## 6.2 Alat dan Bahan

1. Laptop/komputer
2. Internet
3. Python 3.8+
4. Visual Studio Code (atau editor sejenis)

## 6.3 Materi

Sebuah program, kadang butuh menyimpan data dalam bentuk file. Beberapa aktivitas terkait file di antaranya adalah cek keberadaan file, membuat/menghapus file, membuka/menutup file, membaca data file, dan menulis data ke file.

---

### 6.3.1 Cek File

Untuk menangani file, tentu kita harus memastikan bahwa file tersebut ada. Kode 6.1 menunjukkan kode untuk cek keberadaan `file.txt` di folder yang sama dengan folder kode python-nya.

**Kode 6.1: Cek keberadaan file**

```python
import os

if os.path.exists("file.txt"):
    print("file.txt ada")
else:
    print("file.txt tidak ada")
```

---

### 6.3.2 Membuat/Menghapus File

Untuk membuat file, perhatikan Kode 6.2.

**Kode 6.2: buat-file.py**

```python
import os

print("sebelum perintah open")
if os.path.exists("file.txt"):
    print("file.txt ada")
else:
    print("file.txt tidak ada")

# Karakter 'x' dalam fungsi open berarti
# fungsi ini akan error jika file sudah ada.
# Supaya tidak error, gunakan 'w' (write)
f = open("file.txt", "x")

print("setelah perintah open")
if os.path.exists("file.txt"):
    print("file.txt ada")
else:
    print("file.txt tidak ada")
```

Untuk menghapus file, perhatikan Kode 6.3.

**Kode 6.3: hapus-file.py**

```python
import os

if os.path.exists("file.txt"):
    print("file.txt ada dan akan dihapus")
    os.remove("file.txt")
else:
    print("file.txt tidak ada")
```

---

### 6.3.3 Membuka/Menutup File

Untuk membuka sebuah file, kita tuliskan kode seperti yang ditampilkan di Kode 6.4.

**Kode 6.4: buka-file.py**

```python
import os

namafile = "file.txt"

if os.path.exists(namafile):
    f = open(namafile)
    print(namafile, "ada dan telah dibuka.")
else:
    print(namafile, "tidak ada")
```

Setelah suatu file dibuka, dan kita selesai bekerja dengan file tersebut (misalnya selesai menulis atau membaca file), ada baiknya kita menutup file tersebut agar dibersihkan dari memori. Cara menutup file adalah dengan fungsi `close`. Perhatikan Kode 6.5.

**Kode 6.5: tutup-file.py**

```python
import os

namafile = "file.txt"

if os.path.exists(namafile):
    f = open(namafile)
    f.close()  # menutup file
else:
    print(namafile, "tidak ada")
```

Fungsi `open` digunakan baik untuk membuka file maupun untuk membuat file. Beberapa variasinya adalah seperti yang ditunjukkan di Kode 6.6.

**Kode 6.6: Variasi penggunaan perintah open**

```python
namafile = "file.txt"

# Digunakan untuk MEMBUKA dan MENULIS "file.txt".
# Jika "file.txt" tidak ada, file akan dibuat.
# Hati-hati!!! 'w' akan menimpa isi file sebelumnya.
# Jika ingin menambahkan baris, gunakan 'a' (append)
f = open(namafile, 'w')  # write (menimpa)
f = open(namafile, 'a')  # append (menambah)

# Digunakan untuk MEMBUKA dan MEMBACA "file.txt".
# Jika "file.txt" tidak ada, error.
# Perintah berikut sama dengan open(namafile)
f = open(namafile, 'r')

# Digunakan untuk MEMBUAT "file.txt" ('x' berarti create).
# Jika "file.txt" ada, error.
f = open(namafile, 'x')
```

---

### 6.3.4 Membaca File

Setelah dibuka, kita tentu ingin membaca isi file. Misalkan saya memiliki file dengan nama `file.txt` yang isinya seperti di Kode 6.7.

**Kode 6.7: file.txt**

```
ini adalah file
file ini berisi teks
```

Cara membuka dan membaca file tersebut adalah seperti yang ditunjukkan di Kode 6.8. Hasilnya dapat dilihat di Kode 6.9.

**Kode 6.8: baca-file.py**

```python
import os

namafile = "file.txt"

if os.path.exists(namafile):
    f = open(namafile, 'r')
    text1 = f.readline()
    print(text1)
    text2 = f.readline()
    print(text2)
else:
    print(namafile, "tidak ada")
```

**Kode 6.9: Hasil dari baca-file.py**

```
ini adalah file

file ini isinya teks
```

Fungsi `readline` di Kode 6.8 membaca isi file setiap baris. Setelah dibaca, isi baris tersebut disimpan dalam variabel `text1`. Baris yang disimpan di `text1`, mengandung karakter newline (baris baru). Jika kita gunakan fungsi `print(text1)`, kita jadi memiliki 2 karakter newline, yaitu dari isi file yang dibaca dan dari fungsi `print`. Itulah kenapa hasil di Kode 6.9 terdapat baris kosong. Untuk menghindarinya, kita ingin menghilangkan karakter newline di setiap baris yang kita baca dari file. Caranya adalah dengan menggunakan fungsi `strip()`. Perhatikan Kode 6.10.

**Kode 6.10: baca-file-strip.py**

```python
import os

namafile = "file.txt"

if os.path.exists(namafile):
    f = open(namafile, 'r')
    text1 = f.readline().strip()
    print(text1)
    text2 = f.readline().strip()
    print(text2)
else:
    print(namafile, "tidak ada")
```

Kode 6.10 tidaklah efisien karena kita terus-terusan menuliskan fungsi `readline` sebanyak baris yang ingin kita baca. Bagaimana jika kita ingin membaca semua baris dalam file tapi kita tidak tahu berapa baris ada di dalam file tersebut? Untuk itu, kita sebaiknya menggunakan perulangan seperti di Kode 6.11.

**Kode 6.11: baca-file-loop.py**

```python
import os

namafile = "file.txt"

if os.path.exists(namafile):
    f = open(namafile, 'r')

    for text in f:
        print(text.strip())
else:
    print(namafile, "tidak ada")
```

Jika kita ingin membagi setiap baris yang dibaca dari suatu file ke dalam kata-kata, kita bisa gunakan perintah `split`. Perhatikan Kode 6.12 dan hasilnya di Kode 6.13.

**Kode 6.12: split-baris.py**

```python
import os

namafile = "file.txt"

if os.path.exists(namafile):
    f = open(namafile, 'r')
    baris = f.readline().strip()
    kata = baris.split()
    print(kata)
else:
    print(namafile, "tidak ada")
```

**Kode 6.13: Hasil dari split-baris.py**

```
['ini', 'adalah', 'file']
```

---

### 6.3.5 Menulis File

Untuk menulis teks ke file, kita bisa menggunakan fungsi `open` dengan parameter `w` atau `a`. Gunakan `w` jika ingin menimpa isi file dan gunakan `a` jika ingin menambahkan baris ke file. Perhatikan Kode 6.14.

**Kode 6.14: tulis-file.py**

```python
import os

namafile = "file2.txt"

if os.path.exists(namafile):
    f = open(namafile, 'r')
    print("sebelum ditambahkan")
    print("----------------------------")
    for x in f:
        print(x.strip())
    f.close()

    f = open(namafile, 'a')
    f.write("ini adalah baris tambahan\n")
    f.close()

    print("")
    print("setelah ditambahkan")
    print("----------------------------")
    f = open(namafile, 'r')
    for x in f:
        print(x.strip())
    f.close()
else:
    print(namafile, "tidak ada")
```
