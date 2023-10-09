## Daftar Isi

- [Control Flow](#control-flow)
- [Percabangan](#percabangan)
    + [If](#percabangan-if)
    + [If-Else](#percabangan-if-else)
    + [If-Else if](#percabangan-if-elseif)
    + [Switch-Case](#percabangan-switch-case)
    + [Operator Kondisional ( ? : )](#operator-kondisional--)
- [Soal Latihan](#soal-latihan)
    + [Latihan 1](#latihan-1)
    + [Latihan 2](#latihan-2)
    + [Latihan 3](#latihan-3)


# Control Flow
Control Flow adalah cara kita mengatur jalan penyataan, instruksi, dan pemanggilan fungsi  suatu program. Tanpa control flow, program kita hanya bergerak dari atas ke bawah saja (**sequential**). Dengan control flow, suatu insruksi akan dieksekusi jika logika nya terpenuhi. Dalam bahasa C terdapat 2 jenis control flow, yaitu percabangan (**selection**) dan perulangan (**repetition**). Di Modul ini, kita akan membahas percabangan terlebih dahulu.

# Percabangan
Percabangan memungkinkan kita untuk menentukan kode manakah yang akan kita eksekusi berdasarkan suatu kondisi. Percabangan di bahasa C ada 4, yaitu `if`, `if-else`, `if-else if`, dan `switch`.

## Percabangan If

Sintaks yang digunakan dalam percabangan menggunakan `if` adalah sebagai berikut.

```c
if (<Kondisi syarat>) {

    // Kode yang akan dieksekusi jika kondisi syarat tersebut benar

}
```

Cara kerja percabangan `if` yaitu dengan memeriksa dan mengevaluasi suatu kondisi untuk menentukan apakah instruksi selanjutnya dalam _bracket_ akan dijalankan atau tidak oleh program.
- Jika kondisi tersebut bernilai **TRUE (1)**, kode yang di dalam bracket akan **dieksekusi**. 
- Sebaliknya jika kondisi tersebut bernilai **FALSE (0)**, kode yang di dalam bracket **tidak akan dieksekusi**.

Contoh

Sebagai contoh, di meteran listrik yang menggunakan token terdapat alarm yang akan **menyala jika daya listrik telah mencapai batas minimal (10 kWh menurut beberapa sumber)**. Maka kondisi yang disyaratkan pada percabangan adalah “Apakah daya listrik kurang dari 10 kWh?”.

Pada kasus ini jika kondisi
- **Apakah daya listrik kurang dari 10 kWh?** maka nyalakan alarm peringatan.

```c
#include <stdio.h>
int main()
{
    int daya = 0;
    daya = 3;
    if (daya < 10) //jika daya listrik kurang dari 10 kWh
    {
        // Apa yang perlu dilakukan ketika kondisi terpenuhi?
        printf("Alarm peringatan menyala!\n");
    }
}
```

Output

```
Alarm peringatan menyala!
```

## Percabangan If-Else

Sintaks yang digunakan dalam percabangan menggunakan `if-else` adalah sebagai berikut.

```c
if (<Kondisi syarat>) {

    // Kode yang akan dieksekusi jika kondisi tersebut benar

} else {

    // Kode yang akan dieksekusi jika kondisi tersebut salah

}
```

Cara kerja percabangan `if-else` yaitu memeriksa kondisi dalam `if`.
- Jika kondisi tersebut bernilai **TRUE (1)**, Program akan **menjalankan kode di dalam bracket `if`**.
- Sebaliknya jika kondisi tersebut bernilai **FALSE (0)**, kode di bawah **`else`** lah **yang akan dijalankan**.

Sebagai contoh, kita ingin mencari tahu apakah seseorang absen dari kelas atau tidak. **apabila hadir, maka absensinya akan di centang (bernilai V)**, dan **Apabila tidak hadir, maka absensinya akan dicoret (bernilai X)**.

Sehingga dari kasus tersebut, didapat dua alternatif kondisi.
- **Apabila ia hadir, maka muncul V**
- **Apabila ia tidak hadir, maka muncul X**

```c
#include <stdio.h>
#define DATANG 1

int main()
{
    int hadir = DATANG;
    if (hadir) // Jika orang tersebut hadir
    {
        printf("V\n");
    } else {
        printf("X\n");
    }
}
```

Output

```
V

```

## Percabangan If-Else if

Sintaks yang digunakan dalam percabangan menggunakan `if-else if` adalah sebagai berikut.

```c
if (<Kondisi syarat>) {

    // Kode yang akan dieksekusi jika kondisi tersebut benar

}else if (<Kondisi syarat>) {

    // Kode yang akan dieksekusi jika kondisi tersebut salah

}
    // Boleh menambahkan else{} apabila perlu
```

Cara kerja percabangan `if-else` yaitu memeriksa kondisi dalam `if`.
- Jika kondisi tersebut bernilai **TRUE (1)**, Program akan **menjalankan kode di dalam bracket `if`**.
- Apabila kondisi pertama tidak memenuhi, maka ia akan memerika kondisi didalam `else-if`, apabila bernilai **TRUE (1)**, maka ia akan **menjalankan perintah dalam bracket tersebut**, apabila tidak maka ia akan menjalankan sequence selanjutnya.
- Apabila kita menyediakan statement else diakhir, maka ketika **seluruh kondisi** `if` dan `else-if` tidak memenuhi atau **FALSE (0)**, maka secara otomatis ia akan **menjalankan perintah di dalam `else`** tersebut.

## Percabangan Switch-Case

Selain penggunaan statement `if` untuk memilih diantara banyak alternatif, terdapat pula statement `switch` yang memiliki fungsi yang sama, untuk memilih diantara banyak alternatif berdasarkan sebuah kondisi. Kondisi pada statemen `switch` berisi ekspresi (dapat menggunakan sebuah variable tunggal bertipe int atau char) yang akan diperiksa nilainya di setiap blok case. sedangkan pada `case` berisi nilai yang akan menjadi syarat / pembanding terhadap `switch`

Sintaks untuk Switch-Case:

```c
switch(ekspresi) {

    case ekspresi-konstan:
        statement;
        break;

    case ekspresi-konstan:
        statement;
        break;
  
    /* Anda bisa memiliki jumlah case sebanyak mungkin */

    /* Anda harus mengakhiri blok kode Switch-Case dengan "default",
       yaitu bagian kode yang akan dieksekusi jika tidak ada case yang memenuhi */

    default: 
        statement;
}
```

Pada setiap blok `case` harus ditambahkan statement **``break``**, karena apabila tidak maka ia akan tetap menjalankan blok case di bawahnya hingga bertemu `break` lain atau pada akhir blok switch.

Contoh

```c
#include <stdio.h>

int main()
{
    char platNomor;
    printf("Masukkan huruf awal plat nomor anda: ");
    scanf("%c", &platNomor);

    switch(platNomor)
    {
        case 'L':
            printf("Surabaya");
            break;

        case 'B':
            printf("Jakarta");
            break;

        case 'D':
            printf("Bandung");
            break;

        case 'N':
            printf("Malang/Lumajang");
            break;

        default:
            printf("Karakter plat nomor tidak diketahui");
    } 
    return 0;
}
```

Dalam contoh di atas, **ekspresi** yang digunakan adalah **PlatNomor**, di mana **case-case** nya adalah, huruf plat nomor tersebut, L, B, D, N, dan sebagainya.

## Operator Kondisional (` ? : `)

Operator kondisional mempunyai bentuk sintaks sebagai berikut:

```
(ekspresi/kondisi) ? (ekspresi jika TRUE) : (ekspresi jika FALSE);
```

Operator kondisional adalah satu-satunya operator ternary dalam bahasa C. Operator kondisional bertingkah seperti layaknya percabangan `if - else`. Ekspresi/kondisi yang akan dievaluasi diletakkan sebelum tanda tanya (`?`). Apabila menghasilkan **TRUE**, maka program akan mengeksekusi bagian di **kiri** tanda titik dua. Jika **FALSE**, akan mengeksekusi bagian di **kanan** tanda titik dua.

Contoh:

```c
#include <stdio.h>

int main()
{
    int mark;
    
    scanf("%d", &mark);
    printf(mark >= 75 ? "Lulus\n" : "Tidak Lulus\n");
    return 0;
}
```

Program di atas ekuivalen dengan:

```c
#include <stdio.h>

int main()
{
    int mark;
    
    scanf("%d", &mark);
    if (mark >= 75) {
        printf("Lulus\n");
    } else {
        printf("Tidak Lulus\n");
    }
    return 0;
}
```

# Soal Latihan

## Soal 1

Buatlah program yang dapat menentukan apakah suatu input bilangan dari 0 sampai 999 merupakan bilangan prima.

**Sample Input 1**
```
719
```
**Sample Output 1**
```
Merupakan Bilangan Prima
```

**Sample Input 2**
```
25
```
**Sample Output 2**
```
Bukan Merupakan Bilangan Prima
```

Catatan:
coba pahami dengan teliti syarat bilangan prima

## Soal 2

Buatlah program yang hanya menerima inputan 0 sampai 999 dan mengeluarkan hasil berupa kalimat terbilang dari angka yang dimasukan.

**Sample Input 1**
```
1
```
**Sample Output 1**
```
Satu
```

**Sample Input 2**
```
11
```
**Sample Output 2**
```
Sebelas
```

**Sample Input 3**
```
979
```
**Sample Output 3**
```
Sembilan ratus tujuh puluh sembilan
```