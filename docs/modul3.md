# Modul 3: Input dan Percabangan

<!-- ![Status](https://img.shields.io/badge/Status-On_Progress-yellow?style=flat-square) -->
![Status](https://img.shields.io/badge/Status-Finish-brightgreen?style=flat-square)

## **Capaian Pembelajaran Mata Kuliah**

Mampu menggunakan elemen-elemen pemrograman, yaitu variabel,
percabangan, dan pengulangan untuk membuat algoritma sederhana.

---

## **Materi**
### **input**
Sejauh ini kita sudah mengenal tiga fungsi.
yaitu, `print`, `type`, dan `round`.
Sekarang, kita belajar satu fungsi lagi, yaitu `input`.
Jika fungsi `print` mengirimkan data ke terminal,
`input` menerima data dari user lewat terminal.

<br> <br>
![If blok ](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/input-print.png)
<br> <br>



**Coba**

1. Ketikkan program berikut lalu jalankan. Saat dijalankan, apa
yang terjadi?
```python
input() 
```

    !!! Catatan
        Setelah program dijalankan, program akan berhenti untuk menunggu
        sesuatu diinputkan user. Setelah diinputkan, tekan Enter untuk
        mengirimkan sesuatu yang diinputkan tersebut ke program.

1. Fungsi `input` dapat menerima 1 argumen. Ketikkan program berikut lalu jalankan.
Apa yang terjadi?
```python
input("Siapa nama kamu?") 
```

1. Apa beda kode berikut dengan kode sebelumnya?
```python
input("Siapa nama kamu? ") 
```

1. Agar data yang diketikkan user tidak hilang, 
    harus disimpan di sebuah  variabel.
```python
nama = input("Siapa nama kamu? ") 
print(nama)
```

    !!! Catatan
        Setelah user memasukkan nama dan menekan Enter, program
        menerima nama tersebut dan dikonversi menjadi sebuah string.

    !!! Catatan
        Potongan kode berikut, `input("Siapa nama kamu? ")`, adalah sebuah
        ekspresi. Dengan demikian, baris pertama valid karena mengikuti sintaks
        assignment, yaitu `<variabel> = <ekspresi>`.
        Ekspresi tersebut dapat disederhanakan menjadi sebuah value.
        Apa valuenya? String yang diketikkan user.

    !!! Cek
        Cara menulis (sintaks) fungsi `print` dengan satu argumen adalah `print(<ekspresi>)`.
        Oleh karena `input("Siapa nama kamu? ")` adalah suatu ekspresi, berarti kode berikut
        valid. Coba cek!
        ```python
        print(input("Siapa nama kamu?"))
        ```

1. Coba jalankan kode berikut. Apa yang terjadi?
```python
nama = input("Siapa nama kamu? ")
print("Halo", nama, "Senang bertemu dengan kamu!")
```

1. Coba jalankan kode berikut. Apa yang terjadi?
```python
angka1 = input("Masukkan angka ke-1: ")
angka2 = input("Masukkan angka ke-2: ")
print("Jumlah", angka1, "dan", angka2, "adalah", angka1 + angka2)
```

    !!! Catatan
        Ekspresi `input("Masukkan angka ke-1: ")` selalu disederhanakan menjadi sebuah string.
        Jadi, setelah user mengetikkan angka 2, ekspresi tersebut berubah
        menjadi nilai "2" (string) bukan 2 (integer).  
        Dengan demikian, ketika dijumlahkan, terjadi penjumlahan string.
        Untuk mengubah input user menjadi integer, gunakan fungsi typecasting `int()`.

1. Coba jalankan kode berikut. Apa yang terjadi?
```python
angka1 = input("Masukkan angka ke-1: ")
angka1 = int(angka1)

angka2 = input("Masukkan angka ke-2: ")
angka2 = int(angka2)

print("Jumlah", angka1, "dan", angka2, "adalah", angka1 + angka2)
```

    !!! Cek
        Sintaks untuk fungsi `int()` adalah `int(<ekspresi>)`.
        Oleh karena `input("Masukkan angka ke-1: ")` adalah ekspresi, kode berikut valid.
        Coba cek!
        ```python
        angka1 = int(input("Masukkan angka ke-1: "))
        ```

1. Apa bedanya program penjumlahan angka sebelumnya, dengan program berikut?
```python
angka1 = input("Masukkan angka ke-1: ")
angka2 = input("Masukkan angka ke-2: ")

angka1 = int(angka1)
angka2 = int(angka2)

print("Jumlah", angka1, "dan", angka2, "adalah", angka1 + angka2)
```

    !!! Catatan
        Ingat, program adalah urutan perintah-perintah.
        Urutan perintah penting ketika urutan itu mengandung hubungan logis.
        Perintah dapat ditukar-tukar urutannya selama hubungan logisnya tetap sama.

1. Coba program berikut. Isi panjang dengan 2.5 dan lebar dengan 4.1. Apa yang terjadi? Apa fungsi `float()`?
```python
panjang_kotak = input("Berapakah panjang kotak? ")
panjang_kotak = float(panjang_kotak)

lebar_kotak = input("Berapakah lebar kota? ")
lebar_kotak = float(lebar_kotak)

luas_kotak = panjang_kotak * lebar_kotak

print("Luas kotak adalah", luas_kotak)
```

1. Selain `int()` dan `float()`, Python juga memiliki `str()`,
yaitu suatu fungsi untuk mengubah data menjadi string.
Apa perbedaan program berikut dengan program sebelumnya?
```python
panjang_kotak = input("Berapakah panjang kotak? ")
panjang_kotak = float(panjang_kotak)

lebar_kotak = input("Berapakah lebar kota? ")
lebar_kotak = float(lebar_kotak)

luas_kotak = panjang_kotak * lebar_kotak

print("Luas kotak adalah " + str(luas_kotak))
```
---

### **Percabangan**
Misalkan kita diminta untuk membuat program seperti berikut.

1. User diminta input kata `pagi`. 
    ```python
    waktu = input("Masukkan kata pagi: ")
    ```

1. Jika user memasukkan kata `pagi`, program mencetak `Selamat datang`.
Jika tidak, program tidak mencetak apa-apa dan selesai.
    ```
    Untuk membuat dua pilihan seperti ini, kita menggunakan
    percabangan.
    ```

    ```python
    if (waktu == "pagi"):
        print("Selamat datang")
    else:
        print()
    ```

Sintaks dari percabangan adalah sebagai berikut.

```
if (<ekspresi boolean>):
    # kode yang akan dijalankan jika <ekspresi boolean> bernilai True
else:
    # kode yang akan dijalankan jika <ekspresi boolean> bernilai False
```

<br> <br>
![If blok ](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/if_else_sintaks.png)
<br> <br>

1. Dalam program tersebut, jika user mengetikkan `pagi`, variabel `waktu`
isinya sekarang adalah string `"pagi"`.

1. Ekspresi `waktu == "pagi"` bernilai `True`.

1. Karena `True`, statement percabangan menjadi `if(True)` sehingga blok kode di bawahnya
(bagian yang menjorok ke dalam) dijalankan.

1. Jika user mengetikkan selain `pagi`, misalnya `sore`, ekspresi `waktu == "pagi"` menjadi `False` 
sehingga statement percabangan menjadi `if(False)`.
Jika demikian, blok kode di bahwa statement `else` yang akan dijalankan.

Percabangan seperti ini, biasanya digambarkan dalam diagram alur (flowchart)
sebagai berikut.

<br> <br>
![If blok ](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/if_else_flowchart.png)
<br> <br>

!!! Catatan
    Saat membuat percabangan, semua pilihan kemungkinan harus dibuat.
    Untuk contoh di atas, terdapat dua pilihan, yaitu

    1. `pagi`
    1. lainnya

    Kedua pilihan ini sudah mencakup semua kemungkinan yang ada.


Bagaimana jika pilihannya lebih dari 2?
Misalnya jika user mengetikkan:

1. `pagi`
2. `sore`
3. lainnya

Output yang diharapkan adalah:

1. `Selamat datang`
1. `Sampai jumpa`
1. Tidak mencetak apa-apa

Secara umum, komputer hanya bisa memiliki dua percabangan, yaitu
saat `if(True)` dan saat `if(False)`.
Untuk menyiasati pilihan yang lebih dari dua, kita membuat
percabangan lagi di blok `if(False)`. 
Dengan demikian, pilihannya menjadi seperti berikut.

1. `pagi`
1. lainnya
    1. `sore`
    1.  lainnya


Untuk itu, kita harus menambahkan blok `if` ke dalam blok `else` sehingga menjadi `elif`. 

```python
waktu = input("Masukkan kata 'pagi' atau 'sore': ")

if (waktu == "pagi"):
    print("Selamat datang")
elif (waktu == "sore"):
    print("Sampai jumpa")
else:
    print()
```

Flowchart dari kode ini adalah sebagai berikut.

<br> <br>
![If blok ](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/if_elif_flowchart.png)
<br> <br>


!!! Catatan
    Perhatikan kembali karena ini sangat penting.
    Saat membuat percabangan, semua pilihan kemungkinan harus dibuat.
    Untuk contoh di atas, terdapat tiga pilihan, yaitu

    1. `pagi`
    1. `sore`
    1. lainnya`

    Jika pilihan yang dibuat tidak menampung semua kemungkinan,
    program dapat berjalan tidak sesuai dengan yang kita ingingkan.
    Terutama saat user melakukan sesuatu yang tidak diantisipasi
    programer.


**Coba**

1. Tuliskan kode program berikut dan jalankan.
    ```python
    nilai = int(input("Masukkan bilangan sembarang: ")) 

    if nilai >= 100:
        print("Bilangan besar")
    else:
        print("Bilangan kecil")
    ```

    !!! Catatan
        kurung dalam cara penulisan percabangan `if(<ekspresi>):` adalah opsional.
        Kita bisa juga menuliskannya tanpa kurung `if <ekspresi>:`.

1. Jalankan kode berikut.
    ```python
    nilai = input("Berapa nilai total? ")
    nilai = int(nilai)

    if nilai >= 80:   print("A")
    elif nilai >= 70: print("AB")
    elif nilai >= 65: print("B")
    elif nilai >= 60: print("BC")
    elif nilai >= 50: print("C")
    elif nilai >= 40: print("D")
    else:             print("E")
    ```

    !!! Catatan
        Jika blok kode untuk `if`, `elif`, ataupun `else` hanya terdiri dari
        satu baris, kita bisa menuliskannya langsung dalam satu baris.

1. Jalankan kode berikut.
    ```python
    nama   = input("Siapa nama Anda? ")
    umur   = int(input("Berapa umur Anda? "))
    gender = input("Anda Laki-laki atau perempuan (L/P)?")

    if (nama == "Budi"):
        print(nama)
        print(umur)
        print(gender)
    else:
        print("nama tidak dikenal")
        print("umur tidak dikenal")
        print("gender tidak diketahui")
    ```

1. Jalan program berikut.
    ```python
    angka1 = int(input("Masukkan angka pertama: "))
    angka2 = int(input("Masukkan angka kedua: "))

    if angka1 > angka2:
        print("Angka pertama lebih besar dari angka kedua.")
    elif angka1 < angka2:
        print("Angka pertama lebih besar dari angka kedua.")
    else:
        print("Angka pertama sama dengan angka kedua.")
    ```

1. Program tebak angka.
    ```python
    import random

    angka   = random.randint(1, 5)
    tebakan = int(input("Tebak angka yang di-generate komputer: "))

    if (tebakan == angka):
        print("Anda hebat, tebakan anda benar!!")
    else:
        print("Tebakan anda tidak tepat")
        print("Angka yang benar adalah " + str(angka))
    ```

    !!! Catatan
        `import random` adalah suatu baris perintah yang digunakan untuk meng-import modul `random`.
        Di dalam modul `random`, terdapat fungsi `randint()` yang dapat digunakan untuk menghasilkan
        bilangan acak.

        `random.randint(1,5)` adalah contoh penggunaan fungsi `randint()`.
        Ekspresi `random.randint(1,5)` disederhanakan menjadi bilangan bulat
        acak antara 1-5.`

---

## **Tugas Praktikum**
1. Lengkapi program berikut.
    ```python
    # Buat agar user mengetikkan suatu nilai float dan masukkan ke variabel a
    # Buat agar user mengetikkan suatu nilai float dan masukkan ke variabel b

    # cetak hasil a + b
    # cetak hasil a - b
    # cetak hasil a * b
    # cetak hasil a / b

    print("\nSekian, Terima Kasih")
    ```

1. Lengkapi program berikut.
    ```python
    umur = int(input("Berapa umur Anda? "))

    # jika umur lebih dari 40 disebut dewasa,
    # jika antara 20 - 40 disebut muda,
    # jika antara 10 - 20 disebut remaja
    # di bawah 10 disebut anak-anak
    ```

1. Lengkapi program berikut.
    ```python
    nilai = int(input("Masukkan satu bilangan: ""))

    # jika nilai lebih dari 100
    # tulis "nilai lebih dari 100"
    # jika nilai tidak lebih dari 100
    # tulis "nilai tidak lebih dari 100"
    ```

1. Apa beda kode berikut, 
    ```python
    kuliah = 'alpro'

    if kuliah == 'alpro':
        print(kuliah)
    elif kuliah == 'pbo':
        print('bukan alpro tapi juga ngoding')
    elif kuliah == 'agama':
        print('sama sekali gak ngoding')
    ```

    dengan kode ini?

    ```python
    kuliah = 'alpro'

    if kuliah == 'alpro':
        print(kuliah)
    if kuliah == 'pbo':
        print('bukan alpro tapi juga ngoding')
    if kuliah == 'agama':
        print('sama sekali gak ngoding')
    ```

1. Buatlah program tebak angka seperti yang ada di modul.
Buat agar setelah user menebak, keluar tiga pilihan output
berikut.
    1. `Tepat `jika user menjawab tepat
    1. `Sedikit lagi` jika selisih antara angka acak dan tebakan
    user kurang atau sama dengan 10.
    1. `Jauh` jika selisih antara angka acak dan tebakan user
    lebih dari 10.
