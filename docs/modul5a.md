# **Modul 5: Fungsi**

![Status](https://img.shields.io/badge/Status-On_Progress-yellow?style=flat-square)
<!-- ![Status](https://img.shields.io/badge/Status-Finish-brightgreen?style=flat-square) -->

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

Perhatikan gambar berikut untuk melihat contoh input dan output untuk setiap fungsi tersebut. Untuk saat ini, istilah seperti `side effect` dan `standard input (stdin)` boleh diabaikan.


![Anatomi fungsi dalam Python](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/anatomi_fungsi.png)

Kita memasukkan nilai (*value*) sebagai input ke dalam fungsi dan sebaliknya
juga mendapatkan nilai (*value*) sebagai output.

Input yang masuk ke dalam sebuah fungsi adalah nol, satu, atau lebih dari satu nilai.
Output yang keluar dari sebuah fungsi juga nol, satu, atau lebih dari satu nilai.

Perhatikan Kode 5.1 berikut. Kode 5.1 adalah program yang mencetak 10 baris keluaran.
Setiap baris mencetak karakter bintang sebanyak posisi barisnya.
Jadi, baris ke-1 mencetak `*`, baris ke-2 mencetak `**`, baris ke-3 mencetak `***`, dan seterusnya.

**Kode 5.1: Mencetak 10 baris bintang menggunakan loop**

```python linenums="1"
for i in range(1, 11):
    x = ""
    for j in range(i):
        x = x + "*"
    print(x)
```

Baris 2, 3, dan 4 dalam kode tersebut berfungsi untuk membuat string dengan karakter bintang
sebanyak posisi baris, lalu menyimpannya di variabel `x`.
Kita bisa memisahkan ketiga baris kode ini, memberinya nama sesuai tugasnya,
dan membungkusnya menjadi sebuah fungsi. Perhatikan Kode 5.2.

**Kode 5.2: Mendefinisikan fungsi `buat_bintang`**

```python linenums="1"
def buat_bintang(n):
    x = ""
    for i in range(n):
        x = x + "*"
    return x
```

Fungsi dapat dianggap sebagai sebuah mesin yang menerima input, memprosesnya,
dan mengeluarkan output. Dalam fungsi `buat_bintang`:

- Kata kunci `def` menandai awal definisi fungsi.
- `buat_bintang` adalah nama fungsi.
- `n` dalam tanda kurung adalah **parameter**, yaitu variabel yang menampung input.
- Kata kunci `return` pada baris 5 menandai nilai yang dikeluarkan fungsi sebagai output.

Dengan fungsi `buat_bintang`, kode pada Kode 5.1 menjadi lebih sederhana, rapi, dan mudah dibaca.
Perhatikan Kode 5.3, terutama baris 7–9.

**Kode 5.3: Kode 5.1 yang lebih mudah dibaca dengan bantuan fungsi**

```python linenums="1"
def buat_bintang(n):
    x = ""
    for i in range(n):
        x = x + "*"
    return x

for i in range(1, 11):
    bintang = buat_bintang(i)
    print(bintang)
```

!!! Catatan
    Fungsi harus **didefinisikan** terlebih dahulu sebelum **dipanggil**.
    Definisi fungsi ditulis dengan kata kunci `def`.
    Pemanggilan fungsi dilakukan dengan menuliskan nama fungsi diikuti tanda kurung berisi argumen.

---

**Coba**

1. Jalankan Kode 5.3 dan amati outputnya.

1. Lengkapi kode berikut sehingga program mencetak 5 bintang ke layar
   dengan memanfaatkan fungsi `buat_bintang`.

    **Kode 5.4: Lengkapi kode ini**

    ```python linenums="1"
    def buat_bintang(n):
        x = ""
        for i in range(n):
            x = x + "*"
        return x

    # printlah bintang sebanyak 5 bintang
    # dengan menggunakan fungsi buat_bintang
    ```

1. Apa yang terjadi jika baris `return x` dihapus dari Kode 5.2? Coba jalankan dan amati.

    !!! Catatan
        Fungsi tanpa `return` akan mengembalikan nilai `None`.
        `None` adalah nilai khusus di Python yang berarti "tidak ada nilai".

---

### **Mengimpor Fungsi dari File Lain**

Kita bisa menyimpan fungsi di file terpisah sehingga fungsi tersebut dapat digunakan
oleh program lain. Misalkan kita simpan fungsi `buat_bintang` di file bernama `bintang.py`.
Untuk menggunakannya dari file lain, fungsi tersebut harus diimpor terlebih dahulu.
Perhatikan Kode 5.5.

**Kode 5.5: Menggunakan `buat_bintang` dari file `bintang.py`**

```python linenums="1"
from bintang import buat_bintang

for i in range(1, 11):
    bintang = buat_bintang(i)
    print(bintang)
```

Baris 1 menyatakan bahwa kita mengimpor fungsi `buat_bintang` dari file `bintang.py`.
Setelah diimpor, fungsi `buat_bintang` dapat digunakan seperti biasa.

!!! Catatan
    Sintaks untuk mengimpor fungsi dari sebuah file adalah:
    ```
    from <nama_file_tanpa_ekstensi> import <nama_fungsi>
    ```
    File yang diimpor harus berada di direktori yang sama dengan file yang mengimpor.

---

**Coba**

1. Buat file `bintang.py` berisi fungsi `buat_bintang` dari Kode 5.2.
   Lalu buat file kedua dan tulis Kode 5.5 di dalamnya. Jalankan file kedua tersebut.

1. Lengkapi program berikut sehingga outputnya seperti di bawah ini.
   Gunakan fungsi `buat_bintang` yang diimpor dari `bintang.py`.

    **Kode 5.6: Lengkapi kode ini**

    ```python linenums="1"
    from bintang import buat_bintang

    # tulis kode di sini
    ```

    Output yang diharapkan:
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

### **Fungsi dengan Banyak Parameter**

Kita dapat menambah fitur pada fungsi `buat_bintang` dengan membiarkan pemanggil
memilih karakter yang akan dicetak. Dengan demikian, nama fungsinya kita ubah menjadi
`buat_n_karakter`. Perhatikan Kode 5.7.

**Kode 5.7: Fungsi `buat_n_karakter` dengan dua parameter**

```python linenums="1"
def buat_n_karakter(karakter, n):
    x = ""
    for i in range(n):
        x = x + karakter
    return x

print(buat_n_karakter("*", 2))
print(buat_n_karakter("+", 4))
print(buat_n_karakter("%", 6))
```

Output dari Kode 5.7 adalah:
```
**
++++
%%%%%%
```

!!! Catatan
    **Argumen** adalah nilai yang kita masukkan saat **memanggil** fungsi.
    **Parameter** adalah variabel yang menampung argumen di dalam **definisi** fungsi.
    Pada Kode 5.7, `"*"` dan `2` adalah argumen, sedangkan `karakter` dan `n` adalah parameter.
    Urutan argumen saat memanggil fungsi harus sesuai dengan urutan parameter saat mendefinisikannya.

---

**Coba**

1. Jalankan Kode 5.7 dan amati outputnya.

1. Lengkapi kode berikut sehingga fungsi `kuadrat` mengembalikan nilai kuadrat dari argumennya.

    **Kode 5.8: Lengkapi fungsi `kuadrat`**

    ```python linenums="1"
    def kuadrat(angka):
        pass  # ganti dengan kode

    a = kuadrat(4)
    print(a)  # hasilnya 16

    b = kuadrat(5)
    print(b)  # hasilnya 25
    ```

1. Buat fungsi `luas_persegi_panjang(panjang, lebar)` yang mengembalikan luas persegi panjang.
   Panggil fungsi tersebut dengan beberapa nilai berbeda dan cetak hasilnya.

---

## **Tugas Praktikum**

1. Buatlah fungsi yang menerima karakter dan jumlah karakter,
   lalu mengembalikan string yang berisi rentetan karakter sebanyak jumlah yang dimasukkan.

    **Kode 5.9: Kerangka kode untuk soal no. 1**

    ```python linenums="1"
    def nkarakter(karakter, jumlah):
        # tulis kode di sini
        pass

    # contoh penggunaan
    x = nkarakter("#", 5)

    # perintah ini mencetak ##### ke layar
    print(x)
    ```

1. Buatlah fungsi yang menerima sebuah string lalu mengembalikan jumlah karakter dalam string tersebut.
   **Jangan** gunakan fungsi bawaan `len()`.

    **Kode 5.10: Kerangka kode untuk soal no. 2**

    ```python linenums="1"
    def jumlah_karakter(input_string):
        n_karakter = 0
        # tulis kode di sini

        return n_karakter

    # contoh penggunaan
    x = jumlah_karakter("multimedia")

    # perintah ini harus mencetak angka 10 ke layar
    print(x)
    ```

1. Sebuah robot berada di koordinat (0, 0). Buatlah 4 fungsi:
   `maju()` untuk menambah x satu satuan, `mundur()` untuk mengurangi x satu satuan,
   `belok_kanan()` untuk menambah y satu satuan, dan `belok_kiri()` untuk mengurangi y satu satuan.
   Gunakan kerangka program berikut.

    **Kode 5.11: Kerangka kode untuk soal no. 3**

    ```python linenums="1"
    def maju(posisi):
        # kode di sini
        pass

    def mundur(posisi):
        # kode di sini
        pass

    def belok_kanan(posisi):
        # kode di sini
        pass

    def belok_kiri(posisi):
        # kode di sini
        pass

    selesai = False
    posisi_robot = (0, 0)

    while selesai == False:
        print("---------------")
        print("Pilih perintah untuk robot.")
        print("1. maju")
        print("2. mundur")
        print("3. belok kanan")
        print("4. belok kiri")
        print("5. selesai")
        print("---------------")
        perintah = int(input("Masukkan perintah: "))

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
            posisi_robot = belok_kiri(posisi_robot)
            print(posisi_robot)
        elif perintah == 5:
            selesai = True
            print(posisi_robot)
    ```

1. Ubahlah Kode 5.11. Jadikan keempat fungsi menjadi **satu fungsi** bernama `gerak_robot(posisi, arah)`
   yang menerima posisi robot dan arah gerak sebagai argumen.

1. Fungsi rekursif adalah fungsi yang memanggil dirinya sendiri.
   Perhatikan Kode 5.12. Menurut kamu, apa yang akan terjadi jika kode ini dijalankan?
   Coba jalankan dan amati.

    **Kode 5.12: Fungsi rekursif**

    ```python linenums="1"
    def rekursif():
        print("x")
        rekursif()

    rekursif()
    ```

    !!! Catatan
        Python membatasi kedalaman rekursi untuk mencegah program menghabiskan memori.
        Saat batas tersebut tercapai, Python akan mengeluarkan error `RecursionError`.

1. Buat program untuk menyimpan data nama dan nilai mahasiswa.
   Simpan data tersebut ke dalam sebuah file teks, dengan setiap baris berisi satu data
   dalam format `nama,nilai`.

1. Buat program kalkulator dengan menu sebagai berikut.
   Setiap operasi dibuat sebagai fungsi tersendiri.

    ```
    (a) Tambah
    (b) Kurang
    (c) Kali
    (d) Bagi
    (e) Keluar
    ```

1. Buat program tebak kata dengan ketentuan berikut.
    - Buat file teks berisi minimal 20 kata (satu kata per baris).
    - Baca file tersebut dan simpan kata-katanya ke dalam sebuah list.
    - Komputer memilih satu kata secara acak dari list.
    - User menebak huruf-huruf dalam kata tersebut, maksimal 10 kali tebakan.
    - Setiap kali huruf berhasil ditebak, tampilkan kata dengan huruf-huruf
      yang sudah ditebak di posisi yang benar (huruf yang belum ditebak diganti `_`).
