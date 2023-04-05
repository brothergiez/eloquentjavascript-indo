# Chapter 1 Nilai, Tipe, dan Operator

> Di bawah permukaan mesin, program bergerak. Tanpa usaha, ia memperluas dan mengecil. Dalam harmoni besar, elektron tersebar dan berkumpul kembali. Bentuk-bentuk pada monitor hanyalah riak-riak di atas air. Esensi tetap tidak terlihat di bawahnya. 

_--Master Yuan-Ma, The Book of Programming_

Di dalam dunia komputer, hanya ada data. Anda dapat membaca data, mengubah data, membuat data baru—tetapi yang bukan data tidak dapat disebutkan. Semua data ini disimpan sebagai urutan panjang bit dan karena itu pada dasarnya sama.

Bit adalah segala jenis benda dengan dua nilai, biasanya dijelaskan sebagai nol dan satu. Di dalam komputer, mereka mengambil bentuk seperti muatan listrik tinggi atau rendah, sinyal kuat atau lemah, atau bercak berkilau atau kusam pada permukaan CD. Setiap informasi diskrit dapat dikurangi menjadi urutan nol dan satu dan dengan demikian direpresentasikan dalam bit.

Sebagai contoh, kita dapat mengungkapkan angka 13 dalam bit. Ini bekerja sama dengan angka desimal, tetapi daripada 10 digit yang berbeda, Anda hanya memiliki 2, dan bobot masing-masing meningkat dengan faktor 2 dari kanan ke kiri. Berikut ini adalah bit yang membentuk angka 13, dengan bobot digit yang ditunjukkan di bawahnya:

```
0 0 0 0 1 1 0 1
128 64 32 16 8 4 2 1
```

Jadi itu adalah angka biner 00001101. Digit non-nolnya mewakili 8, 4, dan 1, dan berjumlah 13.

## Nilai

Bayangkan lautan bit—sebuah samudera dari bit. Komputer modern biasanya memiliki lebih dari 30 miliar bit di dalam penyimpanan data volatilnya (memori kerja). Penyimpanan non-volatil (hard disk atau yang setara) cenderung memiliki beberapa orde magnitudo lebih banyak lagi.

Untuk dapat bekerja dengan jumlah bit yang sedemikian banyak tanpa tersesat, kita harus memisahkan mereka menjadi bagian-bagian yang mewakili informasi. Dalam lingkungan JavaScript, bagian-bagian itu disebut nilai. Meskipun semua nilai terbuat dari bit, mereka memainkan peran yang berbeda. Setiap nilai memiliki tipe yang menentukan perannya. Beberapa nilai adalah angka, beberapa nilai adalah potongan teks, beberapa nilai adalah fungsi, dan sebagainya.

Untuk membuat nilai, Anda hanya perlu memanggil namanya. Ini mudah. Anda tidak perlu mengumpulkan bahan bangunan untuk nilai Anda atau membayarnya. Anda hanya memanggil salah satu, dan whoosh, Anda memilikinya. Mereka tidak benar-benar dibuat dari udara tipis, tentu saja. Setiap nilai harus disimpan di suatu tempat, dan jika Anda ingin menggunakan sejumlah besar nilai secara bersamaan, Anda mungkin akan kehabisan memori. Untungnya, ini hanya menjadi masalah jika Anda membutuhkan semuanya secara bersamaan. Begitu Anda tidak lagi menggunakan sebuah nilai, ia akan hilang, meninggalkan bit-nya untuk didaur ulang sebagai bahan bangunan untuk generasi nilai berikutnya.

Bab ini memperkenalkan elemen-elemen atom dari program JavaScript, yaitu jenis nilai sederhana dan operator yang dapat bertindak pada nilai-nilai tersebut.

##  Angka

Nilai dari tipe data angka adalah, seperti yang bisa ditebak, nilai numerik. Dalam program JavaScript, angka ditulis sebagai berikut:

```
13
```


Gunakan itu dalam program, dan itu akan membuat pola bit untuk angka 13 ada di dalam memori komputer.

JavaScript menggunakan jumlah bit yang tetap, 64 bit, untuk menyimpan nilai angka tunggal. Hanya ada beberapa pola yang dapat dibuat dengan 64 bit, yang berarti jumlah angka yang berbeda yang dapat direpresentasikan terbatas. Dengan N digit desimal, Anda dapat mewakili 10<sup>N</sup> angka. Begitu juga, dengan 64 digit biner, Anda dapat merepresentasikan 2<sup>64</sup> angka yang berbeda, yang sekitar 18 kuadriliun (18 dengan 18 nol setelahnya). Itu sangat banyak.

Memori komputer dulunya jauh lebih kecil, dan orang cenderung menggunakan kelompok 8 atau 16 bit untuk merepresentasikan angka-angka mereka. Mudah untuk secara tidak sengaja melebihi batas angka yang kecil ini - sampai pada angka yang tidak muat ke dalam jumlah bit yang diberikan. Saat ini, bahkan komputer yang muat di saku Anda memiliki banyak memori, sehingga Anda bebas menggunakan gumpalan 64 bit, dan Anda hanya perlu khawatir tentang overflow (melebihi batas) saat berurusan dengan angka-angka yang benar-benar astronomi.

Namun, tidak semua bilangan bulat kurang dari 18 kuadriliun muat dalam tipe data angka JavaScript. Bit-bit tersebut juga menyimpan bilangan negatif, sehingga satu bit menunjukkan tanda angka. Masalah yang lebih besar adalah bahwa bilangan tidak bulat juga harus direpresentasikan. Untuk melakukannya, beberapa bit digunakan untuk menyimpan posisi titik desimal. Angka bulat maksimum yang sebenarnya yang dapat disimpan berada dalam kisaran 9 kuadriliun (15 nol) - yang masih sangat besar.

Angka pecahan ditulis dengan menggunakan titik.

```
9.81
```

Untuk angka yang sangat besar atau sangat kecil, Anda juga dapat menggunakan notasi ilmiah dengan menambahkan huruf e (untuk eksponen), diikuti oleh eksponen dari angka tersebut.

```
2.998e8
```

Artinya 2,998 × 10^8 = 299.800.000.

Perhitungan dengan angka bulat (juga disebut bilangan bulat) yang lebih kecil dari 9 kuadriliun yang disebutkan dijamin selalu akurat. Sayangnya, perhitungan dengan angka pecahan umumnya tidak akurat. Sama seperti π (pi) tidak dapat diungkapkan secara tepat dengan jumlah digit desimal yang terbatas, banyak angka kehilangan beberapa presisi ketika hanya 64 bit tersedia untuk menyimpannya. Ini sangat disayangkan, tetapi hanya menyebabkan masalah praktis pada situasi tertentu. Hal yang penting adalah menyadari hal ini dan memperlakukan angka digital pecahan sebagai perkiraan, bukan sebagai nilai yang tepat.

## Aritmatika
Hal utama yang dilakukan dengan angka adalah aritmatika. Operasi aritmatika seperti penjumlahan atau perkalian mengambil dua nilai angka dan menghasilkan angka baru dari mereka. Berikut adalah contohnya dalam JavaScript:

```
100 + 4 * 11
```

Simbol + dan * disebut operator. Yang pertama melambangkan penjumlahan, dan yang kedua melambangkan perkalian. Menempatkan operator antara dua nilai akan menerapkannya pada nilai tersebut dan menghasilkan nilai baru.

Namun, apakah contoh tersebut berarti "menambahkan 4 dan 100, dan mengalikan hasilnya dengan 11" ataukah perkalian dilakukan sebelum penjumlahan? Seperti yang mungkin sudah Anda tebak, perkalian terjadi terlebih dahulu. Namun seperti dalam matematika, Anda dapat mengubahnya dengan membungkus penjumlahan dalam tanda kurung.

```
(100 + 4) * 11
```

Untuk pengurangan, ada operator -, dan pembagian dapat dilakukan dengan operator /.

Ketika operator muncul bersama tanpa tanda kurung, urutan penerapan operator ditentukan oleh prioritas operator. Contoh menunjukkan bahwa perkalian dilakukan sebelum penjumlahan. Operator / memiliki prioritas yang sama dengan *. Begitu pula dengan + dan -. Ketika beberapa operator dengan prioritas yang sama muncul bersebelahan, seperti pada 1 - 2 + 1, mereka diterapkan dari kiri ke kanan: (1 - 2) + 1.

Aturan prioritas ini bukan sesuatu yang harus Anda khawatirkan. Ketika ragu, cukup tambahkan tanda kurung.

Ada satu operator aritmatika lagi, yang mungkin tidak langsung Anda kenali. Simbol % digunakan untuk mewakili operasi sisa bagi. X % Y adalah sisa dari membagi X dengan Y. Misalnya, 314 % 100 menghasilkan 14, dan 144 % 12 memberikan 0. Prioritas operator sisa bagi sama dengan perkalian dan pembagian. Anda juga sering melihat operator ini disebut sebagai modulo.

## Angka-angka Spesial

Ada tiga nilai spesial dalam JavaScript yang dianggap sebagai angka tetapi tidak berperilaku seperti angka biasa.

Dua yang pertama adalah Infinity dan -Infinity, yang mewakili tak terhingga positif dan negatif. Infinity - 1 masih tetap Infinity, dan seterusnya. Namun, jangan terlalu bergantung pada komputasi tak terhingga. Ini tidak matematis secara benar, dan akan segera membawa pada angka spesial berikutnya: NaN.

NaN berarti "bukan angka", meskipun itu adalah nilai dari jenis angka. Anda akan mendapatkan hasil ini ketika Anda, misalnya, mencoba menghitung 0 / 0 (nol dibagi nol), Infinity - Infinity, atau beberapa operasi numerik lainnya yang tidak menghasilkan hasil yang bermakna.

## String
Jenis data dasar selanjutnya adalah string. String digunakan untuk merepresentasikan teks. String ditulis dengan mengapit isinya dengan tanda kutip.

```js
`Down on the sea`
"Lie on the ocean"
'Float on the ocean'
```

Anda dapat menggunakan tanda kutip tunggal, tanda kutip ganda, atau backticks untuk menandai string, selama tanda kutip pada awal dan akhir string cocok.

Hampir semua hal dapat dimasukkan ke dalam tanda kutip, dan JavaScript akan membuat nilai string darinya. Namun, beberapa karakter lebih sulit. Anda dapat membayangkan bagaimana menempatkan tanda kutip di antara tanda kutip mungkin sulit. Baris baru (karakter yang muncul ketika Anda menekan enter) dapat dimasukkan tanpa melarikan diri hanya ketika string dikutip dengan backtick (\`).

Untuk memungkinkan karakter-karakter tersebut dimasukkan ke dalam string, notasi berikut digunakan: setiap kali backslash () ditemukan di dalam teks yang dikutip, itu menunjukkan bahwa karakter setelahnya memiliki arti khusus. Ini disebut menghindari karakter tersebut. Kutipan yang mendahului backslash tidak akan mengakhiri string tetapi menjadi bagian darinya. Ketika karakter n muncul setelah backslash, itu diinterpretasikan sebagai baris baru. Demikian pula, t setelah backslash berarti karakter tab.

Ambil string berikut:

```js
"This is the first line\nAnd this is the second"
```

Teks sebenarnya yang terkandung adalah ini:

```js
Ini adalah baris pertama
Dan ini adalah baris kedua
```

Tentu saja, ada situasi di mana Anda ingin backslash dalam string hanya menjadi backslash, bukan kode khusus. Jika dua backslash mengikuti satu sama lain, mereka akan bergabung bersama, dan hanya satu yang akan tersisa dalam nilai string yang dihasilkan. Inilah bagaimana string "Karakter baris baru ditulis seperti "\n"." dapat diungkapkan:

```js
"Karakter baris baru ditulis seperti \"\\n\"."
```

String juga harus dimodelkan sebagai serangkaian bit agar dapat ada di dalam komputer. Cara JavaScript melakukannya didasarkan pada standar Unicode. Standar ini menetapkan nomor untuk hampir setiap karakter yang Anda butuhkan, termasuk karakter dari bahasa Yunani, Arab, Jepang, Armenia, dan sebagainya. Jika kita memiliki nomor untuk setiap karakter, sebuah string dapat dijelaskan oleh urutan nomor.

Dan itulah yang dilakukan oleh JavaScript. Tetapi ada satu masalah: representasi JavaScript menggunakan 16 bit per elemen string, yang dapat menggambarkan hingga 216 karakter yang berbeda. Tetapi Unicode menetapkan lebih banyak karakter dari itu — sekitar dua kali lipat, pada saat ini. Jadi beberapa karakter, seperti banyak emoji, membutuhkan dua "posisi karakter" dalam string JavaScript. Kami akan kembali ke hal ini di Bab 5.

String tidak bisa dibagi, dikalikan, atau dikurangi, namun operator + dapat digunakan pada string. Operator + pada string tidak menambah, tetapi menggabungkan atau menggabungkan dua string. Baris berikut akan menghasilkan string "gabungkan":

```js
"con" + "cat" + "e" + "nate"
```

Nilai string memiliki sejumlah fungsi terkait (metode) yang dapat digunakan untuk melakukan operasi lain pada mereka. Saya akan menjelaskan lebih lanjut tentang ini di Bab 4.

String yang ditulis dengan tanda kutip tunggal atau ganda berperilaku sangat mirip - satu-satunya perbedaan terletak pada jenis tanda kutip yang perlu Anda hindari di dalamnya. String yang dikutip dengan backtick, biasanya disebut sebagai template literal, dapat melakukan beberapa trik tambahan. Selain dapat membentang beberapa baris, mereka juga dapat menyisipkan nilai lain.

```js
`setengah dari 100 adalah ${100 / 2}`
```

Ketika Anda menulis sesuatu di dalam ${} pada template literal, hasilnya akan dihitung, dikonversi menjadi string, dan disertakan pada posisi tersebut. Contoh tersebut menghasilkan "_setengah dari 100 adalah 50_".


## Operator Unary

Tidak semua operator ditulis dalam bentuk simbol. Beberapa ditulis sebagai kata. Salah satu contohnya adalah operator typeof, yang menghasilkan nilai string yang menamai tipe nilai yang Anda berikan padanya.

```js
console.log(typeof 4.5)
// → number

console.log(typeof "x")
// → string
```
Kami akan menggunakan console.log dalam contoh kode untuk menunjukkan bahwa kami ingin melihat hasil dari mengevaluasi sesuatu. Lebih banyak tentang hal itu di bab berikutnya.

Operator lain yang ditunjukkan semuanya beroperasi pada dua nilai, tetapi typeof hanya membutuhkan satu. Operator yang menggunakan dua nilai disebut operator biner, sedangkan operator yang menggunakan satu nilai disebut operator uner. Operator minus dapat digunakan sebagai operator biner dan operator uner.

```js
console.log(- (10 - 2))
// → -8
```


## Nilai Boolean

Seringkali berguna untuk memiliki nilai yang membedakan antara dua kemungkinan saja, seperti "ya" dan "tidak" atau "hidup" dan "mati". Untuk tujuan ini, JavaScript memiliki tipe data Boolean, yang hanya memiliki dua nilai, true dan false, yang ditulis sebagai kata-kata tersebut.

Perbandingan
Berikut adalah salah satu cara untuk menghasilkan nilai Boolean:

```js
console.log(3 > 2)
// → true

console.log(3 < 2)
// → false
```


Tanda > dan < adalah simbol tradisional untuk "lebih besar dari" dan "kurang dari", masing-masing. Mereka adalah operator biner. Menerapkannya menghasilkan nilai Boolean yang menunjukkan apakah mereka benar dalam kasus ini.

String dapat dibandingkan dengan cara yang sama.

```js
console.log("Aardvark" < "Zoroaster")
// → true
```

Cara pengurutan string kira-kira berdasarkan urutan abjad tetapi tidak benar-benar seperti yang Anda harapkan dalam kamus: huruf kapital selalu "lebih kecil" daripada huruf kecil, sehingga "Z" < "a", dan karakter non-abjad (!, -, dan sebagainya) juga termasuk dalam pengurutan. Saat membandingkan string, JavaScript melewati karakter dari kiri ke kanan, membandingkan kode Unicode satu per satu.

Operator serupa lainnya adalah >= (lebih besar dari atau sama dengan), <= (kurang dari atau sama dengan), == (sama dengan), dan != (tidak sama dengan).

```js
console.log("Itchy" != "Scratchy")
// → true

console.log("Apple" == "Orange")
// → false
```

Hanya ada satu nilai dalam JavaScript yang tidak sama dengan dirinya sendiri, yaitu NaN (“bukan angka”).

```js
console.log(NaN == NaN)
// → false
```

NaN seharusnya menunjukkan hasil dari perhitungan yang tidak masuk akal, dan sebagai hasilnya, NaN tidak sama dengan hasil dari perhitungan yang tidak masuk akal lainnya.

## Operator logika

Ada beberapa operasi yang dapat diterapkan pada nilai Boolean itu sendiri. JavaScript mendukung tiga operator logika: dan, atau, dan tidak. Ini dapat digunakan untuk "berpikir" tentang Boolean.

Operator && mewakili logika dan. Ini adalah operator biner, dan hasilnya benar hanya jika kedua nilai yang diberikan kepadanya adalah benar.

```js
console.log(true && false)
// → false

console.log(true && true)
// → true
```

Operator || menunjukkan logika atau. Ini menghasilkan benar jika salah satu dari nilai yang diberikan kepadanya adalah benar.

```js
console.log(false || true)
// → true

console.log(false || false)
// → false
```

Tidak ditulis sebagai tanda seru (!). Ini adalah operator tunggal yang membalikkan nilai yang diberikan kepadanya - !true menghasilkan false, dan !false menghasilkan true.

Ketika mencampur operator Boolean ini dengan operator aritmatika dan lainnya, tidak selalu jelas kapan tanda kurung diperlukan. Pada praktiknya, biasanya Anda dapat mengetahui bahwa dari operator yang telah kita lihat sejauh ini, || memiliki prioritas terendah, kemudian datang &&, kemudian operator perbandingan (>, ==, dan sebagainya), dan kemudian yang lainnya. Urutan ini telah dipilih sehingga, dalam ekspresi yang tipikal seperti berikut, se sedikit mungkin tanda kurung yang diperlukan:

```js
1 + 1 == 2 && 10 * 10 > 50
```

Operator logika terakhir yang akan saya bahas tidak unary, bukan binary, tetapi ternary, beroperasi pada tiga nilai. Ini ditulis dengan tanda tanya dan titik dua, seperti ini:

```js
console.log(true ? 1 : 2);
// → 1

console.log(false ? 1 : 2);
// → 2
```

Ini disebut operator kondisional (atau kadang-kadang hanya operator ternary karena ini adalah satu-satunya operator semacam itu dalam bahasa). Nilai di sebelah kiri tanda tanya "memilih" nilai mana dari dua nilai lainnya yang akan keluar. Ketika benar, ia memilih nilai tengah, dan ketika salah, ia memilih nilai di sebelah kanan.


## Nilai kosong
Ada dua nilai khusus, ditulis null dan undefined, yang digunakan untuk menunjukkan ketiadaan nilai yang bermakna. Mereka sendiri adalah nilai, tetapi tidak membawa informasi.

Banyak operasi dalam bahasa yang tidak menghasilkan nilai yang bermakna (Anda akan melihat beberapa nanti) menghasilkan undefined hanya karena mereka harus menghasilkan beberapa nilai.

Perbedaan makna antara undefined dan null adalah suatu kebetulan dalam desain JavaScript, dan kebanyakan waktu itu tidak penting. Dalam kasus di mana Anda benar-benar harus memperhatikan nilai-nilai ini, saya sarankan untuk memperlakukan mereka sebagai saling dapat dipertukarkan.

## Konversi jenis otomatis
Di bagian Pengantar, saya menyebutkan bahwa JavaScript berusaha keras untuk menerima hampir setiap program yang Anda berikan, bahkan program yang melakukan hal-hal aneh. Hal ini ditunjukkan dengan baik oleh ekspresi berikut:

```js
console.log(8 * null)
// → 0
console.log("5" - 1)
// → 4
console.log("5" + 1)
// → 51
console.log("five" * 2)
// → NaN
console.log(false == 0)
// → true
```


Ketika operator diterapkan pada jenis nilai "salah", JavaScript akan diam-diam mengonversi nilai tersebut ke jenis yang diperlukan, menggunakan seperangkat aturan yang seringkali bukan yang Anda inginkan atau harapkan. Ini disebut coercion. Null pada ekspresi pertama menjadi 0, dan "5" pada ekspresi kedua menjadi 5 (dari string ke angka). Namun pada ekspresi ketiga, + mencoba penggabungan string sebelum penjumlahan numerik, sehingga angka 1 dikonversi menjadi "1" (dari angka ke string).

Ketika sesuatu yang tidak dapat dipetakan ke dalam sebuah angka dengan cara yang jelas (seperti "lima" atau tidak terdefinisi), diubah menjadi angka, maka nilai yang didapatkan adalah NaN. Operasi aritmatika pada NaN terus menghasilkan NaN, jadi jika Anda menemukan diri Anda mendapatkan nilai NaN pada tempat yang tidak terduga, carilah konversi tipe yang tidak disengaja.

Ketika membandingkan nilai dari tipe yang sama menggunakan ==, hasilnya mudah diprediksi: Anda seharusnya mendapatkan nilai true ketika kedua nilai tersebut sama, kecuali pada kasus NaN. Namun ketika tipe berbeda, JavaScript menggunakan seperangkat aturan yang rumit dan membingungkan untuk menentukan apa yang harus dilakukan. Pada kebanyakan kasus, ia hanya mencoba mengonversi satu dari nilai tersebut ke tipe nilai lainnya. Namun, ketika null atau undefined terjadi pada salah satu sisi operator, maka ia hanya menghasilkan true jika kedua sisi adalah null atau undefined.

```js
console.log(null == undefined);
// → true
console.log(null == 0);
// → false
```

Perilaku tersebut seringkali berguna. Ketika Anda ingin menguji apakah sebuah nilai memiliki nilai yang sebenarnya bukan null atau undefined, Anda dapat membandingkannya dengan null menggunakan operator == (atau !=).

Namun, bagaimana jika Anda ingin menguji apakah sesuatu merujuk pada nilai false secara tepat? Ekspresi seperti 0 == false dan "" == false juga bernilai true karena konversi tipe otomatis. Ketika Anda tidak ingin ada konversi tipe yang terjadi, terdapat dua operator tambahan: === dan !==. Yang pertama menguji apakah sebuah nilai sama persis dengan nilai lainnya, dan yang kedua menguji apakah nilai tersebut tidak sama persis. Sehingga "" === false bernilai false seperti yang diharapkan.

Saya menyarankan untuk menggunakan operator perbandingan tiga karakter secara defensif untuk mencegah konversi tipe yang tidak terduga. Namun, ketika Anda yakin bahwa tipe pada kedua sisi akan sama, tidak ada masalah dengan menggunakan operator yang lebih pendek.


## Pemendekan operator logika
Operator logika && dan || menangani nilai-nilai dari jenis yang berbeda dengan cara yang unik. Mereka akan mengonversi nilai di sisi kiri ke tipe Boolean untuk memutuskan apa yang harus dilakukan, tetapi tergantung pada operator dan hasil dari konversi itu, mereka akan mengembalikan nilai tangan-kiri asli atau nilai tangan-kanan.

Operator ||, misalnya, akan mengembalikan nilai di sebelah kiri ketika itu dapat dikonversi menjadi true dan akan mengembalikan nilai di sebelah kanan jika tidak. Ini memiliki efek yang diharapkan ketika nilai-nilai adalah Boolean dan melakukan sesuatu yang analog untuk nilai-nilai dari jenis lain.

```js
console.log(null || "user")
// → user

console.log("Agnes" || "user")
// → Agnes
```

Kita dapat menggunakan fungsi ini sebagai cara untuk kembali pada nilai default. Jika Anda memiliki nilai yang mungkin kosong, Anda dapat menempatkan || setelahnya dengan nilai pengganti. Jika nilai awal dapat dikonversi menjadi false, maka Anda akan mendapatkan nilai pengganti tersebut. Aturan untuk mengonversi string dan angka ke nilai Boolean menyatakan bahwa 0, NaN, dan string kosong ("") dianggap sebagai false, sementara semua nilai lain dianggap sebagai true. Jadi, 0 || -1 menghasilkan -1, dan "" || "!?" menghasilkan "!?".

Operator && bekerja dengan cara yang sama tetapi sebaliknya. Ketika nilai di sebelah kirinya adalah sesuatu yang dapat dikonversi menjadi false, ia mengembalikan nilai tersebut, dan jika tidak, ia mengembalikan nilai di sebelah kanannya.

Properti penting lain dari kedua operator ini adalah bagian di sebelah kanan hanya dievaluasi jika diperlukan. Dalam kasus true || X, tidak peduli X apa bahkan jika itu adalah bagian program yang mengerikan, hasilnya akan menjadi true, dan X tidak pernah dievaluasi. Hal yang sama berlaku untuk false && X, yang merupakan false dan akan mengabaikan X. Ini disebut evaluasi pemendekan.

Operator kondisional bekerja dengan cara yang sama. Dari nilai kedua dan ketiga, hanya yang terpilih yang dievaluasi.

## Ringkasan

Kita melihat empat jenis nilai JavaScript dalam bab ini: angka, string, Boolean, dan nilai yang tidak terdefinisi.

Nilai-nilai tersebut dibuat dengan mengetikkan nama (true, null) atau nilai (13, "abc"). Anda dapat menggabungkan dan mengubah nilai-nilai dengan operator. Kami melihat operator biner untuk aritmatika (+, -, *, /, dan%), penggabungan string (+), perbandingan (==, !=, ===, !==, <,>, <=,> =), dan logika (&&, ||), serta beberapa operator unary (- untuk membalikkan nomor, ! untuk membalikkan secara logis, dan typeof untuk menemukan tipe nilai) dan operator ternary (?:) untuk memilih satu dari dua nilai berdasarkan nilai ketiga.

Ini memberi Anda informasi yang cukup untuk menggunakan JavaScript sebagai kalkulator saku tetapi tidak banyak lagi. Bab berikutnya akan mulai mengikat ekspresi-ekspresi ini menjadi program dasar.

#Programming