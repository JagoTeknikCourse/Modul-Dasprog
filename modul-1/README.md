## Daftar Isi

- [IDE (Integrated Development Environment)](#ide-intregated-development-environment)

- [Pengenalan Bahasa C](#pengenalan-bahasa-c)

    + [Statement](#statement)
    + [Program "Hello, world."](#program-hello-world)
    + [Struktur Program](#struktur-program)
    + [Komentar](#komentar)\
    + [Input Dasar](#input-dasar)
    + [Output Dasar](#output-dasar)
    

- [Identifier](#identifier)

    + [Identifier](#identifier)

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
    + [Operator Relasional](#operator-relasional)
    + [Operator Bitwise](#operator-bitwise)
    + [Operator Gabungan](#operator-gabungan)
    + [Operator Lain](#operator-lain)

# IDE (Integrated Development Environment)

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

Kita juga dapat menambahkan escape sequence pada string. Escape Sequence adalah urutan karakter yang digunakan untuk memformat output dan tidak ditampilkan ketika dicetak ke layar. Setiap karakter mempunyai fungsi tertentu. lihatlah tabel escape sequence berikut
![a](https://github.com/JagoTeknikCourse/Modul-Dasprog/blob/main/img/escape-sequence.md)
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
 
![a](https://github.com/JagoTeknikCourse/Modul-Dasprog/blob/main/img/printf.md)

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