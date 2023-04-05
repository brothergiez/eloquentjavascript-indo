# Chapter 0 Introduction

## Pengantar

> Kita berpikir bahwa kita menciptakan sistem untuk kepentingan kita sendiri. Kita percaya bahwa kita menciptakannya sesuai dengan citra kita sendiri ... Namun, komputer sebenarnya tidak seperti kita. Ini adalah proyeksi dari bagian yang sangat kecil dari diri kita: bagian yang didedikasikan untuk logika, keteraturan, aturan, dan kejelasan. 

_--Ellen Ullman, Close to the Machine: Technophilia and its Discontents_

![](i/images/chapter_picture_00.jpg)

Ini adalah buku tentang menginstruksikan komputer. Komputer sekarang sama umumnya seperti obeng, tetapi jauh lebih kompleks, dan membuat mereka melakukan apa yang Anda inginkan tidak selalu mudah.

Jika tugas yang Anda miliki untuk komputer Anda adalah tugas yang umum dan dipahami dengan baik, seperti menampilkan email atau bertindak sebagai kalkulator, Anda dapat membuka aplikasi yang sesuai dan mulai bekerja. Namun, untuk tugas yang unik atau terbuka, mungkin tidak ada aplikasi yang tersedia.

Di sinilah pemrograman dapat membantu. Pemrograman adalah tindakan membuat program - serangkaian instruksi yang tepat yang memberi tahu komputer apa yang harus dilakukan. Karena komputer adalah hewan yang bodoh dan pedantis, pemrograman pada dasarnya melelahkan dan menjengkelkan.

Untungnya, jika Anda dapat melewatkan kenyataan tersebut, dan mungkin bahkan menikmati ketegasan dalam berpikir dengan cara yang bisa dipahami oleh mesin bodoh, pemrograman dapat memberikan kepuasan. Ini memungkinkan Anda melakukan hal-hal dalam hitungan detik yang akan memakan waktu selamanya jika dilakukan secara manual. Ini adalah cara membuat alat komputer Anda melakukan hal-hal yang sebelumnya tidak dapat dilakukan. Dan ini memberikan latihan yang luar biasa dalam berpikir abstrak.

Sebagian besar pemrograman dilakukan dengan bahasa pemrograman. Bahasa pemrograman adalah bahasa buatan yang digunakan untuk menginstruksikan komputer. Menariknya, cara yang paling efektif yang kita temukan untuk berkomunikasi dengan komputer sangat terinspirasi dari cara kita berkomunikasi satu sama lain. Seperti bahasa manusia, bahasa komputer memungkinkan kata dan frasa digabungkan dengan cara baru, sehingga memungkinkan untuk mengekspresikan konsep yang baru.

Pada satu titik, antarmuka berbasis bahasa, seperti BASIC dan prompt DOS pada tahun 1980-an dan 1990-an, adalah metode utama berinteraksi dengan komputer. Mereka sebagian besar telah digantikan dengan antarmuka visual, yang lebih mudah dipelajari tetapi menawarkan kebebasan yang lebih sedikit. Bahasa pemrograman masih ada, jika Anda tahu di mana mencarinya. Salah satu bahasa tersebut, JavaScript, dibangun ke dalam setiap browser web modern dan oleh karena itu tersedia di hampir setiap perangkat.

Buku ini akan mencoba membuat Anda cukup terbiasa dengan bahasa ini untuk melakukan hal-hal yang berguna dan menyenangkan dengan itu.

## Tentang Pemrograman

Selain menjelaskan JavaScript, saya akan memperkenalkan prinsip dasar pemrograman. Ternyata, pemrograman itu sulit. Aturan dasarnya sederhana dan jelas, namun program yang dibangun di atas aturan ini cenderung menjadi kompleks sehingga memperkenalkan aturan dan kompleksitas mereka sendiri. Anda sedang membangun labirin Anda sendiri, dan mungkin saja Anda akan tersesat di dalamnya.

Akan ada saat-saat ketika membaca buku ini terasa sangat frustasi. Jika Anda baru belajar pemrograman, akan ada banyak materi baru yang harus dicerna. Sebagian besar materi ini kemudian digabungkan dengan cara yang membutuhkan Anda untuk membuat koneksi tambahan.

Sekarang terserah pada Anda untuk melakukan usaha yang diperlukan. Ketika Anda kesulitan mengikuti buku, jangan melompat pada kesimpulan tentang kemampuan Anda sendiri. Anda baik-baik saja - Anda hanya perlu terus melakukannya. Istirahat sejenak, baca ulang beberapa materi, dan pastikan Anda membaca dan memahami program contoh dan latihan. Belajar adalah pekerjaan keras, tetapi semua yang Anda pelajari adalah milik Anda dan akan membuat pembelajaran berikutnya lebih mudah.

> Ketika tindakan menjadi tidak menguntungkan, kumpulkan informasi; ketika informasi menjadi tidak menguntungkan, tidurlah. 

_-- Ursula K. Le Guin, The Left Hand of Darkness_

Sebuah program adalah banyak hal. Ini adalah potongan teks yang diketik oleh programmer, ia adalah kekuatan pengarah yang membuat komputer melakukan apa yang dilakukannya, ia adalah data dalam memori komputer, tetapi mengontrol tindakan yang dilakukan pada memori yang sama. Analogi yang mencoba membandingkan program dengan objek yang kita kenal cenderung gagal. Salah satu analogi yang sepadan adalah mesin - banyak bagian terpisah cenderung terlibat, dan untuk membuat semuanya berjalan, kita harus mempertimbangkan cara-cara di mana bagian-bagian ini saling terhubung dan berkontribusi terhadap operasi keseluruhan.

Komputer adalah mesin fisik yang bertindak sebagai tuan rumah untuk mesin tak berwujud ini. Komputer itu sendiri hanya dapat melakukan hal-hal yang sangat sederhana. Alasannya sangat bermanfaat adalah bahwa mereka melakukan hal-hal ini dengan kecepatan yang sangat tinggi. Sebuah program dapat dengan cerdik menggabungkan sejumlah besar tindakan sederhana ini untuk melakukan hal-hal yang sangat rumit.

Sebuah program adalah sebuah bangunan pemikiran. Gratis untuk dibangun, tanpa berat, dan mudah tumbuh di bawah tangan kita yang mengetik.

Namun, tanpa perawatan, ukuran dan kompleksitas program akan tumbuh tak terkendali, bahkan membingungkan orang yang membuatnya. Menjaga program tetap terkendali adalah masalah utama dalam pemrograman. Ketika program berhasil, itu sangat indah. Seni pemrograman adalah keterampilan mengendalikan kompleksitas. Program yang bagus harus terkendali, sederhana dalam kompleksitasnya.

Beberapa programmer percaya bahwa kompleksitas ini dapat diatur dengan baik dengan menggunakan hanya satu set kecil teknik yang dipahami dengan baik dalam program mereka. Mereka telah menyusun aturan ketat ("best practice") yang menentukan bentuk program yang harus mereka miliki dan mereka berada dalam wilayah aman mereka dengan hati-hati.

Ini tidak hanya membosankan, tapi juga tidak efektif. Masalah baru sering membutuhkan solusi baru. Bidang pemrograman masih muda dan berkembang dengan cepat, dan cukup beragam untuk memiliki ruang bagi pendekatan yang sangat berbeda. Ada banyak kesalahan yang mengerikan dalam desain program, dan Anda harus pergi dan membuatnya agar Anda memahaminya. Rasa bagaimana program yang baik terlihat dikembangkan dalam praktek, bukan dipelajari dari daftar aturan.

## Mengapa bahasa penting

Pada awalnya, saat lahirnya komputasi, tidak ada bahasa pemrograman. Program terlihat seperti ini:

```
00110001 00000000 00000000
00110001 00000001 00000001
00110011 00000001 00000010
01010001 00001011 00000010
00100010 00000010 00001000
01000011 00000001 00000000
01000001 00000001 00000001
00010000 00000010 00000000
01100010 00000000 00000000
```


Itu adalah program untuk menambahkan angka dari 1 hingga 10 dan mencetak hasilnya: 1 + 2 + ... + 10 = 55. Program tersebut dapat dijalankan pada mesin sederhana yang dibayangkan. Untuk memprogram komputer awal, perlu untuk menyetel array besar saklar dalam posisi yang tepat atau menembus lubang pada strip kartu dan memberikannya ke komputer. Anda mungkin bisa membayangkan seberapa menjengkelkannya dan berpotensi untuk kesalahan prosedur ini. Bahkan menulis program sederhana memerlukan banyak kecerdasan dan disiplin. Program yang kompleks hampir tidak dapat dibayangkan.

Tentu saja, memasukkan secara manual pola bit yang kuno ini (satu dan nol) memberikan perasaan mendalam bagi programmer sebagai penyihir yang perkasa. Dan itu harus bernilai sesuatu dalam hal kepuasan kerja.

Setiap baris program sebelumnya berisi satu instruksi. Ini bisa ditulis dalam bahasa Inggris seperti ini:

1. Simpan angka 0 di lokasi memori 0.
2. Simpan angka 1 di lokasi memori 1.
3. Simpan nilai dari lokasi memori 1 di lokasi memori 2.
4. Kurangi angka 11 dari nilai di lokasi memori 2.
5. Jika nilai di lokasi memori 2 adalah angka 0, lanjutkan pada instruksi 9.
6. Tambahkan nilai lokasi memori 1 ke lokasi memori 0.
7. Tambahkan angka 1 ke nilai lokasi memori 1.
8. Lanjutkan dengan instruksi 3.
9. Keluaran nilai dari lokasi memori 0.

Meskipun itu sudah lebih mudah dibaca daripada deretan bit, itu masih cukup samar. Menggunakan nama daripada angka untuk instruksi dan lokasi memori membantu.

```
 Set "total" to 0.
 Set "count" to 1.
[loop]
 Set "compare" to "count".
 Subtract 11 from "compare".
 If "compare" is zero, continue at [end].
 Add "count" to "total".
 Add 1 to "count".
 Continue at [loop].
[end]
 Output "total".
```

Apakah Anda dapat melihat bagaimana program ini bekerja pada saat ini? Dua baris pertama memberikan dua lokasi memori nilai awal: total akan digunakan untuk membangun hasil dari perhitungan, dan count akan melacak nomor yang sedang kita lihat saat ini. Baris yang menggunakan compare mungkin adalah yang paling aneh. Program ingin melihat apakah count sama dengan 11 untuk memutuskan apakah itu bisa berhenti berjalan. Karena mesin hipotetis kita cukup primitif, hanya dapat menguji apakah angka itu nol dan membuat keputusan berdasarkan nilai tersebut. Jadi ia menggunakan lokasi memori yang diberi label compare untuk menghitung nilai count - 11 dan membuat keputusan berdasarkan nilai tersebut. Dua baris berikutnya menambahkan nilai count ke hasil dan menambahkan count sebesar 1 setiap kali program telah memutuskan bahwa count belum mencapai 11.

Berikut ini adalah program yang sama yang ditulis menggunakan javascript:	

```
let total = 0, count = 1;
while (count <= 10) {
  total += count;
  count += 1;
}
console.log(total);
// → 55
```

Versi ini memberikan beberapa perbaikan. Yang paling penting, tidak perlu lagi menentukan cara kita ingin program melompat ke sana kemari. Konstruksi while akan menanganinya. Program akan terus mengeksekusi blok (yang dibungkus dalam kurung kurawal) di bawahnya selama kondisi yang diberikan masih berlaku. Kondisi tersebut adalah count <= 10, yang berarti "count kurang dari atau sama dengan 10". Kita tidak lagi perlu membuat nilai sementara dan membandingkannya dengan nol, yang hanya merupakan detail yang tidak menarik. Sebagian dari kekuatan bahasa pemrograman adalah bahwa mereka dapat menangani detail-detail yang tidak menarik bagi kita.

Pada akhir program, setelah konstruksi while selesai, operasi console.log digunakan untuk menuliskan hasil.

Akhirnya, inilah bagaimana program akan terlihat jika kita memiliki operasi range dan sum yang nyaman tersedia, yang masing-masing membuat kumpulan angka dalam rentang dan menghitung jumlah dari kumpulan angka: 

```
console.log(sum(range(1, 10)));
// → 55
```

Moral dari cerita ini adalah bahwa program yang sama dapat diekspresikan dalam cara yang panjang dan sulit dibaca atau cara yang singkat dan mudah dibaca. Versi pertama dari program tersebut sangat sulit dimengerti, sedangkan versi terakhir hampir seperti bahasa Inggris: mencatat jumlah dari rentang angka dari 1 hingga 10. (Kita akan melihat di bab-bab selanjutnya bagaimana cara mendefinisikan operasi seperti penjumlahan dan rentang.)

Bahasa pemrograman yang baik membantu programmer dengan memungkinkan mereka berbicara tentang tindakan yang harus dilakukan oleh komputer pada tingkat yang lebih tinggi. Ia membantu menghilangkan detail, memberikan blok-blok pembangunan yang nyaman (seperti while dan console.log), memungkinkan Anda untuk mendefinisikan blok pembangunan Anda sendiri (seperti sum dan range), dan membuat blok-blok tersebut mudah untuk disusun.

## Apa itu JavaScript?
JavaScript diperkenalkan pada tahun 1995 sebagai cara untuk menambahkan program ke halaman web pada browser Netscape Navigator. Bahasa ini kemudian diadopsi oleh semua browser web grafis utama lainnya. Ini membuat aplikasi web modern yang interaktif menjadi mungkin - aplikasi di mana Anda dapat berinteraksi langsung tanpa melakukan reload halaman untuk setiap tindakan. JavaScript juga digunakan di situs web yang lebih tradisional untuk menyediakan berbagai bentuk interaktivitas dan kecerdasan.

Penting untuk dicatat bahwa JavaScript hampir tidak memiliki hubungan dengan bahasa pemrograman bernama Java. Nama yang mirip ini terinspirasi dari pertimbangan pemasaran daripada keputusan yang baik. Saat JavaScript diperkenalkan, bahasa Java sedang dipasarkan dengan intens dan semakin populer. Seseorang berpikir bahwa ini adalah ide yang bagus untuk mencoba naik kapal pada keberhasilan ini. Sekarang kita terjebak dengan nama itu.

Setelah diadopsi di luar Netscape, dokumen standar ditulis untuk menjelaskan cara kerja bahasa JavaScript sehingga berbagai bagian perangkat lunak yang mengklaim mendukung JavaScript sebenarnya berbicara tentang bahasa yang sama. Ini disebut standar ECMAScript, setelah organisasi Ecma International yang melakukan standarisasi. Dalam praktiknya, istilah ECMAScript dan JavaScript dapat digunakan secara bergantian - mereka adalah dua nama untuk bahasa yang sama.

Ada orang yang akan mengatakan hal-hal mengerikan tentang JavaScript. Banyak dari hal-hal ini benar. Ketika saya diminta untuk menulis sesuatu dalam JavaScript untuk pertama kalinya, saya segera mulai membencinya. Ini akan menerima hampir apa saja yang saya ketik tetapi menafsirkannya dengan cara yang benar-benar berbeda dari apa yang saya maksudkan. Ini memiliki banyak hubungannya dengan fakta bahwa saya sama sekali tidak tahu apa yang saya lakukan, tentu saja, tetapi ada masalah nyata di sini: JavaScript sangat liberal dalam apa yang memungkinkannya. Ide di balik desain ini adalah membuat pemrograman di JavaScript lebih mudah untuk pemula. Pada kenyataannya, ini sebagian besar membuat menemukan masalah dalam program Anda lebih sulit karena sistem tidak akan menunjukkannya kepada Anda.

Namun, fleksibilitas ini juga memiliki kelebihan. Ini memberi ruang untuk banyak teknik yang tidak mungkin dilakukan dalam bahasa yang lebih kaku, dan seperti yang akan Anda lihat (misalnya di Bab 10), itu dapat digunakan untuk mengatasi beberapa kelemahan JavaScript. Setelah belajar bahasa tersebut dengan benar dan bekerja dengan itu selama beberapa waktu, saya belajar untuk menyukai JavaScript.

Telah ada beberapa versi JavaScript. ECMAScript versi 3 adalah versi yang banyak didukung pada saat JavaScript naik menjadi dominan, sekitar antara tahun 2000 dan 2010. Selama waktu ini, pekerjaan sedang berlangsung pada versi 4 yang ambisius, yang merencanakan sejumlah perbaikan dan perluasan radikal pada bahasa. Mengubah bahasa yang hidup dan banyak digunakan dengan cara yang radikal ternyata sulit secara politik, dan pekerjaan pada versi 4 ditinggalkan pada tahun 2008, sehingga menghasilkan versi 5 yang jauh lebih sedikit ambisius, yang hanya membuat beberapa perbaikan yang tidak kontroversial, yang keluar pada tahun 2009. Kemudian pada tahun 2015 versi 6 keluar, pembaruan utama yang mencakup beberapa ide yang direncanakan untuk versi 4. Sejak itu, kami telah memiliki pembaruan kecil baru setiap tahun.

Kenyataan bahwa bahasa tersebut terus berkembang berarti bahwa browser harus terus menjaga agar tetap terdepan, dan jika Anda menggunakan browser yang lebih lama, mungkin tidak mendukung setiap fitur. Desainer bahasa berhati-hati untuk tidak membuat perubahan apa pun yang dapat merusak program yang sudah ada, sehingga browser baru masih dapat menjalankan program lama. Dalam buku ini, saya menggunakan versi 2017 dari JavaScript.

Browser web bukanlah satu-satunya platform di mana JavaScript digunakan. Beberapa database, seperti MongoDB dan CouchDB, menggunakan JavaScript sebagai bahasa scripting dan kueri mereka. Beberapa platform untuk pemrograman desktop dan server, terutama proyek Node.js (subjek Bab 20), menyediakan lingkungan untuk pemrograman JavaScript di luar browser.

# Kode, dan Apa yang Dilakukan dengan Kode tersebut

Kode adalah teks yang membentuk program. Sebagian besar bab dalam buku ini mengandung banyak kode. Saya percaya membaca kode dan menulis kode adalah bagian yang tak terpisahkan dari pembelajaran pemrograman. Cobalah untuk tidak hanya sekedar melihat contohnya - baca dengan cermat dan pahami. Awalnya ini mungkin lambat dan membingungkan, tetapi saya berjanji bahwa Anda akan cepat terbiasa. Hal yang sama berlaku untuk latihan-latihan. Jangan mengira Anda mengerti sampai Anda benar-benar menulis solusi yang berfungsi.

Saya menyarankan Anda mencoba solusi untuk latihan-latihan dalam sebuah interpreter JavaScript yang sebenarnya. Dengan cara itu, Anda akan mendapatkan umpan balik langsung tentang apakah yang Anda lakukan berfungsi, dan, saya harap, Anda akan tergoda untuk bereksperimen dan mencoba hal-hal di luar latihan-latihan.

Ketika membaca buku ini di browser Anda, Anda dapat mengedit (dan menjalankan) semua program contoh dengan mengkliknya.

Jika Anda ingin menjalankan program-program yang didefinisikan dalam buku ini di luar situs web buku tersebut, beberapa kehati-hatian diperlukan. Banyak contoh berdiri sendiri dan seharusnya dapat bekerja di lingkungan JavaScript mana pun. Namun, kode di bab-bab selanjutnya sering ditulis untuk lingkungan tertentu (browser atau Node.js) dan hanya dapat dijalankan di sana. Selain itu, banyak bab yang menentukan program yang lebih besar, dan bagian kode yang muncul di dalamnya bergantung satu sama lain atau pada file eksternal. Sandbox di situs web menyediakan tautan ke file Zip yang berisi semua skrip dan file data yang diperlukan untuk menjalankan kode untuk bab tertentu.

## Ringkasan buku ini

Buku ini terdiri dari tiga bagian. Dua belas bab pertama membahas tentang bahasa pemrograman JavaScript. Tujuh bab berikutnya membahas tentang browser web dan cara JavaScript digunakan untuk memprogramnya. Terakhir, dua bab diperuntukkan untuk Node.js, lingkungan lain untuk memprogram JavaScript.

Selama buku ini, ada lima bab proyek, yang menjelaskan program contoh yang lebih besar untuk memberi Anda gambaran tentang pemrograman sebenarnya. Secara berurutan, kita akan membangun robot pengiriman, bahasa pemrograman, game platform, program cat piksel, dan situs web dinamis.

Bagian bahasa diawali dengan empat bab yang memperkenalkan struktur dasar bahasa JavaScript. Mereka memperkenalkan struktur kontrol (seperti kata while yang Anda lihat dalam pengenalan ini), fungsi (membuat blok bangunan sendiri), dan struktur data. Setelah itu, Anda dapat menulis program dasar. Selanjutnya, Bab 5 dan 6 memperkenalkan teknik untuk menggunakan fungsi dan objek untuk menulis kode yang lebih abstrak dan menjaga kompleksitas di bawah kendali.

Setelah bab proyek pertama, bagian bahasa buku dilanjutkan dengan bab tentang penanganan kesalahan dan perbaikan bug, ekspresi reguler (alat penting untuk bekerja dengan teks), modularitas (pertahanan lain terhadap kompleksitas), dan pemrograman asinkron (menangani peristiwa yang memakan waktu). Bab proyek kedua menutupi bagian pertama buku.

Bagian kedua, Bab 13 hingga 19, menjelaskan tentang alat yang dapat diakses oleh JavaScript pada browser. Anda akan belajar untuk menampilkan sesuatu di layar (Bab 14 dan 17), merespons masukan pengguna (Bab 15), dan berkomunikasi melalui jaringan (Bab 18). Ada lagi dua bab proyek dalam bagian ini.

Setelah itu, Bab 20 menjelaskan tentang Node.js, dan Bab 21 membangun situs web kecil menggunakan alat tersebut.

## Konvensi tipografi
Dalam buku ini, teks yang ditulis dengan huruf monospace akan mewakili elemen-elemen dari program - terkadang mereka adalah fragmen yang mandiri, dan terkadang mereka hanya merujuk pada bagian dari program yang terdekat. Program (yang sudah Anda lihat beberapa) ditulis sebagai berikut:

```
function factorial(n) {
	if (n == 0) {
		return 1;
	} else {
		return factorial(n - 1) * n;
	}
}
```


Kadang-kadang, untuk menunjukkan output yang dihasilkan oleh sebuah program, output yang diharapkan ditulis setelahnya, dengan dua garis miring dan tanda panah di depan.

```
console.log(factorial(8));
// → 40320
```


Semoga berhasil!

#Programming
