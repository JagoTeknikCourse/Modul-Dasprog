## Daftar Isi

- [IDE (Integrated Development Environment)](#ide)

- [Pengenalan Bahasa C](#pengenalan-bahasa-c)

    + [Statement](#statement)
    + [Program "Hello, world."](#program-hello-world)
    + [Struktur Program](#struktur-program)
    + [Komentar](#komentar)
    + [Input Dasar](#input-dasar)
    + [Output Dasar](#output-dasar)
    

- [Identifier](#identifier)

    + [Identifier](#identifier)
    + [Keyword](#keyword)

- [Variabel](#variabel)

    + [Pengenalan Variabel](#pengenalan-variabel)
    + [Deklarasi dan Definisi Variabel](#deklarasi-dan-definisi-variabel)
    + [Pengisian Nilai Variabel](#pengisian-nilai-variabel)
    + [Inisialisasi Variabel](#inisialisasi-variabel)

- [Konstanta dan Literal](#konstanta-dan-literal)

    + [Konstanta dan Literal](#konstanta-dan-literal-1)
    + [Mendefinisikan Konstanta](#mendefinisikan-konstanta)

- [Tipe Data Dasar](#tipe-data-dasar)

    + [Tipe Bilangan Bulat (integer)](#tipe-bilangan-bulat-integer)
    + [Tipe Bilangan Real (floating)](#tipe-bilangan-real-floating)
    + [Tipe Karakter](#tipe-karakter)
    

- [Operator Aritmatika](#operator-Aritmatika)

    + [Operator Assignment](#operator-assignment)
    + [Operator Aritmatika](#operator-aritmatika)
    + [Operator Increment dan Decrement](#operator-increment-dan-decrement) 

- [Operator Logika](#operator-Logika)

    + [Operator Perbandingan](#operator-perbandingan)
    + [Operator Logika](#operator-logika)
    + [Operator Bitwise](#operator-bitwise)
    
- [Operator Lain](#operator-lain)
    + [Operator Gabungan](#operator-gabungan)
    + [Operator Size-of](#operator-sizeof)
    + [Operator Address-of](#operator-Address-of)
    + [Operator Dereference](#operator-dereference)
    + [Operator Kondisional](#operator-kondisional)
    + [Operator Koma](#operator-koma)
    + [Operator Subsrcipt](#operator-subscript)

- [Soal Latihan](#latihan)
    + [Latihan 1](#latihan-1)
    + [Latihan 2](#latihan-2)
    + [Latihan 3](#latihan-3)


# IDE 
## (Integrated Development Environment)

Sebelum memulai menulis kode (atau *ngoding*), kita membutuhkan IDE untuk menyederhanakan proses pengkodean. Apa itu IDE? Sederhananya, IDE atau Intregated Development Environment adalah aplikasi editor kode yang menyertakan compiler. Berikut ini adalah aplikasi IDE bahasa C yang dapat digunakan.

- [CodeBlocks](http://www.codeblocks.org/downloads)

# Pengenalan Bahasa C

## Statement

Dalam suatu program, sebuah **statement** atau pernyataan adalah intruksi/perintah yang mempunyai makna tertentu sehingga menyebabkan program tersebut dapat melakukan suatu tindakan.

Analoginya, untuk berbicara kepada seseorang, kita menggunakan bahasa tertentu yang dapat dimengerti, sehingga kita dapat menyampaikan apa yang ingin disampaikan. Nah, seperti itulah statement. Apa yang kita sampaikan kepada orang lain layaknya statement pada program yang kita sampaikan kepada komputer.

## Program "Hello, world."

Mari kita mulai dengan membuat program sederhana, yakni program untuk menampilkan kalimat **“Hello, world!”** pada layar (konsol). Berikut adalah kode program tersebut.

```c
#include <stdio.h>  

int main()
{
    printf("Hello, world!\n");  
    return 0;  
}  
```

Salinlah kode di atas pada IDE, kemudian compile dan jalankan. Jika proses compilation berhasil, maka code akan menghasilkan output sebagai berikut.

```
Hello, world!
```

## Struktur Program

Untuk menjelaskan cara kerja program di atas, mari kita pisahkan bagian-bagian kode satu per satu.

### Header File

Baris 1 pada kode di atas disebut dengan preprocessor directive. Preprocessor yang digunakan dalam hal ini adalah `#include`.

Preprocessor `#include` menjelaskan bahwa program tersebut menyertakan **file header** `<stdio.h>`. File header  tersebut merupakan library bawaan C yang berisi fungsi-fungsi penting yang dibutuhkan oleh program, misalnya pada kasus ini, program membutuhkan fungsi `printf()` untuk mencetak kalimat **“Hello, world!”**. Tanpa adanya library, program tersebut tidak akan bisa di-compile.

### Fungsi `main()`

Fungsi `main()` pada kode tersebut ditunjukan pada baris ke 3 hingga baris ke 7.

```c
int main()
{
    printf("Hello, world!\n");  
    return 0;  
}
```

Dalam bahasa C, fungsi `main()` adalah fungsi utama yang harus ada. Hal ini dikarenakan eksekusi kode akan dimulai dari awal fungsi `main()`. 

+ Baris 3 menunjukkan nama dari fungsi dan tipe return dari fungsi tersebut. `int` merupakan tipe _return_ dari fungsi yang bernama `main()`. Kemudian terdapat tanda  `{` yang menandakan awal pembuka dari fungsi `main()`.
+ Baris 4 s.d 6 merupakan tubuh dari fungsi `main()`.
+ Baris 8 terdapat tanda `}` yang menandakan akhir dari fungsi `main()`. Pada dasarnya, tubuh dari sebuah fungsi berada di antara tanda `{ }`.

### Whitespace

Dapat diperhatikan pada kode bahwa baris 2 dan 4 kosong (tidak terdapat karakter apapun). Ini disebut dengan **whitespace**. Whitespace adalah area kosong pada kode, dan biasanya dtujukan agar kode mudah dibaca.

Terdapat tiga jenis whitespace, yakni **space**, **tab**, dan **new line**. Baris 2 dan 4 adalah contoh dari new line.

### Statement

Di dalam fungsi `main()`, terdapat dua **statement** yang ditunjukkan pada baris 5 dan 6. Seluruh statement yang ditulis pada bahasa c harus diakhiri oleh tanda titik-koma (`;`).

```c
printf("Hello, world!\n");  
return 0;  
```

Statement pada baris 5 menginstruksikan program untuk memanggil fungsi `printf()`. Fungsi `printf()` adalah fungsi yang tersedia dalam library header `<stdio.h>` dan digunakan untuk mencetak output pada konsol (layar). Dalam hal ini, fungsi `printf()` menerima argumen string bertuliskan **“Hello, world!\n”**. Tanda `‘\n’` dalam string tersebut merupakan karakter spesial yang berfungsi untuk mencetak new line.

Sedangkan statement pada baris 6 disebut dengan return statement. Perintah `return 0` pada fungsi `main()` digunakan untuk mengakhiri program dan menandakan program tersebut sukses dieksekusi.

## Komentar

**Komentar** (_comment_) adalah bagian dari program yang tidak akan dieksekusi. Komentar sangat berguna untuk mendeskripsikan program yang dibuat, misalnya saja untuk menjelaskan bagian dari kode agar mudah dipahami oleh programmer lainnya. Terdapat dua jenis komentar dalam bahasa C, yaitu komentar single-line dan multi-line.

### Komentar Single-Line

Seperti namanya, komentar single-line hanya bekerja pada satu baris. Komentar single-line diawali dengan simbol `//` . Semua karakter (pada satu baris) dibelakang simbol `//` akan diabaikan.

```c
// Ini adalah komentar single-line  
  
// Fungsi untuk mencetak ke layar  
printf("HALO\n");  

```

### Komentar Multi-Line

Sedangkan komentar multi-line dapat bekerja pada lebih dari satu baris. Pasangan simbol `/*` dan `*/` digunakan untuk membuat komentar multi-line. Semua karakter yang berada di antara dua simbol tersebut akan diabaikan.

```c
/* 
Ini adalah komentar multi-line 
Semua yang berada di sini akan 
diabaikan 
*/  
```
[< Kembali ke Daftar Isi](#daftar-isi)

# Input dan Output Dasar

Program yang kita buat dapat dijadikan program yang interaktif. Kita dapat menginstruksikannya untuk menerima input (dari keyboard) lalu menampilkan hasil output (pada konsol layar). Fungsi-fungsi yang berkaitan dengan input/output ada di dalam library `<stdio.h>` (standard input output).

## Input Dasar

### Fungsi `scanf()`

Umumnya kita melakukan input untuk menerima data/nilai dari user. Kemudian, data/nilai tersebut akan dimasukkan pada variabel yang akan diproses kemudian.
Untuk melakukan input dari keyboard fungsi yang digunakan adalah fungsi `scanf()`. Parameter dari fungsi `scanf()` sama persis dengan fungsi `printf()`. Kita menggunakan format specifier untuk menentukan jenis tipe data yang kita input, kemudian nilai input tersebut akan di-assign pada variabel.

Contoh:

Program di bawah menerima input berupa bilangan bulat yang disimpan pada variabel n, kemudian mencetak nilai variabel n dengan format _“n mempunyai nilai = n”_.

```c
#include <stdio.h>  
  
int main()   
{  
    int n;  
    scanf("%d", &n);  
    printf("n mempunyai nilai = %d", n);  
    return 0;  
} 
```

Input

```
3
```

Output

```
n mempunyai nilai = 3
```

## Output Dasar

### Fungsi `printf()`

Untuk mencetak output pada konsol, fungsi yang digunakan adalah fungsi `printf()`. Seperti yang sudah kita ketahui sebelumnya, fungsi `printf()` dapat menerima string sebagai argumen.

```c
#include <stdio.h>  
  
int main()   
{  
    printf("Ini adalah sebuah string\n");  
    return 0;  
} 
```

Output

```
Ini adalah sebuah string
```

Kita juga dapat menambahkan escape sequence pada string. Escape Sequence adalah urutan karakter yang digunakan untuk memformat output dan tidak ditampilkan ketika dicetak ke layar. Setiap karakter mempunyai fungsi tertentu. lihatlah tabel escape sequence berikut dan cobalah untuk menggunakan nya!
![cek tabel escape sequence](https://github.com/JagoTeknikCourse/Modul-Dasprog/blob/main/img/escape-sequence.md)
Mari kita ubah statement `printf()` di atas menjadi:

```c
printf("Ini adalah  string\nAku adalah new-line\n\tAku adalah karakter \\tab");
```  
 
```
Ini adalah sebuah string
Aku adalah new-line
    Aku adalah karakter \tab
```

Memisahkan dua statement `printf()` pada baris berbeda bukan berarti mencetak pada baris berbeda juga.

```c
#include <stdio.h>  
  
int main()   
{  
    printf("Sayang sekali");  
    printf("Aku tidak akan berpindah baris");  
    return 0;  
}  
```

Output

```
Sayang sekali Aku tidak akan berpindah baris
```

Potongan-potongan kode di atas adalah contoh untuk mencetak string tetap. Lalu bagaimana jika kita ingin mencetak string bersama dengan nilai dari suatu variabel?


### Output Dengan Format Specifier

Untuk mencetak nilai dari suatu variabel, kita perlu menambahkan argumen pada fungsi `printf()`. Argumen pertama pada fungsi `printf()` selalu berupa string. Kita dapat memasukkan variabel/nilai pada argumen ke-2, 3, 4 dan seterusnya sesuai kebutuhan.
Ingat, pada chapter [Tipe Data Dasar](#tipe-data-dasar), **setiap tipe data mempunyai format specifier masing-masing**. Nah, format specifier inilah yang akan kita gunakan untuk mencetak nilai dari suatu variabel.
 
```
printf(“<format string>”, var1, var2, var3, ... dst);
```

Misalnya saja, kita mempunyai dua variabel bertipe int dan char yakni `a = 2` dan `b = ‘X’`. Kita hendak mencetak nilai dari a dan b dipisahkan oleh spasi, maka programnya seperti:   

```c
#include <stdio.h>  
  
int main()   
{  
    int  a = 2;  
    char b = 'X';  
    printf("%d %c", a, b);  
    return 0;  
}
```

Output

```
2 X
```
 
Perhatikan ilustrasi di bawah.
 
![cek contoh printf](https://github.com/JagoTeknikCourse/Modul-Dasprog/blob/main/img/printf.md)

Dengan menyertakan format specifier dari tipe data yang bersesuaian, kita dapat mencetak nilai dari variabel tersebut. 
+ Fungsi `printf()` di atas mencetak string dengan nilai dua variabel (dua format specifier yang dipisahkan spasi).
+ Format specifier pertama adalah format specifier tipe data int dan akan merujuk pada variabel pertama yang dimasukkan, yakni a.
+ Format specifier kedua adalah format specifier tipe data char dan akan merujuk pada variabel kedua, yakni b.
+ Dan begitu seterusnya, satu format specifier untuk satu variabel berurutan.
Dengan begitu, kita dapat menyertakan format specifier bersamaan dengan string.

```c
printf("Nilai dari a = %d, dan b = '%c'", a, b);    
```

```
Nilai dari a = 2, dan b = ‘X’
```
[< Kembali ke Daftar Isi](#daftar-isi)

# Identifier dan Keyword

## Identifier
**Identifier** merujuk kepada penamaan sebuah entitas, seperti pada [variabel](#variabel), fungsi, structures dan lain-lain. Karena identifier menamai sebuah entitas, maka nama dari identifier harus unik (dua entitas tidak boleh mempunyai nama identifier yang sama).

Aturan penamaan identifier:

+ Identifier bukan merupakan [keyword](#keyword).
+ Identifier hanya boleh terdiri dari huruf lowercase, huruf uppercase, digit, dan simbol underscore ( _ ).
+ Identifier tidak boleh mengandung whitespace.
+ Identifier harus dimulai dengan huruf atau simbol underscore. Tidak boleh dimulai dengan digit/angka.
+ Bersifat case-sensitive, artinya identifier `variable` berbeda dengan `vAriaBle`.

## Keyword

**Keyword** merupakan kata khusus yang telah dipesan (reserved) pada bahasa pemograman. Kata-kata khusus tersebut mempunyai makna tersendiri bagi compiler, dan kata-kata tersebut merupakan bagian dari sintaks dan tidak dapat digunakan sebagai identifier.
Berikut adalah daftar keyword pada bahasa C.

|                 |             |             |             |
|-----------------|:------------|:------------|:------------|
| `auto`          | `double`    | `int`       | `struct`    |
| `break`         | `else`      | `long`      | `switch`    |
| `case`          | `enum`      | `register`  | `typedef`   |
| `char`          | `extern`    | `return`    | `union`     |
| `continue`      | `for`       | `signed`    | `void`      |
| `do`            | `if`        | `static`    | `while`     |
| `default`       | `goto`      | `sizeof`    | `volatile`  |
| `const`         | `float`     | `short`     | `unsigned`  |

[< Kembali ke Daftar Isi](#daftar-isi)

# Variabel

## Pengenalan Variabel

**Variabel** adalah suatu tempat yang digunakan untuk menampung data atau nilai pada memori yang mempunyai nilai yang dapat berubah–ubah selama proses penulisan program. Dalam bahasa C, variabel menyimpan data/nilai dengan tipe data tertentu, seperti menyimpan suatu angka yang termasuk bilangan bulat (integer) atau menyimpan suatu kata yang termasuk string.

Variabel dapat dianalogikan sebagai sebuah gelas. Gelas dalam hal ini disebut sebagai **variabel**. Pada umumnya, gelas digunakan untuk menampung cairan. Dalam hal ini cairan adalah **tipe datanya**. Kemudian, contoh dari cairan adalah air, yakni dalam hal ini **data** yang akan disimpan oleh gelas.

Pada dasarnya program bekerja dengan mengolah data-data. Data-data inilah yang kemudian disimpan pada variabel.

## Deklarasi Variabel

Pada bahasa C, variabel harus dideklarasikan terlebih dahulu sebelum bisa digunakan. Seperti halnya gelas tadi, gelas tersebut harus ada terlebih dahulu sebelum bisa digunakan.

Untuk mendeklarasikan sebuah variabel, sintaksnya adalah sebagai berikut.

```
<tipe_data> <identifier>
```

Misalkan, potongan kode berikut mendeklarasikan variabel `x` yang bertipe `int`.

```c
int x
```

Jika ingin mendeklarasikan lebih dari satu variabel dengan tipe yang sama, bisa menggunakan operator koma (`,`).

```
<tipe_data> <variabel1>, <variabel2>, ... dst;
```

```c
int x, y;
```

## Definisi Variabel (pengisian nilai pada variabel)

Setelah dideklarasikan, variabel dapat didefinisikan (diisi oleh sebuah nilai). Untuk melakukannya, gunakan operator assignment (simbol `=`).

```
identifier_variabel = <nilai yang bersesuaian>
```

Contoh:

```c
int x, y;  
x = 10;  
y = -2; 
```

Dalam hal ini, variabel `x` dan `y` akan mempunyai nilai masing-masing `10` dan `-2`.

## Inisialisasi Variabel

Deklarasi dan definisi variabel dapat dilakukan dalam satu instruksi sekaligus. Hal ini disebut dengan **inisialisasi**. Dengan melakukan inisialisasi variabel, berarti kita memberikan nilai awal pada variabel tersebut.

```
tipe_data identifier_variabel = <nilai yang bersesuaian>;
```

Contoh:

```c
int x = 10;
```
[< Kembali ke Daftar Isi](#daftar-isi)

# Konstanta dan Literal

## Konstanta dan Literal

Istilah konstanta merujuk pada suatu nilai tetap, tidak dapat berubah/diubah bahkan oleh program itu sendiri. Literal adalah konstanta yang nilainya kita tulis secara eksplisit pada kode. Contohnya:

```c
5       // Literal bilangan bulat  
1.23    // Literal bilangan real  
'S'     // Literal karakter  
"Hai"   // Literal string  
```

Berikut adalah jenis-jenis literal dalam bahasa C.

| Jenis Literal             | Contoh                        | Tipe Default  |
|---------------------------|:------------------------------|:--------------|
| Bilangan bulat            | `10, 0, -1 dll.`              | int           |
| Bilangan real (floating)  | `202.15, 33.24, -12.45 dll.`  | double        |
| Karakter                  | `‘A’, ‘1’, ‘#’`               | char          |
| String                    | `“Hai”`                       | const char[4] |

### Bilangan Bulat

Terdapat tiga cara untuk menuliskan literal bilangan bulat. Yakni menggunakan basis 10 (desimal), basis 8 (oktal) dan basis 16 (heksadesimal).
+ **Desimal** - ditulis seperti bilangan pada umumnya. Contohnya `100, -22`.
+ **Oktal** - diawali dengan angka “0”, kemudian diikuti bilangan oktal. Contohnya `077, 033`.
+ **Heksadesimal** - diawali dengan “0x”, kemudian diikuti bilangan heksadesimal. Contohnya `0x7f, 0x521`.

### Bilangan Real (floating)

Bilangan real (floating) dituliskan dengan menggunakan pemisah tanda titik (.) antara bilangan bulat dan bilangan pecahannya. Contohnya `2.321, -11.22, 0.00012`.

### Karakter

Literal karakter dituliskan dengan mengapitnya menggunakan tanda petik. Misalnya karakter A ditulis ‘A’. Selain karakter normal, terdapat karakter khusus dalam bahasa C yang mempunyai fungsi-fungsi khusus atau karakter yang tidak bisa begitu saja dituliskan dengan bentuk aslinya. Misalnya, “new line” direpresentasikan dengan ‘\n’, simbol backslash direpresentasikan dengan ‘\\’. Karakter-karakter tersebut disebut dengan escape sequence. Berikut adalah escape sequence yang terdapat dalam bahasa C.

![cek tabel escape sequence](https://github.com/JagoTeknikCourse/Modul-Dasprog/blob/main/img/escape-sequence.md)


### String

String adalah kumpulan dari satu karakter atau lebih. Literal string diapit oleh tanda kutip. Misalnya, `“Hello, world.”`. Representasi string dalam bahasa C menggunakan array bertipe `char`. Kita akan mempelajarinya di bagian selanjutnya.

## Mendefinisikan Konstanta

Untuk mendefinisikan konstanta, dapat dilakukan dengan cara-cara seperti berikut.

### Mendefinisikan Variabel Konstan

Variabel juga dapat dibuat konstan nilainya agar tidak dapat berubah/diubah selama program berjalan. Variabel konstan dibuat dengan menambahkan keyword `const` saat pendefinisian variabel.
 
```c
const tipe_data nama_var = <nilai yang bersesuaian>
```

Perlu diperhatikan bahwa definisi variabel konstan harus disertai inisialisasinya.
Contoh:

```c
const int    konstInt = 23;  
const double konstDouble = 23.12;
```

Segala bentuk perubahan yang dilakukan terhadap variabel konstan akan menghasilkan error.

```c
const int konstInt = 23;  
konsInt = 11; // Error
```

### Menggunakan #define

Cara lainnya adalah menggunakan prepocessor directive `#define`. Sintaksnya adalah sebagai berikut.
 
```
#define nama <nilai yang bersesuaian>
```

Contoh:
```c
#define konstInt    23  
#define konstDouble 23.11  
  
int main()  
{  
    int    a = konstInt;  
    double b = konstDouble;  
}  
```
[< Kembali ke Daftar Isi](#daftar-isi)

# Tipe Data Dasar

Secara sederhana **tipe data** adalah jenis data dan ukuran data yang akan ditampung dan oleh **variabel** (atau objek secara umum). Tipe data menentukan tipe dan jenis data seperti apa yang akan dimiliki oleh suatu variabel.

Dalam bahasa C terdapat beberapa jenis tipe data. Di antaranya adalah tipe data dasar, tipe data turunan, dan void. Untuk kali ini kita akan berfokus pada tipe data dasar.

## Tipe Bilangan Bulat (integer)

Bilangan Bulat adalah bilangan yang tidak mempunyai nilai pecahan (real). Tipe data bilangan bulat pada bahasa C diantaranya sebagai berikut.
![cek tabel tipe bilangan bulat](https://github.com/JagoTeknikCourse/Modul-Dasprog/blob/main/img/tipe-data-bulat.md)

Seperti namanya, tipe-tipe data di atas adalah tipe data yang digunakan untuk merepresentasikan bilangan bulat (positif dan negatif) dan bilangan 0. Misalnya, 0, -5, 12, -1, 200 dsb. **Perlu ditekankan** bahwa tipe-tipe data di atas tidak dapat digunakan untuk merepresentasikan bilangan floating-point (bilangan real).

Jika diperhatikan, terdapat dua jenis tipe data antara lain **signed** dan **unsigned**. Lalu apa perbedaan dari kedua jenis tersebut? Perbedaannya adalah terletak pada kemampuan untuk menampung bilangan negatif. **signed** dapat menampung bilangan negatif, sedangkan **unsigned** tidak.

## Tipe Bilangan Real (floating)

Bilangan Real atau floating-point adalah bilangan yang mempunyai nilai pecahan (real). Tipe data bilangan real pada bahasa C di antaranya adalah sebagai berikut.
![cek tabel tipe bilangan real (floating)](https://github.com/JagoTeknikCourse/Modul-Dasprog/blob/main/img/tipe-data-real.md)

Tipe data di atas digunakan untuk menyimpan data berupa bilangan real (floating-point)/bilangan berkoma. Misalnya, `2.35, -12.246, 0.005` dsb.

## Tipe Karakter

Karakter dalam bahasa C sebenarnya adalah bilangan bulat. Setiap karakter mempunyai kode tersendiri yang disebut dengan ASCII dan kode tersebut dapat direpresentasikan sebagai sebuah bilangan bulat.
![cek tabel tipe karakter](https://github.com/JagoTeknikCourse/Modul-Dasprog/blob/main/img/tipe-data-karakter.md)

Penggunaan paling umum dari tipe data di atas adalah untuk merepresentasikan satu karakter. Misalnya, `‘A’`, `‘-‘`, dan sebagainya.

[< Kembali ke Daftar Isi](#daftar-isi)

# Operator Aritmatika

## Operator Assignment

**Operator Assignment** digunakan untuk mengisikan (assign) sebuah nilai ke variabel. Simbol yang biasa digunakan adalah tanda sama dengan  `=`. Contohnya:

```c
int x, y;  
x = 4;  
y = 3;  
x = x + y; // x = 7  
y = x + x; // y = 14 
```

## Operator Aritmatika

Seperti namanya, **operator aritmatika** melakukan operasi layaknya pada matematika seperti penjumlahan, pengurangan, pembagian dsb. Beberapa operator menggunakan simbol yang sama pada matematika (penjumlahan dengan simbol `‘+’`, pengurangan dengan `‘-‘`, dst.). Operator-operator aritmatika pada bahasa C adalah sebagai berikut.

| Simbol | Operasi                                               | Contoh   |
|:------:| ----------------------------------------------------- | :------: |
| +      | Penjumlahan pada dua operan                           | `a + b`  |
| -      | Pengurangan pada dua operan                           | `a - b`  |
| *      | Perkalian pada dua operan                             | `a * b`  |
| /      | Pembagian pada dua operan                             | `a / b`  |
| %      | Menghitung sisa pembagian dua operan (operasi modulo) | `a % b`  |

## Operator Increment dan Decrement

Operator `++` disebut dengan operator **increment**, sedangkan operator `--` merupakan operator **decrement**. Kedua operator ini digunakan untuk menambah (increment)/mengurangi (decrement) nilai dari suatu variabel sebanyak satu.

Terdapat dua cara untuk menggunakan operator ini.

+ **Prefix** - yakni dengan meletakkan operator increment/decrement didepan nama variabel. 

    ```c
    int a, b;  
    a = 5;  
    ++a; // Nilai a sekarang adalah 6  
    --a; // Nilai a sekarang adalah 5
    ```

    Cara kerja dari operator increment/decrement prefix adalah dengan menambahkan/mengurangi nilai variabel sebanyak satu terlebih dahulu, sebelum operan tersebut digunakan pada operasi lainnya pada sekuens intstruksi yang sama. Untuk lebih jelasnya, perhatikan potongan kode berikut

    ```c
    int a, b;  
    a = 5;  
    b = ++a; // Nilai b sekarang adalah 6  
    a = --b; // Nilai a sekarang adalah 5 
    ```

    Di sini, saat instruksi `b = ++a;` dieksekusi, yang terjadi pertama kali adalah nilai dari `a` ditambahkan satu terlebih dahulu, kemudian baru di-assign nilainya ke variabel `b`.

+ **Postfix** - yakni dengan meletakkan operator increment/decrement di belakang nama variabel. Cara kerja dari operator increment/decrement postfix berbeda dari prefix. Pada postfix, nilai variabel akan ditambah satu setelah operan digunakan pada operasi lainnya pada sekuens instruksi yang sama. Perhatikan potongan kode berikut.

    ```c
    int a, b;  
    a = 5;  
    b = a++; // Nilai b sekarang adalah 5  
    a = b--; // Nilai a sekarang adalah 5 
    ```

    Di sini, saat instruksi `b = a++;` dieksekusi, yang terjadi pertama kali adalah nilai dari `a` akan di-assign terlebih dahulu ke variabel `b`, kemudian baru ditambahkan satu. Karena itulah variabel `b` mendapat nilai dari `a` sebelum terjadi penambahan.

# Operator Logika

## Operator Perbandingan

**Operator Perbandingan** digunakan untuk memeriksa relasi dan membandingkan nilai dari dua operan. Jika benar akan menghasilkan nilai **TRUE** (direpresentasikan angka 1), jika salah maka akan menghasilkan nilai **FALSE** (direpresentasikan angka 0).

Berikut adalah operator relasional dalam bahasa C.

| Operator                | Simbol   | Keterangan                                                                                            | Contoh                                           |
| ----------------------- | :----:   | ----------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| Sama dengan             | ==       | Digunakan untuk memeriksa apakah kedua operan memiliki nilai yang sama.                               | 5 == 2 (FALSE)<br>5 == 5 (TRUE)                  |
| Tidak Sama dengan       | !=       | Digunakan untuk memeriksa apakah kedua operan memiliki nilai yang tidak sama.                         | 5 != 2 (TRUE)<br>5 != 5 (FALSE)                  |
| Lebih besar             | >        | Digunakan untuk membandingkan apakah operan pertama lebih besar nilainya dari operan kedua.           | 5 > 2 (TRUE)<br>5 > 5 (FALSE)<br>2 > 4 (FALSE)   |
| Lebih kecil             | <        | Digunakan untuk membandingkan apakah operan pertama lebih kecil nilainya dari operan kedua.           | 5 < 2 (FALSE)<br>5 < 5 (FALSE)<br>2 < 4 (TRUE)   |
| Lebih besar sama dengan | >=       | Digunakan untuk membandingkan apakah operan pertama lebih besar atau sama nilainya dari operan kedua. | 5 >= 2 (TRUE)<br>5 >= 5 (TRUE)<br>2 >= 4 (FALSE) |
| Lebih kecil sama dengan | <=       | Digunakan untuk membandingkan apakah operan pertama lebih kecil atau sama nilainya dari operan kedua. | 5 <= 2 (FALSE)<br>5 <= 5 (TRUE)<br>2 <= 4 (TRUE) |

## Operator Logika

**Operator Logika** digunakan untuk melakukan tes pada kondisi/ekspresi, apakah kondisi tersebut benar atau salah. Operator logika hanya akan menghasilkan nilai **TRUE** (jika benar) atau **FALSE** (jika salah). TRUE direpresentasikan oleh angka 1, sedangkan FALSE oleh angka 0.

Operator-operator logika dalam bahasa C adalah sebagai berikut.

| Operator                | Simbol   | Keterangan                                                                                            | Nilai Kebenaran                                              |
| ----------------------- |:------:  | ----------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| Logical NOT             | !        | Operator NOT digunakan untuk membalikkan kondisi, TRUE menjadi FALSE dan FALSE menjadi TRUE.          | `!1 = 0`<br>`!0 = 1`                                         |
| Logical AND             | &&       | Operator AND akan menghasilkan nilai TRUE jika kedua operan mempunyai nilai TRUE.                     | `1 && 1 = 1`<br>`0 && 1 = 0`<br>`1 && 0 = 0`<br>`0 && 0 = 0` |
| Logical OR              | \|\|      | Operator OR akan menghasilkan nilai TRUE jika salah satu operan mempunyai nilai TRUE.                | `1 \|\| 1 = 1`<br>`0 \|\| 1 = 1`<br>`1 \|\| 0 = 1`<br>`0 \|\| 0 = 0` |

> Operator Logika **NOT** merupakan operator unary yang artinya hanya pada bekerja pada satu operan

Operator logika pada umumnya digunakan bersamaan dengan operator relasional untuk melakukan tes pada ekspresi yang berhubungan dengan kebenaran suatu kondisi. Penggunaan paling umum adalah untuk melakukan percabangan (akan dipelajari di bagian selanjutnya).

Contoh:

```c
int a, b, c, d;  
a = 11;  
b = 24;  
c = 11;  
d = ((a == c) && (b > a));               // 1 (TRUE)  
d = ((a >= b) || (a < c));               // 0 (FALSE)  
d = ((b != b) || (b > c)) && (c == a);   // 1 (TRUE) 
```

## Operator Bitwise

**Operator Bitwise**, seperti namanya digunakan untuk melakukan operasi pada dua operan dalam skala biner (bilangan basis 2). Sebelum mempelajari lebih lanjut cara kerja operasi bitwise, sebaiknya kamu harus paham terlebih dahulu mengenai bilangan dalam basis biner.

Terdapat 6 jenis operator bitwise, yakni **AND**, **OR**, **XOR**, **COMPELEMENT**, **SHIFT LEFT**, dan **SHIFT RIGHT**. Untuk lebih memahami perbedaan cara kerja operator bitwise, perhatikan tabel berikut.

| Operator                | Simbol | Keterangan                                                                                                                             |
| ----------------------- | :----: | -------------------------------------------------------------------------------------------------------------------------------------- |
| Bitwise AND             | &      | Mengevaluasi bit dari dua operan. Menghasilkan 1 apabila keduanya 1, jika tidak menghasilkan nilai 0.                                  |
| Bitwise OR              | \|     | Mengevaluasi bit dari dua operan. Menghasilkan 1 apabila salah satu nilainya 1, jika keduanya 0, maka menghasilkan nilai 0.            |
| Bitwise XOR             | ^      | Mengevaluasi bit dari dua operan. Menghasilkan 1 apabila bit pada kedua operan nilainya berbeda. Jika sama, maka menghasilkan nilai 0. |
| Bitwise COMPLEMENT      | ~      | Membalik semua nilai bit, dari 1 menjadi 0 dan 0 menjadi 1 (dalam panjang bit).                                                        |
| Bitwise SHIFT LEFT      | <<     | Menggeser bit ke kiri sebanyak n (operan kedua).                                                                                       |
| Bitwise SHIFT RIGHT     | >>     | Menggeser bit ke kanan sebanyak n (operan kedua).                                                                                      |

# Operator Lain

## Operator Gabungan

**Operator Gabungan** adalah operator yang terdiri dari gabungan dua operator. Tujuan dari operator gabungan adalah untuk mempersingkat penulisan kode. Berikut adalah operator gabungan dalam bahasa C.

| Operator | Contoh    | Ekuivalen Dengan        |
| :------: | :------:  | :---------------------: |
| +=	   | `a += b`  |	`a = a + b`      |
| -=	   | `a -= b`  |	`a = a - b`      |
| *=	   | `a *= b`  |	`a = a * b`      |
| /=	   | `a /= b`  |	`a = a / b`      |
| %=	   | `a %= b`  |	`a = a % b`      |
| &=	   | `a &= b`  |	`a = a & b`      |
| \|=	   | `a \|= b` |	`a = a \| b`     |
| ^=	   | `a ^= b`  |	`a = a ^ b`      |
| >>=	   | `a >>= b` |	`a = a >> b`     |
| <<=	   | `a <<= b` |	`a = a << b`     |

## Operator sizeof()
Walaupun mempunyai bentuk seperti sebuah fungsi, namun dalam standardisasi bahasa C menganggap operator `sizeof()` sebagai operator. Kegunaan dari operator ini adalah untuk mengetahui besarnya alokasi memori sebuah operan (berupa variabel atau tipe data) dalam satuan byte.

Contoh:

```c
sizeof(int);
```

## Operator Address-of

Operator  Address-of (`&`) ini mengembalikan alamat memori dari sebuah operan berupa variabel.

Contoh:

```c
int var;
printf("%d\n", &var);
```

## Operator Dereference

Berbeda dari operator address-of (`&`), operator deference (`*`) mengembalikan nilai dari variabel pointer (akan dijelaskan pada modul pointer).

> Meskipun menggunakan simbol yang sama seperti operator perkalian, operator deference mempunyai fungsi yang benar-benar berbeda dari operator perkalian.

## Operator Kondisional 

Operator kondisial (` ? : `) merupakan satu-satunya operator ternary (bekerja pada tiga operan) dalam bahasa C. Fungsi dari operator kondisional layaknya percabangan menggunakan `if - else` (akan dijelaskan pada modul percabangan).

## Operator Koma (`,`)

Tanda koma (`,`) sebagai operator dalam bahasa C merupakan binary operator yang akan mengevaluasi operan pertama, kemudian akan membuang hasilnya. Lalu mengevaluasi operan kedua dan akan mengembalikan nilainya.

```c
int number = (5, 23);   // number bernilai 23, bukan 5
```

Selain berfungsi sebagai operator, tanda koma (`,`) juga berfungsi sebagai separator (pemisah) antar statement. Misalkan saat deklarasi lebih dari satu variabel.

```c
int var1, var2, var3;   
// Menggunakan tanda koma untuk memisahkan deklarasi tiap variabel
```

> Tidak semua statement dapat dipisahkan oleh tanda koma.

## Operator Subscript (`[]`)

Penggunaan paling umum operator ini adalah untuk melakukan pengaksesan terhadap elemen suatu array (akan dibahas pada modul array).

_Operator lain yang belum ter-cover pada modul ini akan dibahas pada modul-modul selanjutnya._

[< Kembali ke Daftar Isi](#daftar-isi)

# Latihan

## Latihan 1

Buatlah sebuah program dengan output sebagai berikut :

```c
Hello World!
"Hello World!"
\(*o*)\ /(*o*)/
'Programming is Ez'
```

## Latihan 2

Buatlah sebuah program dengan dengan ketentuan banyak input yang dipisahkan oleh spasi, kemudian menjumlahkan input pertama dengan kedua, input ketiga dengan keempat, dst :

Input :

```c
1 2 3 4 5 6
```

Output :

```c
3 7 11
```

## Latihan 3

Buatlah sebuah program yang dapat menghitung luas lingkaran (π = 3.14), dengan jari-jari sebagai input :

Input :

```c
8
```

Output :

```c
200.96
```