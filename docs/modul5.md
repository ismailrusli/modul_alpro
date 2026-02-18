# Modul 5: Fungsi

## 5.1 Capaian

Mampu menggunakan elemen-elemen dasar pemrograman, seperti inisialisasi variabel untuk berbagai macam tipe data, menggunakan percabangan, menggunakan pengulangan, membuat dan menggunakan fungsi, serta membuat dan menggunakan tipe data bentukan sendiri.

---

## 5.2 Alat dan Bahan

1. Laptop/komputer
2. Internet
3. Python 3.8+
4. Visual Studio Code (atau editor sejenis)

---

## 5.3 Materi

Perhatikan Kode 5.1 berikut. Kode 5.1 adalah program yang mencetak 10 baris keluaran. Setiap baris mencetak karakter bintang sebanyak posisi barisnya. Jadi, misalnya baris ke-1, akan mencetak karakter `*`. Baris ke-2 mencetak `**`. Baris ke-3, `***`, dan seterusnya.

**Kode 5.1: Print 10 baris bintang menggunakan loop**

```python
for i in range(1, 11):
    x = ""
    for j in range(i):
        x = x + "*"
    print(x)
```

Baris 2, 3, dan 4 dalam kode tersebut berfungsi untuk membuat string dengan karakter bintang sebanyak posisi baris dan menyimpannya di `x`. Kita bisa memisahkan 3 baris kode ini dan memberi nama sesuai tugasnya, yaitu membuat bintang sebanyak yang diinginkan. Perhatikan Kode 5.2.

**Kode 5.2: Fungsi untuk membuat bintang**

```python
def buat_bintang(n):
    x = ""
    for i in range(n):
        x = x + "*"
    return x
```

Di Kode 5.2, baris 2, 3, dan 4 dari Kode 5.1 dimasukkan ke dalam suatu fungsi yang namanya `buat_bintang`. Fungsi dapat dianggap sebagai sebuah mesin yang menerima input, memprosesnya, dan mengeluarkan output (hasilnya). Dalam fungsi `buat_bintang`, inputnya adalah variabel `n`. Sementara, outputnya ada di baris 5, yaitu `x`. Variabel `x` berisi string bintang sebanyak `n`. Kata kunci `return` menunjukkan data (dalam hal ini `x`) yang dihasilkan fungsi `buat_bintang`.

> **Gambar 5.1:** Fungsi `buat_bintang` menerima `n` dan mengeluarkan `x`
>
> `n` → [ loop untuk buat bintang sebanyak n, lalu simpan di x ] → `x`

Dengan fungsi `buat_bintang` kita bisa membuat program di Kode 5.1 menjadi tampak lebih sederhana dan rapi serta bersih. Perhatikan Kode 5.3 terutama baris 7-9.

**Kode 5.3: Kode 5.1 menjadi lebih mudah dibaca dengan fungsi**

```python
def buat_bintang(n):
    x = ""
    for i in range(n):
        x = x + "*"
    return x

for i in range(1, 11):
    bintang = buat_bintang(i)
    print(bintang)
```

---

**Kode 5.4: Kerjakan**

```python
def buat_bintang(n):
    x = ""
    for i in range(n):
        x = x + "*"
    return x

# printlah bintang sebanyak 5 bintang
# dengan menggunakan fungsi buat_bintang
```

---

Kita bisa menyimpan fungsi `buat_bintang` di file terpisah sehingga fungsi ini dapat digunakan oleh kode lain juga. Jika demikian, fungsi `buat_bintang` harus diimpor terlebih dahulu. Misalkan kita simpan fungsi `buat_bintang` di file yang namanya `bintang.py`. Perhatikan Kode 5.5.

**Kode 5.5: Menggunakan `buat_bintang` dari file `bintang.py`**

```python
from bintang import buat_bintang

for i in range(1, 11):
    bintang = buat_bintang(i)
    print(bintang)
```

Baris 1 Kode 5.5 menyatakan bahwa kita mengimport dari file `bintang.py` fungsi `buat_bintang`.

---

**Kode 5.6: Kerjakan — Buat program yang hasilnya seperti berikut:**

```
*
**
***
****
***
**
*
```

---

Kita dapat menambah fitur ke fungsi `buat_bintang`, yaitu dengan menentukan karakter yang akan dicetak. Dengan demikian, kita ubah nama fungsinya menjadi `buat_n_karakter`. Perhatikan Kode 5.7.

**Kode 5.7: Fungsi `buat_n_karakter`**

```python
def buat_n_karakter(karakter, n):
    x = ""
    for i in range(n):
        x = x + karakter
    return x

print(buat_n_karakter("*", 2))
print(buat_n_karakter("+", 4))
print(buat_n_karakter("%", 6))
```

---

**Kode 5.8: Kerjakan**

```python
# Buat fungsi untuk menghitung kuadrat dari sebuah angka
def kuadrat(angka):
    pass  # Ganti dengan kode

a = kuadrat(4)
print(a)  # hasilnya 16

b = kuadrat(5)
print(b)  # hasilnya 25
```

---

### 5.3.1 Kerjakan

**1.** Buatlah fungsi yang menerima karakter dan jumlah karakter serta mengembalikan string yang berisi rentetan karakter sebanyak jumlah karakter yang dimasukkan.

**Kode 5.9: Kerangka kode untuk soal no. 1**

```python
def nkarakter(karakter, jumlah):
    # tulis kode di sini

# contoh penggunaan
x = nkarakter("#", 5)

# perintah ini mencetak ##### ke layar
print(x)
```

---

**2.** Buatlah fungsi yang menerima string lalu mengembalikan jumlah karakter dalam string tersebut.

**Kode 5.10: Kerangka kode untuk soal no. 2**

```python
def jumlah_karakter(input_string):
    n_karakter = 0
    # tulis kode di sini

    return n_karakter

# contoh penggunaan
x = jumlah_karakter("multimedia")

# perintah ini harus mencetak angka 10 ke layar
print(x)
```

---

**3.** Sebuah robot berada di koordinat (0,0). Buatlah 4 fungsi, yaitu `maju()` untuk menambah x satu satuan, `mundur()` untuk mengurangi x satu satuan, `belok_kanan()` untuk menambah y satu satuan, dan `belok_kiri()` untuk mengurangi y satu satuan. Perhatikan kerangka program di Kode 5.11.

**Kode 5.11: Kerangka kode untuk soal no. 3**

```python
def maju(posisi):
    # kode di sini

def mundur(posisi):
    # kode di sini

def belok_kanan(posisi):
    # kode di sini

def belok_kiri(posisi):
    # kode di sini

selesai = False
posisi_robot = (0, 0)  # tuple
while selesai == False:
    print("---------------")
    print("Pilih perintah untuk robot.")
    print("1. maju")
    print("2. mundur")
    print("3. belok kanan")
    print("4. belok kiri")
    print("5. selesai")
    print("---------------")
    perintah = input("Masukkan perintah")
    perintah = int(perintah)

    if perintah == 1:
        posisi_robot = maju(posisi_robot)
        print(posisi_robot)
    elif perintah == 2:
        posisi_robot = mundur(posisi_robot)
        print(posisi_robot)
    elif perintah == 3:
        posisi_robot = belok_kanan(posisi_robot)
        print(posisi_robot)
    elif perintah == 4:
        posisi_robot = belok_kanan(posisi_robot)
        print(posisi_robot)
    elif perintah == 5:
        selesai = True
        print(posisi_robot)
```

---

**4.** Ubahlah Kode 5.11. Jadikan 4 fungsi `maju()`, `mundur()`, `belok_kanan()`, dan `belok_kiri()` ke dalam satu fungsi. Akan tetapi, 1 fungsi ini menerima masukan tambahan berupa petunjuk apakah robot harus maju, mundur, belok kanan, atau belok kiri.

---

**5.** Fungsi rekursif adalah fungsi yang memanggil dirinya sendiri. Contohnya adalah fungsi di Kode 5.12. Menurut anda, apa yang akan terjadi jika Kode 5.12 dijalankan?

**Kode 5.12: Fungsi rekursif**

```python
def rekursif():
    print("x")
    rekursif()

rekursif()
```

---

**6.** Buat program untuk menyimpan data nama dan nilai. Simpan data nama dan nilai tersebut di dalam file.

---

**7.** Buat program kalkulator dengan menu seperti berikut:

- (a) Tambah
- (b) Kurang
- (c) Kali
- (d) Bagi
- (e) Keluar

---

**8.** Buat program tebak kata. Baca daftar kata yang ada di dalam file (buat dulu file-nya, misal 20 kata. Tulis setiap kata per baris dalam file tersebut). Lalu baca filenya. Simpan kata-kata tersebut ke dalam list. Lalu buat komputer untuk memilih secara acak satu kata. User hanya dapat menebak huruf-huruf yang ada dalam kata tersebut 10 kali. Setiap kali satu huruf berhasil ditebak, tampilkan kata dengan huruf-huruf yang sudah ditebak dalam posisi yang benar.
