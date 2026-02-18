# **Modul 2: Variabel, Literal, dan Operator**

## **Tujuan Pembelajaran**

Mampu menggunakan elemen-elemen dasar pemrograman, seperti inisialisasi variabel 
untuk berbagai macam tipe data, menggunakan percabangan, menggunakan pengulangan, 
membuat dan menggunakan fungsi, serta membuat dan menggunakan tipe data bentukan sendiri.

## **Alat dan Bahan**
1. Laptop/komputer
1. Internet
1. Python 3.8+
1. Visual Studio Code (atau editor sejenis)

## **Materi**

Secara abstrak, program komputer dapat dilihat seperti gambar berikut. 
![Program komputer secara abstrak](https://raw.githubusercontent.com/ismailrusli/modul_alpro/refs/heads/master/gambar/proses.png)
Program komputer memiliki input dan output.
Ke dalam input, dimasukkan data.
Dari output, keluar data.
Jadi, tugas program komputer adalah memproses data. 
Dengan kata lain: dari data menjadi data. 

Oleh karena program berkaitan erat dengan data,
kita mulai juga dengan data.
Ada 3 istilah penting dalam pemrograman terkait data, yaitu

1. Literal
1. Jenis/tipe data
1. Operator

\subsection{Literal}
Literal adalah nilai/isi data. Contohnya bilangan \texttt{5}.
Contoh lain adalah huruf atau sekumpulan karakter (string), 
misalnya \texttt{"a"} dan \texttt{"Bandung"}.
Keduanya ditulis dalam tanda petik untuk membedakan
dengan perintah yang dipakai dalam bahasa pemrograman.
Di Kode \ref{literal1}, kata \texttt{print} yang pertama
adalah perintah dan kata \texttt{"print"} di dalam tanda petik
adalah literal.

\lstinputlisting[caption={Perintah dan literal},label={literal1}]{kode/variabel/literal.py}

Kita bisa menuliskan literal ke dalam Python Interpreter. 
Sebagai contoh, ketikkan literal-literal berikut dan tekan Enter
setiap kali selesai mengetikkan satu literal.
\begin{enumerate}[itemsep=0pt,parsep=0pt]
  \item \texttt{5}
  \item \texttt{5.03}
  \item \texttt{'a'}
  \item \texttt{'algoritma'}
  \item \texttt{True}
  \item \texttt{[1,2,3]}
\end{enumerate}

Sekarang, coba ketikkan \texttt{a} (tanpa tanda petik). Apa yang terjadi?
Mengapa demikian?

\subsection{Jenis/Tipe Data}
Data tentu bermacam-macam. 
Ada data berupa bilangan bulat (Contoh \texttt{5}).
Ada data berupa bilangan riil (Contoh \texttt{5.03}).
Ada data berupa karakter(Contoh \texttt{"a"}).
Ada data berupa rangkaian karakter (Contoh \texttt{"algoritma"}).
Ada data berupa nila kebenaran suatu ekspresi/logika (Contoh \texttt{True}).
Ada juga data berupa kumpulan bilangan (Contoh \texttt{[1,2,3]}).

Dalam pemrograman, setiap tipe data biasanya ada namanya.
Sebagai contoh, untuk data berupa bilangan bulat,
biasanya tipe datanya disebut \textbf{integer}.
Untuk data berupa bilangan riil, disebut \textbf{float} atau
\textbf{double}.
Untuk karakter biasanya disebut \textbf{char}.
Untuk serangkaian karakter biasanya disebut \textbf{string}.
Untuk kumpulan bilangan bisa disebut sebagai \textbf{array}
atau \textbf{list} atau \textbf{set} atau lainnya.
Setiap bahasa pemrograman, menentukan sendiri tipe
datanya. Pemrogram dapat juga membuat
tipe data kustom sesuai kebutuhan.

Coba ketikkan setiap baris berikut ke dalam Python Interpreter 
(Enter setelah mengetikkan satu baris).
\begin{enumerate}[itemsep=0pt,parsep=0pt]
  \item \texttt{type(5)}
  \item \texttt{type(5.03)}
  \item \texttt{type('a')}
  \item \texttt{type('algoritma')}
  \item \texttt{type(True)}
  \item \texttt{type([1,2,3])}
\end{enumerate}

Sebagai catatan, dalam bahasa pemrograman Python, tidak dibedakan
antara tipe data \textbf{char} dan \textbf{string}. Keduanya 
dianggap sebagai \textbf{string}.

\subsection{Mendefinisikan Variabel}
Satu komponen penting dari sebuah program adalah variabel.
Variabel digunakan untuk menampung data. 
Variabel memiliki nama agar mudah dipanggil. 
Contohnya adalah program di Kode \ref{int01}.
\lstinputlisting[caption={Variabel dengan nama \texttt{a}},label={int01}]{kode/variabel/int01.py}

Di Kode \ref{int01}, variabel dengan nama \texttt{a} diisi dengan data
berupa bilangan 100. Kita bisa melambangkannya seperti ini: $\texttt{a} \leftarrow 100$.
Baris ketiga dari Kode \ref{int01} adalah baris untuk mencetak 
isi dari variabel \texttt{a} ke layar (via terminal).
Jika kamu menjalankan Kode \ref{int01}, hasilnya adalah munculnya angka 100 di terminal. 
Berapakah bilangan yang muncul di kode-kode berikut?
\lstinputlisting[caption={Bilangan berapa yang akan muncul?},label={int02}]{kode/variabel/int02.py}
\lstinputlisting[caption={Bilangan berapa yang akan muncul?},label={int03}]{kode/variabel/int03.py}
\lstinputlisting[caption={Bilangan berapa yang akan muncul?},label={int04}]{kode/variabel/int04.py}
\lstinputlisting[caption={Bilangan berapa yang akan muncul?},label={int05}]{kode/variabel/int05.py}
\lstinputlisting[caption={Bilangan berapa yang akan muncul?},label={int06}]{kode/variabel/int06.py}
\lstinputlisting[caption={Bilangan berapa yang akan muncul?},label={int07}]{kode/variabel/int07.py}
\lstinputlisting[caption={Bilangan berapa yang akan muncul?},label={int08}]{kode/variabel/int08.py}
\lstinputlisting[caption={Bilangan berapa yang akan muncul?},label={int09}]{kode/variabel/int09.py}
\lstinputlisting[caption={Bilangan berapa yang akan muncul?},label={int10}]{kode/variabel/int10.py}

\subsection{Tipe Data Dasar}
Jika kita perhatikan Kode \ref{int01}-\ref{int10}, 
variabel-variabel di sana diisi bilangan bulat atau integer.
Tentu saja variabel bisa diisi selain dari integer.
Contohnya diisi \textit{string} di Kode \ref{str01},
diisi \textit{float} di Kode \ref{float01},
dan diisi \textit{boolean} di Kode \ref{bool01}.
Integer, string, float, dan boolean disebut sebagai tipe data.
Lebih jauh, keempatnya merupakan tipe data dasar dalam Python.
\lstinputlisting[caption={Contoh variabel string},label={str01}]{kode/variabel/str01.py}
\lstinputlisting[caption={Contoh variabel float},label={float01}]{kode/variabel/float01.py}
\lstinputlisting[caption={Contoh variabel boolean},label={bool01}]{kode/variabel/bool01.py}

Berikut adalah beberapa contoh kode menggunakan tipe data
string, float, dan boolean.
\lstinputlisting[caption={Contoh variabel string},label={str02}]{kode/variabel/str02.py}
\lstinputlisting[caption={Contoh variabel float},label={float02}]{kode/variabel/float02.py}
\lstinputlisting[caption={Jika integer ditambah float, apa hasilnya?},label={float03}]{kode/variabel/float03.py}
\lstinputlisting[caption={Apa hasilnya?},label={bool02}]{kode/variabel/bool02.py}
\lstinputlisting[caption={Apa hasilnya?},label={bool03}]{kode/variabel/bool03.py}

Untuk mengetahui tipe data yang terdapat dalam sebuah variabel,
kita dapat menggunakan perintah \texttt{type} seperti dalam Kode \ref{var01}.
\lstinputlisting[caption={Mengetahui tipe data sebuah variabel},label={var01}]{kode/variabel/var01.py}

Python adalah bahasa pemrograman yang cukup fleksibel.
Saat membuat variabel, kita tidak perlu 
menentukan tipe data dari variabel tersebut.
Bahkan, sebuah variabel dapat menampung tipe data
yang berbeda-beda, seperti contoh di Kode \ref{var02}.
\lstinputlisting[caption={Variabel \texttt{x} dapat berubah tipe datanya},label={var02}]{kode/variabel/var02.py}

\subsection{Tipe Data Lanjut}
Selain tipe data dasar, seperti integer, float, string, dan boolean, terdapat
juga tipe data lanjut. Berikut adalah beberapa contoh tipe data lanjut.

\subsubsection{List}
List dapat dianggap sebagai daftar. Sebuah list dapat berisi daftar integer, string,
float, atau boolean. List juga dapat berisi daftar campuran.
\lstinputlisting[caption={Tipe data \textit{list} dari integer},label={list01}]{kode/variabel/list01.py}
\lstinputlisting[caption={Tipe data \textit{list} dari float},label={list02}]{kode/variabel/list02.py}
\lstinputlisting[caption={Tipe data \textit{list} dari string},label={list03}]{kode/variabel/list03.py}
\lstinputlisting[caption={Tipe data \textit{list} dari boolean},label={list04}]{kode/variabel/list04.py}
\lstinputlisting[caption={Tipe data \textit{list} dari data gabungan},label={list05}]{kode/variabel/list05.py}

Untuk mengambil satu data dari list, gunakan kurung siku seperti contoh Kode \ref{list06}
berikut. Untuk mengakses data pertama dalam list, gunakan indeks $0$.
Untuk mengakses data terakhir dalam list, gunakan indeks $-1$ jika
kita tidak tahu ada berapa elemen di dalam list tersebut.
\lstinputlisting[caption={Akses satu data dalam list},label={list06}]{kode/variabel/list06.py}
\lstinputlisting[caption={Akses satu data dalam list},label={list07}]{kode/variabel/list07.py}
\lstinputlisting[caption={Akses data terakhir dalam list},label={list08}]{kode/variabel/list08.py}

Untuk menambahkan data ke akhir list, gunakan perintah \texttt{append}.
Contohnya seperti dalam Kode \ref{list09}. 
Sementara untuk menambah data di sembarang posisi, gunakan perintah
\texttt{insert}. Contohnya di Kode \ref{list10}.
\lstinputlisting[caption={Menambah data di akhir list},label={list09}]{kode/variabel/list09.py}
\lstinputlisting[caption={Menambah data di posisi sebelum data ke-1 di list},label={list10}]{kode/variabel/list10.py}

Untuk menghapus data di list, gunakan perintah \texttt{remove}, \texttt{pop}, atau
\texttt{del}. Berikut adalah contoh-contohnya.
\lstinputlisting[caption={Menghapus data/item dari list},label={list12}]{kode/variabel/list12.py}

Dua list juga bisa digabungkan, contohnya di Kode \ref{list11}.
\lstinputlisting[caption={Penggabungan 2 list},label={list11}]{kode/variabel/list11.py}

Untuk mengetahui jumlah data dalam list,  gunakan perintah \texttt{len} (Kode \ref{list19}).
\lstinputlisting[caption={Mengetahui panjang list},label={list19}]{kode/variabel/list19.py}

Sebagai latihan, coba pahami kode-kode berikut.
\lstinputlisting[caption={Apa hasilnya?},label={list13}]{kode/variabel/list13.py}
\lstinputlisting[caption={Apa hasilnya?},label={list14}]{kode/variabel/list14.py}
\lstinputlisting[caption={Apa hasilnya?},label={list15}]{kode/variabel/list15.py}
\lstinputlisting[caption={Apa hasilnya?},label={list16}]{kode/variabel/list16.py}
\lstinputlisting[caption={Apa hasilnya?},label={list17}]{kode/variabel/list17.py}
\lstinputlisting[caption={Apa hasilnya?},label={list18}]{kode/variabel/list18.py}

\subsubsection{Tuple}
Tuple mirip seperti list hanya saja elemen di dalam tuple tidak dapat diubah.
Tuple juga dituliskan dalam kurung biasa sementara list dituliskan dalam
kurung siku. Sebagai contoh perhatikan Kode \ref{tuple01}.
\lstinputlisting[caption={Data dalam tuple tidak dapat diubah.},label={tuple01}]{kode/variabel/tuple01.py}

Dua tuple dapat digabungkan dengan menggunakan simbol $+$.
Perhatikan contoh di Kode \ref{tuple02}.
\lstinputlisting[caption={Dua tuple digabungkan menggunakan operator $+$.},label={tuple02}]{kode/variabel/tuple02.py}

Tuple digunakan untuk merepresentasikan data yang ukurannya sudah diketahui,
misalnya posisi objek dalam ruang 3 dimensi $\rightarrow (x,y,z)$.

\subsubsection{Dictionary}
Dictionary, seperti artinya yaitu kamus. Dictionary adalah tipe data yang terdiri dari pasangan
key dan value. Dalam kamus, misalnya kamus Indonesia-Inggirs, 
setiap entri terdiri dari 2 item, yaitu kata dan artinya.
Dalam dictionary juga sama. Untuk jelasnya, perhatikan Kode \ref{dict01}.
\lstinputlisting[caption={Tipe data dictionary},label={dict01}]{kode/variabel/dict01.py}

Di Kode \ref{dict01}, kita lihat pasangan datanya bertipe string dan integer ('budi' : 30).
Setiap pasang dalam satu dictionary, tidak harus memiliki tipe data yang sama
dan key tidak harus string.
Contohnya di Kode \ref{dict02}.
\lstinputlisting[caption={Tipe key dan value dalam dictionary tidak harus sama},label={dict02}]{kode/variabel/dict02.py}

%Apakah key harus selalu string? Tidak. 
%Perhatikan Kode \ref{dict03}.
%Bisakah kamu mencari contoh kasus yang membutuhkan penyimpanan data
%dalam dictionary dengan key yang tidak bertipe string?
%\lstinputlisting[caption={Sembarang tipe data dapat digunakan untuk key.},label={dict03}]{kode/variabel/dict03.py}

Untuk menambah, mengganti, atau menghapus data di dictionary, lihat Kode \ref{dict04}.
Di Kode \ref{dict04}, ditunjukkan dua cara untuk menghapus data dari dictionary,
yaitu menggunakan perintah \texttt{del} dan \texttt{pop}.
Selain dari kedua perintah tersebut, terdapat perintah lain juga.
Kamu dapat mengetahui perintah-perintah yang ada di Python 
dengan mencarinya di Google\footnote{Contohnya di sini: https://www.w3schools.com/python/default.asp}.
\lstinputlisting[caption={Menambah, mengganti, atau menghapus data di dictionary.},label={dict04}]{kode/variabel/dict04.py}

Untuk mendapatkan semua key dari dictionary, perhatikan Kode \ref{dict05}.
\lstinputlisting[caption={Mendapatkan semua key dalam sebuah dictionary.},label={dict05}]{kode/variabel/dict05.py}

\subsection{Operator}
Dua variabel dapat dioperasikan menggunakan operator (Kode \ref{op1}). 
%dan hasilnya di Kode \ref{op1.hasil}.
\lstinputlisting[caption={Operator aritmatika},label={op1}]{kode/variabel/op1.py}
%\lstinputlisting[caption={Hasil program di Kode \ref{op1}},label={op1.hasil}]{kode/variabel/variabel/op1.hasil}

Kode \ref{op1} menunjukkan operator aritmatika.
Jenis operator lainnya adalah operator perbandingan.
Operator perbandingan digunakan untuk membandingkan 2 variabel.
Perhatikan Kode \ref{op2}.
%dan hasilnya di Kode \ref{op2.hasil}.
\lstinputlisting[caption={Operator perbandingan},label={op2}]{kode/variabel/op2.py}
%\lstinputlisting[caption={Hasil program di Kode \ref{op2}},label={op2.hasil}]{kode/variabel/variabel/op2.hasil}

Untuk variabel tipe data string, simbol \texttt{+} dapat digunakan untuk
menggabungkan dua string atau lebih (\textit{concatenation}).
Perhatikan Kode \ref{op3}.
%dan hasilnya di Kode \ref{op3.hasil}.
\lstinputlisting[caption={Penggabungan 2 variabel string menggunakan operator \texttt{+}},label={op3}]{kode/variabel/op3.py}
%\lstinputlisting[caption={Hasil dari program di Kode \ref{op3}},label={op3.hasil}]{kode/variabel/variabel/op3.hasil}

Selain itu, ada juga operator logika. Contohnya di Kode \ref{op4}.
%dan hasilnya di Kode \ref{op4.hasil}.
\lstinputlisting[caption={Operator logika},label={op4}]{kode/variabel/op4.py}
%\lstinputlisting[caption={Hasil dari program di kode \ref{op4}},label={op4.hasil}]{kode/variabel/variabel/op4.hasil}

\subsection{Input}
Salah satu yang membuat sebuah program interaktif adalah
program tersebut dapat menerima input dari pengguna.
Perhatikan contoh di Kode \ref{input01}.
Jalankan prorgram tersebut. Apa yang terjadi?
\lstinputlisting[caption={Program yang dapat menerima input dari pengguna},label={input01}]{kode/variabel/input01.py}
%\lstinputlisting[caption={Hasil dari program di kode \ref{input1}},label={input1.hasil}]{kode/variabel/variabel/input1.hasil}

Sekarang perhatikan contoh program input lainnya di Kode \ref{input02}.
Jalankan program tersebut dan apa yang terjadi?
\lstinputlisting[caption={Program yang meminta pengguna input angka},label={input02}]{kode/variabel/input02.py}

Apakah tipe data dari variabel \texttt{a}, \texttt{b}, dan \texttt{c} dalam Kode \ref{input02}?
Ya, betul, tipe data ketiga variabel tersebut adalah string.
Agar masukan pengguna dapat kita anggap sebagai bilangan, kita
harus mengubahnya dulu (\textit{type casting}).
Perhatikan Kode \ref{input03}, tulis dan jalankan program tersebut.
\lstinputlisting[caption={Variabel \texttt{a} dan \texttt{b}, kita ubah ke integer dan \texttt{c} kita ubah ke string},label={input03}]{kode/variabel/input03.py}

Perintah di baris 3 adalah menyuruh komputer untuk mengubah terlebih dahulu
variabel \texttt{a} ke integer (\texttt{int(a)}), lalu variabel \texttt{b} ke integer (\texttt{int(b)}),
kemudian menjumlahkan 2 integer tersebut dan menyimpannya di \texttt{c}.

\subsection{Contoh Program}
Kode \ref{menu} adalah contoh program sederhana memilih menu di restoran.
Tulis program tersebut dan jalankan. Apa yang terjadi?
\lstinputlisting[caption={Program menu},label={menu}]{kode/variabel/menu.py}

\subsection{Kerjakan}
\begin{enumerate}
	\item Terdapat error di Kode \ref{var-soal01} - Kode \ref{var-soal08}. Perbaikilah.
		\lstinputlisting[caption={Perbaiki program berikut.},label={var-soal01}]{kode/variabel/var-soal01.py}
		\lstinputlisting[caption={Perbaiki program berikut.},label={var-soal02}]{kode/variabel/var-soal02.py}
		\lstinputlisting[caption={Perbaiki program berikut.},label={var-soal03}]{kode/variabel/var-soal03.py}
		\lstinputlisting[caption={Perbaiki program berikut.},label={var-soal04}]{kode/variabel/var-soal04.py}
		\lstinputlisting[caption={Perbaiki program berikut.},label={var-soal05}]{kode/variabel/var-soal05.py}
		\lstinputlisting[caption={Perbaiki program berikut.},label={var-soal06}]{kode/variabel/var-soal06.py}
		\lstinputlisting[caption={Perbaiki program berikut.},label={var-soal07}]{kode/variabel/var-soal07.py}
		\lstinputlisting[caption={Perbaiki program berikut.},label={var-soal08}]{kode/variabel/var-soal08.py}
	\item Buatlah program yang menerima input dari user berupa angka 0-9, lalu
		munculkan string yang bersesuaian. Misalnya, user memasukkan angka 1,
		maka print string "satu". \textbf{Petunjuk:} Gunakan list untuk menyimpan kata-katanya.
%	\item Tulislah program di Kode \ref{loop.list} lalu jalankan.  Apa yang terjadi?
%		\lstinputlisting[caption={Latihan1},label={loop.list}]{kode/variabel/variabel/loop-list.py}
%	\item Tulislah program di Kode \ref{add.list} lalu jalankan.  Apa yang terjadi?
%		\lstinputlisting[caption={Latihan2},label={add.list}]{kode/variabel/variabel/add-list.py}
%	\item Tulislah program di Kode \ref{list.index} lalu jalankan. Apa yang terjadi?
%		\lstinputlisting[caption={Latihan3},label={list.index}]{kode/variabel/variabel/list-index.py}
%	\item Tulislah program di Kode \ref{list.append.remove} lalu jalankan. Apa yang terjadi?
%		\lstinputlisting[caption={Latihan4},label={list.append.remove}]{kode/variabel/variabel/list-append-remove.py}
%	\item Tulislah program di Kode \ref{string.index} lalu jalankan. Apa yang terjadi?
%		\lstinputlisting[caption={Latihan5},label={string.index}]{kode/variabel/variabel/string-index.py}
	\item Komputer dapat menghasilkan bilangan acak seperti yang tertulis di Kode \ref{random}. 
		\lstinputlisting[caption={Komputer menghasilkan bilangan acak antara 1-100},label={random}]{kode/variabel/myrandom.py}
		Buatlah suatu game sederhana.
		Program men-generate angka acak antara 0-100.
		User menebak angka yang di-generate komputer (inputkan angkanya).
		Munculkan skor tebakannya dengan cara menentukan selisih antara
		angka komputer dan angka tebakannya. Perhatikan contoh di Kode \ref{bab01-soal10}.
		\lstinputlisting[caption={Contoh program tebak angka.},label={bab01-soal10}]{kode/variabel/bab01-soal10.hasil}
  \item Suatu list dapat diubah menjadi tuple, carilah caranya di Internet lalu buat program contohnya.
    Buat juga sebaliknya, yaitu dari tuple menjadi list.
  \item Buat program yang memunculkan nama 5 huruf secara random dengan ketentuan, 
    huruf ke-2 dan ke-4 vokal, sisanya konsonan. Petunjuk: gunakan dua list, yaitu list untuk vokal
    dan list untuk konsonan. Lalu gunakan fungsi random untuk mengambil huruf dari kedua list tersebut.
  \item Buat seperti program nama acak sebelumnya, tapi minta user untuk memasukkan huruf pertama
    nama acak tersebut.
  \item Buat program pertandingan dengan skenario sebagai berikut.
    \begin{enumerate}[itemsep=0pt, parsep=0pt]
      \item Ketika program dijalankan, user diminta memasukkan nama pertama, lalu enter
      \item Selanjutnya, user diminta memasukkan angka ke-2, lalu enter
      \item Lalu program menuliskan nama pertama dan skornya (random antara 0-100)
        serta nama kedua dan skornya (dalam baris berbeda)
    \end{enumerate}
  \item Buatlah program yang mengacak kata. Skenarionya adalah, user diminta untuk memasukkan
    kata, lalu tampilkan versi teracak dari kalimat tersebut (kata-katanya diacak).
    Petunjuk: gunakan fungsi \texttt{split} untuk memisahkan kalimat ke dalam list dari kata-kata.
    Lalu gunakan \texttt{random.shuffle()} untuk mengacak list tersebut.
    Selanjutnya, gabungkan lagi kata-kata dalam list tersebut menggunakan perintah
    \texttt{" ".join(list)}
\end{enumerate}

%\begin{figure}
%	\centering
%	\includegraphics[width=8cm]{gambar/flowchart1.png}
%	\caption{Diagram alir (flowchart) dari program tebak angka.}
%	\label{fig:flow1}
%\end{figure}

