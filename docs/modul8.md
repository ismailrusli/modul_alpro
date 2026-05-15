# Modul 8: Modul Open Source 

![Status](https://img.shields.io/badge/Status-On_Progress-yellow?style=flat-square)
<!-- ![Status](https://img.shields.io/badge/Status-Finish-brightgreen?style=flat-square) -->

## **Capaian Pembelajaran Mata Kuliah**

Mampu membuat dan memodifkasi program sederhana
dengan bantuan modul open source.
---

## **Materi**

Membuat program yang kompleks, game misalnya,
membutuhkan sumber daya yang banyak.
Ukuran program yang kompleks bisa sangat besar
mencapai ratusan ribu baris.
Jika program seperti ini dibuat dari nol,
sangat banyak memakan waktu.
Untuk itu, programmer mengandalkan
modul-modul yang sudah dibuat orang lain.
Dengan modul-modul ini, programmer istilahnya
tidak *reinvent the wheel*.
Fungsi-fungsi, kelas-kelas, yang sudah dibuat orang lain,
kita gunakan sehingga kita bisa fokus ke
algoritma spesifik game kita.

!!! Catatan
    Ada banyak sekali modul-modul Python di internet
    yang bisa dipakai gratis. Modul-modul ini bisa kita
    lihat kodenya. Oleh karena itulah, modul-modul ini
    kita sebut *open source*.

Di Modul 8 ini, kita akan mencoba menggunakan satu modul
open source untuk membuat animasi, yaitu [Manim](https://www.manim.community/).

![Manim Logo](https://docs.manim.community/en/stable/_static/manim-logo-sidebar.svg)

### **Instalasi**

Ikuti cara instalasi di website resmi [Manim](https://docs.manim.community/en/stable/installation/uv.html).

### **Alur Pembuatan Animasi Menggunakan Manim**

Untuk membuat animasi menggunakan Manim, biasanya digunakan
alur sebagai berikut.

1. Buat Scene (`class <nama scene>(Scene):`)
1. Buat konstruktor (`def construct(self):`)
1. Buat objek dalam fungsi `costruct` 
1. Tambahkan atribut terhadap objek jika perlu
1. Animasikan (`self.play()`)

Perhatikan contoh berikut yang membuat kotak warna merah,
lalu menggerakkannya ke atas.

```py linenums="1" title="hello_manim.py"
class Kotak(Scene):
  def construct(self):
    kotak = Square(2)
    kotak.set_fill(RED, opacity=1.0)
    self.play(kotak.animate.shift(UP), run_time = 2)
```

Jalankan kode tersebut di terminal dengan memanggil perintah:

```
manim -pql hello_manim.py
```

1. `kotak = Square(2)` berarti membuat objek `Square` dengan panjang sisi 2 unit
1. `kotak.set_fill(RED, opacity=1.0)`, mewarnai kotak dengan warna merah
1. `self.play(kotak.animate.shift(UP), run_time = 2)` berarti
    menganimasikan kotak tersebut ke atas `UP` sebanyak 1 satuan
    dalam waktu (`run_time`) 2 detik. 
1. `-pql` artinya (p)lay setelah selesai render menggunakan (q)uality (l)ow.
    Untuk render dengan kualitas tinggi gunakan `manim -pqh`.

### **Membuat Objek Geometri**

Ada beberapa objek geometri dalam Manim, seperti:

- Lingkaran (`Circle`)
- Persegi panjang (`Rectangle`)
- Segitiga (`Triangle`)

Untuk lengkapnya, lihat
di [dokumentasi Manim tentang Polygram](https://docs.manim.community/en/stable/reference/manim.mobject.geometry.polygram.html#module-manim.mobject.geometry.polygram).

Kita bisa menganimasikan pembuatan objek geometri tersebut
menggunakan Fungsi `Create`.

```py linenums="1" title="hello_manim.py"
from manim import *

class BuatObjek(Scene):
  def construct(self):
    lingkaran = Circle(2)
    lingkaran.set_fill(BLUE, opacity=1.0)
    self.play(Create(lingkaran), run_time=2)
```

Sebagai alternatif, kita juga bisa menggunakan fungsi `FadeIn`.

```py linenums="1" title="hello_manim.py"
from manim import *

class BuatObjek(Scene):
  def construct(self):
    lingkaran = Circle(2)
    lingkaran.set_fill(BLUE, opacity=1.0)
    self.play(FadeIn(lingkaran), run_time=2)
```

**Coba**

Coba buat objek-objek geometri menggunakan Manim.
Ubah-ubah ukuran dan warnanya.
Gerakkan ke berbagai arah (`UP`, `DOWN`, `LEFT`, `RIGHT`).

!!! Catatan
    1. Untuk berpindah lebih jauh, gunakan pengali (`2 * UP`).
    1. Untuk gerakan pindah berurutan (misalnya ke kanan lalu ke atas),
        panggil `self.play` secara berurutan pula.  
        ```py
        self.play(kotak.animate.shift(RIGHT), run_time=2)
        self.play(kotak.animate.shift(UP), run_time=2)
        ```
    1. Untuk berpindah diagonal (misalnya ke kanan atas) gunakan
        operator penjumlahan.
        ```py
        self.play(kotak.animate.shift(RIGHT + UP), run_time=2)
        ```

### **Transformasi**
Sebuah objek dapat bertransformasi menjadi objek lainnya
dengan fungsi `Transform`.

```py linenums="1"
from manim import *

class LingkaranJadiKotak(Scene):
  def construct(self):
    lingkaran = Circle()
    kotak = Square()
    self.play(Create(lingkaran))
    self.play(Transform(lingkaran, kotak), run_time=2)
    self.wait(1)
```

Pahami kode berikut, tuliskan, lalu jalankan.

```py linenums="1" 
from manim import *

class LingkaranJadiKotak(Scene):
  def construct(self):
    lingkaran = Circle()
    kotak = Square()
    segitiga = Triangle()
    titik_pusat_segitiga = segitiga.get_center_of_mass()

    # Buat kotak dan lingkaran di tengah
    self.play(Create(lingkaran), Create(kotak))

    # lingkaran geser kiri, kotak geser kanan, segitiga muncul di tengah
    self.play(lingkaran.animate.shift(2 * LEFT), kotak.animate.shift(2 * RIGHT), FadeIn(segitiga), run_time=2)

    # Rotasi segitiga di titik pusatnya sebesar 60 derajat (pi/3)
    self.play(Rotate(segitiga, PI/3, about_point=titik_pusat_segitiga), run_time=2)

    # Transform kotak dan lingkaran jadi segitiga
    self.play(Transform(lingkaran, segitiga), Transform(kotak, segitiga))

    self.wait(1)
```

**Coba**

1. Buat animasi kotak yang bergerak dari ujung kiri layar
    ke ujung kanan layar. Sebelum bergerak, kotak berputar dulu di tempatnya.
    Untuk memindahkan ke pinggir layar, bisa gunakan
    fungsi `to_edge()`. Misal ke pinggir kiri layar
    gunakan `to_edge(LEFT)`, ke pinggir kiri atas `to_edge(LEFT + UP)`.

1. Buat tiga objek (segitiga, kotak, dan lingkaran). Munculkan segitiga di tengah
    lalu pindahkan ke pinggir kiri. Munculkan kotak di tengah, lalu
    pindahkan ke pinggir kanan. Munculkan lingkaran di tengah, lalu
    pindahkan ke ujung atas layar (`to_edge(UP)`). 
    Selanjutnya, buat ketiganya berputar secara serentak.

### **Teks**

Selain objek, kita juga bisa membuat teks dalam manim.
Perhatikan kode berikut.

```py linenums="1"
from manim import *

class Tulisan(Scene):
  def construct(self):
    alpro = Text("Algoritma dan Pemrograman")
    self.play(Create(alpro))
    self.wait(2)
```

Kita bisa mengotaki teks yang kita buat seperti berikut.

```py linenums="1"
from manim import *

class Tulisan(Scene):
  def construct(self):
    alpro = Text("Algoritma dan Pemrograman")
    box = SurroundingRectangle(alpro)
    self.play(FadeIn(alpro), Create(box))
    self.wait(2)
```

**Coba**

Cobalah untuk membuat dua teks dan lakukan
transformasi dari satu teks ke teks lainnya.
Bisakah?

---

## **Tugas Praktikum**

Lakukan eksplorasi dokumentasi Manim.
Cobalah contoh-contoh kode yang
ada di [Example Gallery](https://docs.manim.community/en/stable/examples.html).
Baca juga [Reference Manual](https://docs.manim.community/en/stable/reference.html)
