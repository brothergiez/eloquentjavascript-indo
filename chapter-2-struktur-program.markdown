# Chapter 2 Struktur Program

> Dan hatiku bersinar merah terang di bawah kulit yang tipis dan tembus cahaya dan mereka harus memberikan 10cc JavaScript agar aku kembali. (Aku merespons dengan baik racun di dalam darah.) Ya Tuhan, benda itu akan membuatmu terkesiap!

_--why, Panduan (Manis) tentang Ruby_

![alt Introduction](https://raw.githubusercontent.com/brothergiez/eloquentjavascript-indo/main/images/chapter_picture_2.jpg)

Pada bab ini, kita akan mulai melakukan hal-hal yang sebenarnya dapat disebut _pemrograman_. Kita akan memperluas pemahaman kita tentang bahasa JavaScript melampaui kata benda dan fragmen kalimat yang telah kita lihat sebelumnya, sehingga kita dapat mengekspresikan prosa yang bermakna.

## Expressions and statements

In Chapter 1, we made values and applied operators to them to get new values. Creating values like this is the main substance of any JavaScript program. But that substance has to be framed in a larger structure to be useful. So that’s what we’ll cover next.

A fragment of code that produces a value is called an expression. Every value that is written literally (such as 22 or "psychoanalysis") is an expression. An expression between parentheses is also an expression, as is a binary operator applied to two expressions or a unary operator applied to one.

This shows part of the beauty of a language-based interface. Expressions can contain other expressions in a way similar to how subsentences in human languages are nested—a subsentence can contain its own subsentences, and so on. This allows us to build expressions that describe arbitrarily complex computations.

If an expression corresponds to a sentence fragment, a JavaScript statement corresponds to a full sentence. A program is a list of statements.

The simplest kind of statement is an expression with a semicolon after it. This is a program:

```js
1;
!false;
```

It is a useless program, though. An expression can be content to just produce a value, which can then be used by the enclosing code. A statement stands on its own, so it amounts to something only if it affects the world. It could display something on the screen—that counts as changing the world—or it could change the internal state of the machine in a way that will affect the statements that come after it. These changes are called side effects. The statements in the previous example just produce the values 1 and true and then immediately throw them away. This leaves no impression on the world at all. When you run this program, nothing observable happens.

Dalam beberapa kasus, JavaScript memungkinkan Anda untuk menghilangkan tanda titik koma di akhir pernyataan. Namun, dalam beberapa kasus, tanda titik koma harus ada, jika tidak baris berikutnya akan dianggap sebagai bagian dari pernyataan yang sama. Aturan kapan tanda titik koma dapat dihilangkan dengan aman agak kompleks dan rentan terhadap kesalahan. Oleh karena itu, dalam buku ini, setiap pernyataan yang membutuhkan tanda titik koma akan selalu diberi satu. Saya menyarankan Anda untuk melakukan hal yang sama, setidaknya sampai Anda belajar lebih banyak tentang subtleties dari tanda titik koma yang hilang.

## Bindings
Bagaimana program menjaga keadaan internal? Bagaimana ia mengingat hal-hal? Kita telah melihat bagaimana menghasilkan nilai baru dari nilai lama, tetapi ini tidak mengubah nilai lama, dan nilai baru harus segera digunakan atau akan hilang lagi. Untuk menangkap dan menahan nilai, JavaScript menyediakan sesuatu yang disebut binding, atau variabel:

```js
let caught = 5 * 5;
```

Itu adalah jenis pernyataan kedua. Kata (keyword) khusus let menunjukkan bahwa kalimat ini akan mendefinisikan binding. Ini diikuti oleh nama binding dan, jika kita ingin segera memberinya nilai, oleh operator = dan ekspresi.

Pernyataan sebelumnya membuat binding yang disebut caught dan menggunakannya untuk menangkap angka yang dihasilkan dengan mengalikan 5 dengan 5.

Setelah sebuah binding telah didefinisikan, namanya dapat digunakan sebagai ekspresi. Nilai dari ekspresi seperti itu adalah nilai yang saat ini dipegang oleh binding. Berikut adalah contohnya:

```js
let ten = 10;
console.log(ten * ten);
// → 100
```

Ketika sebuah binding menunjuk pada sebuah nilai, itu tidak berarti binding tersebut terikat pada nilai itu selamanya. Operator = dapat digunakan kapan saja pada binding yang ada untuk memutuskan hubungan dengan nilai saat ini dan menunjukkannya pada nilai baru.

```js
let mood = "light";
console.log(mood);

// → light
mood = "dark";

console.log(mood);
// → dark
```

Mari bayangkan binding (ikatan) seperti tentakel, bukan kotak. Mereka tidak mengandung nilai; mereka memegangnya - dua binding dapat merujuk pada nilai yang sama. Program hanya dapat mengakses nilai yang masih memiliki referensi. Ketika Anda perlu mengingat sesuatu, Anda menumbuhkan tentakel untuk memegangnya atau melekatkan kembali salah satu tentakel yang sudah ada.

Mari kita lihat contoh lain. Untuk mengingat jumlah dolar yang masih harus dibayar oleh Luigi kepada Anda, Anda membuat sebuah binding. Kemudian ketika dia membayar $35, Anda memberikan binding ini sebuah nilai baru.

```js
let luigisDebt = 140;
luigisDebt = luigisDebt - 35;
console.log(luigisDebt);
// → 105
```

Ketika Anda mendefinisikan sebuah binding tanpa memberikan nilai, tentakel tidak memiliki apa-apa untuk digenggam, sehingga berakhir di udara. Jika Anda meminta nilai dari sebuah binding kosong, Anda akan mendapatkan nilai undefined.

Sebuah pernyataan let tunggal dapat mendefinisikan beberapa binding. Definisi harus dipisahkan oleh koma.

```js
let satu = 1, dua = 2;
console.log(satu + dua);
// → 3
```

Kata-kata var dan const juga dapat digunakan untuk membuat binding, dengan cara yang mirip dengan let.

```js
var nama = "Ayda";
const sapaan = "Halo ";
console.log(sapaan + nama);
// → Halo Ayda
```

Yang pertama, var (singkatan dari "variabel"), adalah cara binding dideklarasikan dalam JavaScript sebelum tahun 2015. Saya akan kembali ke cara tepat yang berbeda dari let di bab berikutnya. Untuk saat ini, ingat bahwa itu sebagian besar melakukan hal yang sama, tetapi kami jarang menggunakannya dalam buku ini karena memiliki beberapa sifat yang membingungkan.

Kata const singkatan dari konstan. Ini mendefinisikan binding konstan, yang menunjuk ke nilai yang sama selama ia hidup. Ini berguna untuk binding yang memberikan nama untuk sebuah nilai sehingga Anda dapat dengan mudah merujuknya nanti.

## Nama binding
Nama binding bisa berupa kata apa saja. Angka bisa menjadi bagian dari nama binding - catch22 adalah contoh nama yang valid - tetapi nama tersebut tidak boleh dimulai dengan angka. Nama binding dapat mencakup tanda dollar ($) atau garis bawah (_) tetapi tidak ada tanda baca atau karakter khusus lainnya.

Kata-kata dengan makna khusus, seperti let, adalah kata kunci, dan mereka tidak dapat digunakan sebagai nama binding. Ada juga sejumlah kata yang "direservasi untuk penggunaan" di versi JavaScript di masa depan, yang juga tidak dapat digunakan sebagai nama binding. Daftar lengkap kata kunci dan kata yang telah direservasi cukup panjang.

```
	break case catch class const continue debugger default
	delete do else enum export extends false finally for
	function if implements import interface in instanceof let
	new package private protected public return static super
	switch this throw true try typeof var void while with yield
```

Jangan khawatir tentang menghafal daftar ini. Ketika membuat sebuah binding menghasilkan kesalahan sintaks yang tidak terduga, lihat apakah Anda mencoba untuk mendefinisikan kata yang telah direservasi.

## Environment
Kumpulan pengikatan dan nilai yang ada pada suatu waktu disebut environment. Ketika sebuah program dimulai, lingkungan ini tidak kosong. Ia selalu berisi pengikatan yang merupakan bagian dari standar bahasa, dan sebagian besar waktu, ia juga memiliki pengikatan yang menyediakan cara untuk berinteraksi dengan sistem sekitarnya. Misalnya, pada browser, terdapat fungsi untuk berinteraksi dengan situs web yang sedang dimuat dan membaca masukan dari mouse dan keyboard.

## Fungsi
Banyak nilai yang disediakan dalam lingkungan default memiliki tipe fungsi. Fungsi adalah bagian program yang dibungkus dalam nilai. Nilai-nilai tersebut dapat diterapkan untuk menjalankan program yang dibungkus. Misalnya, pada lingkungan browser, pengikatan prompt memiliki fungsi yang menampilkan kotak dialog kecil yang meminta masukan dari pengguna. Ia digunakan seperti ini:

```js
prompt("Masukkan kode sandi");
```

![alt Introduction](https://raw.githubusercontent.com/brothergiez/eloquentjavascript-indo/main/images/prompt.png)

Menjalankan sebuah fungsi disebut memanggil atau menerapkannya. Anda dapat memanggil sebuah fungsi dengan menempatkan tanda kurung setelah ekspresi yang menghasilkan nilai fungsi. Biasanya, Anda akan langsung menggunakan nama pengikatan yang memiliki fungsi. Nilai di antara tanda kurung diberikan ke program dalam fungsi tersebut. Pada contoh di atas, fungsi prompt menggunakan string yang diberikan sebagai teks yang akan ditampilkan dalam kotak dialog. Nilai yang diberikan ke fungsi disebut argumen. Fungsi yang berbeda mungkin memerlukan jumlah atau tipe argumen yang berbeda.

Fungsi prompt tidak banyak digunakan dalam pemrograman web modern, terutama karena Anda tidak memiliki kontrol atas tampilan kotak dialog yang dihasilkan, tetapi dapat membantu dalam program percobaan dan eksperimen.

## Fungsi console.log
Dalam contoh-contoh tersebut, saya menggunakan console.log untuk mengeluarkan nilai. Kebanyakan sistem JavaScript (termasuk semua browser web modern dan Node.js) menyediakan fungsi console.log yang menuliskan argumennya ke perangkat output teks tertentu. Pada browser, keluarannya muncul di konsol JavaScript. Bagian antarmuka browser ini biasanya disembunyikan secara default, tetapi sebagian besar browser membukanya ketika Anda menekan F12 atau, pada Mac, perintah-opsi-I. Jika itu tidak berhasil, cari melalui menu untuk item yang bernama Alat Pengembang atau sejenisnya.

Ketika menjalankan contoh-contoh (atau kode Anda sendiri) pada halaman buku ini, output console.log akan ditampilkan setelah contoh, bukan di konsol JavaScript browser.

```js
let x = 30;
console.log("nilai x adalah", x);
// → nilai x adalah 30
```

Meskipun nama pengikatan tidak dapat mengandung karakter periode, console.log memiliki satu. Hal ini karena console.log bukanlah pengikatan sederhana. Ia sebenarnya merupakan ekspresi yang mengambil properti log dari nilai yang dipegang oleh pengikatan console. Kita akan mengetahui secara pasti apa artinya pada Bab 4.

Nilai pengembalian
Menampilkan kotak dialog atau menulis teks ke layar adalah efek samping. Banyak fungsi berguna karena efek samping yang dihasilkannya. Fungsi juga dapat menghasilkan nilai, dalam hal ini mereka tidak perlu memiliki efek samping untuk berguna. Misalnya, fungsi Math.max mengambil jumlah argumen angka dan mengembalikan angka terbesar.

```js
console.log(Math.max(2, 4));
// → 4
```

Ketika sebuah fungsi menghasilkan nilai, ia dikatakan mengembalikan nilai tersebut. Apa pun yang menghasilkan nilai adalah ekspresi dalam JavaScript, yang berarti pemanggilan fungsi dapat digunakan dalam ekspresi yang lebih besar. Di sini, panggilan ke Math.min, yang merupakan kebalikan dari Math.max, digunakan sebagai bagian dari ekspresi tambah:

```js
console.log(Math.min(2, 4) + 100);
// → 102
```

Bab berikutnya akan menjelaskan cara menulis fungsi Anda sendiri.

## Flow kontrol
Ketika program Anda mengandung lebih dari satu pernyataan, pernyataan-pernyataan tersebut dieksekusi seolah-olah mereka adalah sebuah cerita, dari atas ke bawah. Program contoh ini memiliki dua pernyataan. Pernyataan pertama meminta pengguna untuk memasukkan sebuah angka, dan pernyataan kedua, yang dieksekusi setelah pernyataan pertama, menampilkan hasil kuadrat dari angka tersebut.

```js
let theNumber = Number(prompt("Pilih sebuah angka"));
console.log("Angka Anda adalah akar kuadrat dari " +
theNumber * theNumber);
```

Fungsi Number mengonversi sebuah nilai menjadi angka. Kami membutuhkan konversi tersebut karena hasil dari prompt adalah sebuah nilai string, dan kami ingin menggunakannya sebagai angka. Ada juga fungsi serupa yang disebut String dan Boolean yang mengonversi nilai menjadi jenis-jenis tersebut.

Berikut adalah representasi skematik yang agak sepele dari aliran kontrol lurus:

![alt Introduction](https://raw.githubusercontent.com/brothergiez/eloquentjavascript-indo/main/images/controlflow-straight.svg)
## Eksekusi bersyarat
Tidak semua program adalah jalan lurus. Misalnya, kita mungkin ingin membuat jalan bercabang, di mana program mengambil cabang yang tepat berdasarkan situasi yang ada. Ini disebut eksekusi bersyarat.

![alt Introduction](https://raw.githubusercontent.com/brothergiez/eloquentjavascript-indo/main/images/controlflow-if.svg)

Eksekusi bersyarat dibuat dengan kata kunci if di JavaScript. Dalam kasus sederhana, kita ingin beberapa kode dieksekusi jika, dan hanya jika, kondisi tertentu terpenuhi. Misalnya, kita mungkin ingin menampilkan kuadrat dari input hanya jika input sebenarnya adalah angka.

```js
let theNumber = Number(prompt("Pilih sebuah angka"));
if (!Number.isNaN(theNumber)) {
	console.log("Angka Anda adalah akar kuadrat dari " +
	theNumber * theNumber);
}
```

Dengan modifikasi ini, jika Anda memasukkan "parrot", tidak ada output yang ditampilkan.

Kata kunci if mengeksekusi atau melewati sebuah pernyataan tergantung pada nilai dari ekspresi Boolean. Ekspresi yang menentukan ditulis setelah kata kunci, di antara tanda kurung, diikuti oleh pernyataan yang dieksekusi.

Fungsi Number.isNaN adalah fungsi JavaScript standar yang mengembalikan true hanya jika argumen yang diberikan adalah NaN. Fungsi Number sebenarnya mengembalikan NaN ketika Anda memberikannya sebuah string yang tidak mewakili angka yang valid. Oleh karena itu, kondisinya diterjemahkan menjadi "kecuali theNumber bukan bukan-angka, lakukan ini".

Pernyataan setelah if dibungkus dalam kurung kurawal ({ dan }) dalam contoh ini. Kurung kurawal dapat digunakan untuk mengelompokkan sejumlah pernyataan menjadi satu pernyataan tunggal, yang disebut blok. Anda juga dapat menghilangkannya dalam kasus ini, karena mereka hanya memegang satu pernyataan, tetapi untuk menghindari harus memikirkan apakah mereka dibutuhkan, sebagian besar programmer JavaScript menggunakannya dalam setiap pernyataan yang dibungkus seperti ini. Kami akan mengikuti konvensi itu sebagian besar dalam buku ini, kecuali untuk satu baris pernyataan sesekali.

```js
if (1 + 1 == 2) console.log("It's true");
// → It's true
```

Anda sering tidak hanya memiliki kode yang dieksekusi saat kondisi benar, tetapi juga kode yang menangani kasus lain. Jalur alternatif ini direpresentasikan oleh panah kedua dalam diagram. Anda dapat menggunakan kata kunci else, bersama dengan if, untuk membuat dua jalur eksekusi yang terpisah, alternatif.

```js
let theNumber = Number(prompt("Pick a number"));
if (!Number.isNaN(theNumber)) {
	console.log("Your number is the square root of " +
	theNumber * theNumber);
} else {
	console.log("Hey. Why didn't you give me a number?");
}
```

Jika Anda memiliki lebih dari dua jalur untuk dipilih, Anda dapat "mengaitkan" beberapa pasangan if / else bersama. Berikut contohnya:

let num = Number(prompt("Pick a number"));

```js
if (num < 10) {
	console.log("Small");
} else if (num < 100) {
	console.log("Medium");
} else {
	console.log("Large");
}
```

Program akan pertama-tama memeriksa apakah num kurang dari 10. Jika iya, maka akan memilih cabang itu, menampilkan "Small", dan selesai. Jika tidak, maka akan memilih cabang else, yang sendiri berisi if kedua. Jika kondisi kedua (<100) terpenuhi, itu berarti angka tersebut setidaknya 10 tetapi di bawah 100, dan "Medium" ditampilkan. Jika tidak, cabang else kedua dan terakhir dipilih.

Skema untuk program ini terlihat seperti ini:
![alt Introduction](https://raw.githubusercontent.com/brothergiez/eloquentjavascript-indo/main/images/controlflow-nested-if.svg)


## While dan do loops
Mempertimbangkan sebuah program yang mengeluarkan semua bilangan genap dari 0 hingga 12. Salah satu cara untuk menulis program ini adalah sebagai berikut:

```js
console.log(0);
console.log(2);
console.log(4);
console.log(6);
console.log(8);
console.log(10);
console.log(12);
```

Ini berfungsi, tetapi ide dari menulis sebuah program adalah untuk membuat sesuatu menjadi kurang pekerjaan, bukan lebih. Jika kita memerlukan semua bilangan genap kurang dari 1.000, pendekatan ini tidak praktis. Yang kita butuhkan adalah cara untuk menjalankan sebuah kode beberapa kali. Bentuk alur kontrol ini disebut loop.

![alt Introduction](https://raw.githubusercontent.com/brothergiez/eloquentjavascript-indo/main/images/controlflow-loop.svg)

Alur kontrol looping memungkinkan kita untuk kembali ke beberapa titik dalam program di mana kita sebelumnya dan mengulanginya dengan keadaan program saat ini. Jika kita menggabungkannya dengan pengikatan yang menghitung, kita dapat melakukan sesuatu seperti ini:

```js
let number = 0;
while (number <= 12) {
	console.log(number);
	number = number + 2;
}
// → 0
// → 2
// … dan seterusnya
```


Pernyataan yang dimulai dengan kata kunci while membuat sebuah loop. Kata while diikuti oleh ekspresi dalam tanda kurung dan kemudian sebuah pernyataan, seperti halnya dengan if. Loop terus memasuki pernyataan tersebut selama ekspresi menghasilkan nilai yang memberikan nilai true ketika dikonversi menjadi Boolean.

Pengikatan angka menunjukkan cara pengikatan dapat melacak kemajuan program. Setiap kali loop diulang, angka mendapatkan nilai yang 2 lebih besar dari nilai sebelumnya. Pada awal setiap pengulangan, dibandingkan dengan angka 12 untuk memutuskan apakah pekerjaan program sudah selesai.
Sebagai contoh yang benar-benar berguna, sekarang kita dapat menulis program yang menghitung dan menampilkan nilai dari 210 (2 pangkat 10). Kami menggunakan dua pengikatan: satu untuk melacak hasil kita dan satu untuk menghitung seberapa sering kita telah mengalikan hasil ini dengan 2. Loop menguji apakah pengikatan kedua telah mencapai 10 dan, jika tidak, memperbarui kedua pengikatan.

```js
let result = 1;
let counter = 0;
while (counter < 10) {
	result = result * 2;
	counter = counter + 1;
}

console.log(result);
// → 1024
```


Counter juga dapat dimulai dari 1 dan diperiksa untuk <= 10, tetapi karena alasan yang akan menjadi jelas di Bab 4, ide bagus untuk terbiasa menghitung mulai dari 0.

Do loop adalah struktur kontrol yang mirip dengan while loop. Ini hanya berbeda pada satu poin: do loop selalu menjalankan tubuhnya setidaknya satu kali, dan ia mulai menguji apakah harus berhenti hanya setelah eksekusi pertama. Untuk mencerminkan hal ini, pengujian muncul setelah tubuh loop.

```js
let yourName;
do {
	yourName = prompt("Siapa nama Anda?");
} while (!yourName);

console.log(yourName);
```

Program ini akan memaksa Anda memasukkan nama. Ia akan terus bertanya lagi dan lagi sampai mendapatkan sesuatu yang bukan string kosong. Menerapkan operator! akan mengonversi nilai ke tipe Boolean sebelum membalikkan, dan semua string kecuali "" mengonversi ke benar. Ini berarti loop terus berputar sampai Anda memberikan nama yang tidak kosong.

## Indenting Code
Pada contoh-contoh sebelumnya, saya menambahkan spasi di depan pernyataan yang merupakan bagian dari pernyataan yang lebih besar. Spasi ini tidak diperlukan - komputer akan menerima program dengan baik tanpa spasi. Bahkan, pemisahan baris dalam program juga opsional. Anda bisa menulis program sebagai satu baris panjang jika Anda mau.

Peran indentasi di dalam blok adalah untuk membuat struktur kode lebih terlihat. Pada kode di mana blok baru dibuka di dalam blok lain, dapat menjadi sulit untuk melihat di mana satu blok berakhir dan yang lain dimulai. Dengan indentasi yang tepat, bentuk visual program akan sesuai dengan bentuk blok di dalamnya. Saya suka menggunakan dua spasi untuk setiap blok terbuka, tetapi selera orang berbeda-beda - beberapa orang menggunakan empat spasi, dan beberapa orang menggunakan karakter tab. Yang penting adalah setiap blok baru menambahkan jumlah spasi yang sama.

```js
if (false != true) {
  console.log("That makes sense.");
  if (1 < 2) {
    console.log("No surprise there.");
  }
}
```

Sebagian besar program editor kode (termasuk yang ada di buku ini) akan membantu dengan secara otomatis memberikan indentasi pada baris baru dengan jumlah yang tepat.

## For loops

Banyak loop mengikuti pola yang ditunjukkan dalam contoh while. Pertama, pembuatan "binding counter" untuk melacak kemajuan loop. Kemudian diikuti dengan loop while, biasanya dengan ungkapan tes yang memeriksa apakah counter telah mencapai nilai akhirnya. Di akhir tubuh loop, counter diperbarui untuk melacak kemajuan.

Karena pola ini sangat umum, JavaScript dan bahasa yang serupa menyediakan bentuk yang sedikit lebih pendek dan lebih komprehensif, yaitu for loop.

```js
for (let number = 0; number <= 12; number = number + 2) {
	console.log(number);
}
// → 0
// → 2
// … dan seterusnya
```

Program ini sepenuhnya setara dengan contoh pencetakan bilangan genap sebelumnya. Satu-satunya perubahan adalah bahwa semua pernyataan yang terkait dengan "status" dari loop dikelompokkan bersama-sama setelah for.

Tanda kurung setelah kata kunci for harus berisi dua titik koma. Bagian sebelum titik koma pertama menginisialisasi loop, biasanya dengan mendefinisikan binding. Bagian kedua adalah ungkapan yang memeriksa apakah loop harus terus berlanjut. Bagian terakhir memperbarui status loop setelah setiap iterasi. Dalam kebanyakan kasus, ini lebih pendek dan lebih jelas daripada konstruksi while.

Ini adalah kode yang menghitung 210 menggunakan for alih-alih while:

```js
let result = 1;
for (let counter = 0; counter < 10; counter = counter + 1) {
	result = result * 2;
}

console.log(result);
// → 1024
```


## Keluar dari Loop

Menghasilkan false pada kondisi looping bukanlah satu-satunya cara sebuah loop bisa berakhir. Ada pernyataan khusus yang disebut break yang memiliki efek melompat langsung keluar dari loop yang mengelilinginya.

Program ini mengilustrasikan pernyataan break. Ini menemukan angka pertama yang lebih besar dari atau sama dengan 20 dan dapat dibagi dengan 7.

```js
for (let current = 20; ; current = current + 1) {
	if (current % 7 == 0) {
		console.log(current);
		break;
	}
}

// → 21
```

Menggunakan operator sisa (%) adalah cara mudah untuk menguji apakah sebuah angka dapat dibagi dengan angka lain. Jika dapat, sisa dari pembagiannya adalah nol.

Konstruk for pada contoh di atas tidak memiliki bagian yang memeriksa akhir dari loop. Ini berarti loop tidak akan pernah berhenti kecuali pernyataan break di dalamnya dieksekusi.

Jika Anda menghapus pernyataan break tersebut atau secara tidak sengaja menulis kondisi akhir yang selalu menghasilkan true, program Anda akan terjebak dalam loop tak terbatas. Program yang terjebak dalam loop tak terbatas tidak akan pernah selesai berjalan, yang biasanya merupakan hal yang buruk.

Jika Anda membuat loop tak terbatas dalam salah satu contoh di halaman ini, biasanya Anda akan diminta apakah Anda ingin menghentikan skrip setelah beberapa detik. Jika itu gagal, Anda harus menutup tab yang sedang Anda kerjakan, atau di beberapa browser menutup seluruh browser Anda, untuk memulihkan.

Kata kunci continue mirip dengan break, dalam hal ini mempengaruhi kemajuan loop. Ketika continue ditemukan dalam tubuh loop, kontrol melompat keluar dari tubuh dan melanjutkan dengan iterasi berikutnya dari loop.

## Memperbarui variabel dengan singkat

Terutama saat melooping, sebuah program sering perlu "memperbarui" variabel untuk menyimpan nilai berdasarkan nilai sebelumnya.

```js
counter = counter + 1;
```

JavaScript menyediakan pintasan untuk ini.

```js
counter += 1;
```

Pintasan serupa juga berlaku untuk banyak operator lain, seperti result *= 2 untuk menggandakan result atau counter -= 1 untuk menghitung mundur.

Ini memungkinkan kita untuk mempersingkat contoh penghitungan kita sedikit lebih banyak.

```js
for (let number = 0; number <= 12; number += 2) {
	console.log(number);
}
```

Untuk counter += 1 dan counter -= 1, ada yang lebih pendek: counter++ dan counter--.

## Dispatching pada sebuah nilai dengan switch

Tidak jarang kode terlihat seperti ini:

```js
if (x == "nilai1") aksi1();
else if (x == "nilai2") aksi2();
else if (x == "nilai3") aksi3();
else aksiDefault();
```

Ada sebuah konstruksi yang disebut switch yang dimaksudkan untuk mengekspresikan “dispatch” tersebut dengan cara yang lebih langsung. Sayangnya, sintaks JavaScript yang digunakan untuk ini (yang diwarisi dari bahasa pemrograman C/Java) agak canggung—rantai pernyataan if mungkin terlihat lebih baik. Berikut adalah contohnya:

```js
switch (prompt("Bagaimana cuacanya?")) {
	case "hujan":
		console.log("Jangan lupa bawa payung.");
		break;
	case "cerah":
		console.log("Pakai pakaian ringan.");
	case "berawan":
		console.log("Pergi ke luar.");
		break;
	default:
		console.log("Jenis cuaca tidak diketahui!");
		break;
}
```

Anda dapat menempatkan sejumlah label case di dalam blok yang dibuka oleh switch. Program akan mulai dieksekusi pada label yang sesuai dengan nilai yang diberikan pada switch, atau pada default jika tidak ada nilai yang cocok. Program akan terus dieksekusi, bahkan melintasi label-label lain, sampai mencapai pernyataan break. Dalam beberapa kasus, seperti kasus "cerah" dalam contoh tersebut, ini dapat digunakan untuk berbagi kode antara kasus (merekomendasikan pergi ke luar untuk cuaca cerah dan berawan). Tapi berhati-hatilah—mudah untuk lupa memasukkan break, yang akan menyebabkan program mengeksekusi kode yang tidak ingin Anda eksekusi.

## Kapitalisasi

Nama binding tidak boleh mengandung spasi, namun seringkali membantu untuk menggunakan beberapa kata agar dapat menjelaskan dengan jelas apa yang diwakili oleh binding tersebut. Berikut adalah pilihan Anda dalam menulis nama binding dengan beberapa kata di dalamnya:

```js
fuzzylittleturtle
fuzzy_little_turtle
FuzzyLittleTurtle
fuzzyLittleTurtle
```

Gaya pertama sulit dibaca. Saya lebih suka gaya garis bawah, meskipun gaya ini agak sulit untuk diketik. Fungsi standar JavaScript, dan sebagian besar programmer JavaScript, mengikuti gaya bawah – mereka mengkapitalisasi setiap kata kecuali yang pertama. Tidak sulit untuk terbiasa dengan hal-hal kecil seperti itu, dan kode dengan gaya penamaan campuran dapat terlihat tidak nyaman untuk dibaca, jadi kami mengikuti konvensi ini.

Dalam beberapa kasus, seperti pada fungsi Number, huruf pertama pada binding juga dikapitalisasi. Ini dilakukan untuk menandai fungsi ini sebagai konstruktor. Apa itu konstruktor akan menjadi jelas pada Bab 6. Saat ini, hal yang penting adalah jangan terganggu oleh kurangnya konsistensi yang tampak ini.

## Komentar

Seringkali, kode mentah tidak menyampaikan semua informasi yang ingin Anda sampaikan kepada pembaca manusia program, atau menyampaikannya dengan cara yang sulit dipahami sehingga orang mungkin tidak mengerti. Kadang-kadang, Anda mungkin hanya ingin menyertakan beberapa pemikiran terkait sebagai bagian dari program Anda. Itulah yang dimaksud dengan komentar.

Komentar adalah potongan teks yang merupakan bagian dari program tetapi sepenuhnya diabaikan oleh komputer. JavaScript memiliki dua cara menulis komentar. Untuk menulis komentar satu baris, Anda dapat menggunakan dua karakter garis miring (//) dan kemudian teks komentar setelahnya.

```js
let accountBalance = calculateBalance(account);
// komentar pertama

accountBalance.adjust();
// komentar kedua
let report = new Report();

// komentar ketiga
addToReport(accountBalance, report);

// salah satu bentuk untuk menulis komentar adalah seperti ini
```
Komentar // hanya berlangsung hingga akhir baris. Sebuah bagian teks antara /* dan */ akan diabaikan secara keseluruhan, terlepas dari apakah itu berisi pemecahan baris. Ini berguna untuk menambahkan blok informasi tentang file atau sebagian program.

```js
/*
	Pertama kali saya menemukan nomor ini tergores di belakang sebuah
	buku catatan tua. Sejak itu, ia sering muncul di nomor telepon dan
	nomor seri produk yang saya beli. Jelas ia suka saya, jadi saya
	memutuskan untuk menyimpannya.
*/
const myNumber = 11213;
```


## Ringkasan

Anda sekarang tahu bahwa program dibangun dari pernyataan, yang kadang-kadang sendiri berisi lebih banyak pernyataan. Pernyataan cenderung berisi ekspresi, yang sendiri dapat dibangun dari ekspresi yang lebih kecil.

Menempatkan pernyataan satu sama lain memberi Anda program yang dieksekusi dari atas ke bawah. Anda dapat memperkenalkan gangguan dalam alur kontrol dengan menggunakan pernyataan kondisional (if, else, dan switch) dan perulangan (while, do, dan for).

Binding dapat digunakan untuk menyimpan data di bawah nama, dan berguna untuk melacak status di program Anda. Lingkungan adalah kumpulan binding yang didefinisikan. Sistem JavaScript selalu menempatkan sejumlah binding standar yang berguna ke dalam lingkungan Anda.

Fungsi adalah nilai khusus yang mengemas bagian program. Anda dapat memanggilnya dengan menulis namaFungsi(argument1, argument2). Pemanggilan fungsi seperti itu adalah ekspresi dan dapat menghasilkan nilai.

## Latihan

Jika Anda tidak yakin bagaimana menguji solusi untuk latihan-latihan ini, lihatlah Pengantar.

Setiap latihan dimulai dengan deskripsi masalah. Baca deskripsi ini dan coba untuk menyelesaikan latihan tersebut. Jika Anda mengalami masalah, pertimbangkan untuk membaca petunjuk setelah latihan. Solusi lengkap untuk latihan-latihan tersebut tidak termasuk dalam buku ini, tetapi Anda dapat menemukannya secara online di https://eloquentjavascript.net/code. Jika Anda ingin belajar sesuatu dari latihan-latihan tersebut, saya sarankan untuk melihat solusinya hanya setelah Anda menyelesaikan latihan tersebut, atau setidaknya setelah Anda sudah cukup lama dan keras menyerangnya sehingga sedikit pusing.

#### Membuat Segitiga
Tulislah sebuah perulangan yang membuat tujuh panggilan console.log untuk menghasilkan segitiga berikut:

```
#
##
###
####
#####
######
#######
```

Mungkin berguna untuk mengetahui bahwa panjang sebuah string dapat ditemukan dengan menuliskan .length setelahnya.

```js
let abc = "abc";
console.log(abc.length);
// → 3
```

Kebanyakan latihan mengandung potongan kode yang dapat Anda modifikasi untuk menyelesaikan latihan tersebut. Ingatlah bahwa Anda dapat mengklik blok kode untuk mengeditnya.


###### Hints
###### Anda dapat memulai dengan program yang mencetak angka 1 hingga 7, yang dapat Anda turunkan dengan melakukan beberapa modifikasi pada contoh pencetakan bilangan genap yang diberikan sebelumnya dalam bab ini, di mana perulangan for diperkenalkan.

###### Sekarang pertimbangkan kesetaraan antara angka dan string karakter pagar. Anda dapat pergi dari 1 ke 2 dengan menambahkan 1 (+= 1). Anda dapat pergi dari "" ke "" dengan menambahkan karakter (+= ""). Dengan demikian, solusi Anda dapat mengikuti program pencetakan angka.

#### FizzBuzz
Tulis program yang menggunakan console.log untuk mencetak semua angka dari 1 hingga 100, dengan dua pengecualian. Untuk angka yang dapat dibagi habis dengan 3, cetak "Fizz" sebagai gantinya, dan untuk angka yang dapat dibagi habis dengan 5 (dan bukan dengan 3), cetak "Buzz" sebagai gantinya.

Setelah program berjalan, modifikasi program Anda agar mencetak "FizzBuzz" untuk angka yang dapat dibagi habis dengan 3 dan 5 (dan masih mencetak "Fizz" atau "Buzz" untuk angka yang hanya dapat dibagi habis dengan salah satu dari kedua bilangan tersebut).

(Sebenarnya, ini adalah pertanyaan wawancara yang diklaim dapat menyeleksi sebagian besar kandidat programmer. Jadi jika Anda berhasil menyelesaikannya, nilai pasar tenaga kerja Anda baru saja meningkat.)

###### Hints
###### Meninjau kembali angka-angkanya jelas merupakan pekerjaan pengulangan, dan memilih apa yang akan dicetak adalah masalah eksekusi kondisional. Ingat trik menggunakan operator sisa bagi (%) untuk memeriksa apakah suatu angka dapat dibagi habis oleh angka lain (memiliki sisa nol).

###### Pada versi pertama, ada tiga hasil yang mungkin untuk setiap angka, sehingga Anda harus membuat rantai if/else if/else.

###### Versi kedua dari program memiliki solusi yang mudah dan cerdas. Solusi sederhana adalah dengan menambahkan "cabang" kondisional lain untuk menguji kondisi yang diberikan dengan tepat. Untuk solusi cerdas, bangunlah sebuah string yang berisi kata atau kata-kata untuk dicetak dan cetaklah string ini atau angka jika tidak ada kata yang harus dicetak, dengan memanfaatkan operator ||.

