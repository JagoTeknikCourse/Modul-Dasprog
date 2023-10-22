## Daftar Isi
- [Perulangan](#perulangan)
    + [Perulangan While](#perulangan-while)
    + [Perulangan Do-While](#perulangan-do-while)
    + [Perulangan For](#perulangan-for)
    + [Perulangan Bersarang](#perulanganpercabangan-bersarang-nested)
- [Break dan Continue](#break-dan-continue)
- [Infinite Loop](#infinite-loop)
- [Soal Latihan](#soal-latihan)
    + [Soal 1](#soal-1)
    + [Soal 2](#soal-2)
    


# Perulangan

Perulangan atau _looping_ memungkinkan kita untuk mengeksekusi potongan kode berulang-ulang hingga mencapai suatu kondisi. Ada 3 jenis perulangan dalam bahasa C, yaitu `while`, `do - while`, dan `for`.

## Perulangan While

Perulangan `while` adalah bentuk perulangan yang paling sederhana. Sintaksnya adalah sebagai berikut.

```c
//initial value (nilai awal). misal, i = 0
while (<Kondisi>) {
    // Potongan kode yang ingin dieksekusi
    .
    .
    .
    // increment/decrement misalnya, i++
}
```
Cara kerja perulangan `while` mirip dengan `if`. Jika pada **if** potongan kode akan dieksekusi **sekali saja** apabila kondisi bernilai **TRUE**, pada **while** potongan kode akan **terus dieksekusi** hingga ekspresi/kondisi menghasilkan **FALSE**.

Contoh

```c
#include <stdio.h>

int main()
{
    int i = 0;
    while (i < 10)
    {
        printf("Hello World! ke-%d \n",i);
        i++;
    }
    return 0;
}
```

Sehingga pada contoh di atas:

- Pada awalnya, **variabel `i`** bernilai 0. 
- Sequence selanjutnya adalah `while`, dan i bernilai kurang dari 10 (**TRUE**), maka kode didalam `while` akan dijalankan, yakni print Hello world ke-i. 
- Setelah melakukan print hello world, **variabel `i`** akan di increment, dan kembali ke statement `while` untuk memeriksa apakah **`i`** masih kurang dari 10 setelah di-increment
- Karena setelah **`i`** di-increment nilainya = 1 dan kurang dari 10, maka `while` akan dijalankan lagi hingga **`i`** bernilai 10 yang berarti tidak memenuhi kondisi `while`.

## Perulangan Do-While

Sintaks dari perulangan `do – while` adalah sebagai berikut.
```c
do {
    // Potongan kode yang dieksekusi.
    .
    .
    // increment/decrement
} while (<Kondisi>)
```

Cara kerja dari perulangan `do – while` mirip dengan perulangan `while`. Hanya saja, pada perulangan `do – while`, potongan kode dijamin akan dieksekusi tepat satu kali sebelum mengevaluasi kondisi diakhir.

Contoh

```c
#include <stdio.h>
int main()
{
    int num = 0;
    do
    {
        printf("Num sekarang adalah %d\n",num);
        printf("Masukkan bilangan integer positif (-1 untuk keluar ): ");
        scanf("%d", &num);
    } while (num != -1);
    return 0;
}
```

## Perulangan For

Perulangan `for` merupakan perulangan paling rumit diantara perulangan lainnya. Sintaksnya adalah sebagai berikut.

```c
for (init_statement; kondisi/ekspresi; end_statement) {
    //  Potongan kode yang dieksekusi
    .
    .
}
```

Cara kerjanya adalah sebagai berikut:
- Bagian `init_statement` digunakan untuk inisialisasi variabel yang akan digunakan dalam perulangan. Bagian ini hanya dijalankan sekali saja pada saat awal perulangan.
- Selanjutnya `kondisi/ekspresi` akan dievaluasi. Jika menghasilkan **TRUE**, maka akan mengeksekusi potongan kode. Jika menghasilkan **FALSE**, maka perulangan berhenti.
- Setelah potongan kode selesai dieksekusi, akan mengeksekusi bagian `end_statement`. Biasanya bagian ini digunakan sebagai **increment/decrement**.
- Lalu akan **mengevaluasi ekspresi/kondisi lagi**, dan begitu seterusnya.

Contoh

```c
#include <stdio.h>
int main()
{
    int i;
    //    init; condition; increment
    for (i = 0; i < 10  ; i++) {
        printf("Hello World!\n");
    }
}
```
1. Awalnya **`i`** bernilai 0
2. For statement akan memeriksa nilai **`i`** apakah kurang dari 10
3. Apabila **TRUE** maka jalankan kode dalam for block, yakni print hello world
4. Setelah command dalam block for selesai dijalankan, maka variabel **`i`** akan di-increment, dan diperiksa lagi.
5. Apabila **`i`** kurang dari 10, maka command dalam block dieksekusi, apabila tidak maka for loop akan berhenti

## Perulangan Bersarang (Nested Loop)

Perulangan juga dapat dibuat secara bersarang (membuat perulangan di dalam perulangan), tentu saja menyesuaikan kebutuhan. Contoh berikut adalah perulangan `for` bersarang.
```c
int i, j;
for (i = 1; i <= 10; ++i) {
    // Statement yang ingin dijalankan pada level terluar

    for (j = 1; j <= 10; j++) {
        // Statement yang ingin dijalankan pada level terdalam

        // Percabangan di dalam perulangan
        if (i == 10) {
            // Lakukan sesuatu
        }
    }
    // Statement yang ingin dijalankan pada level terluar
}
```

# Break and Continue
Keyword `break` dan `continue` digunakan untuk mengendalikan (kontrol) alur pada perulangan. Berikut penjelasannya.

## Break
Perintah `break` digunakan untuk **menghentikan** perulangan (secara paksa). Apabila perintah `break` pada suatu perulangan dijalankan, maka perulangan tersebut akan **dihentikan (secara paksa) dari titik dimana perintah break muncul**.

Contoh

```c
#include <stdio.h>

int main()
{
	int i;
	for (i = 1; i <= 6; i++) {
		printf("%d\n", i);
		//   Jika i adalah 4, maka keluar dari perulangan
		if (i == 4) {
			break;
		}
	}
	return 0;
}
```

## Continue

Kebalikan dari perintah break, perintah `continue` digunakan untuk **melanjutkan perulangan**. Pada perulangan, apabila menemui perintah `continue`, maka perintah-perintah dibawah `continue` akan **diabaikan** dan **kembali akan mengevaluasi ekspresi/kondisi**. Sedangkan pada perulangan `for` akan langsung mengekekusi bagian end_statement kemudian mengevaluasi ekspresi/kondisi.

Contoh

```c
#include <stdio.h>

int main()
{
	int i;
    for (i = 1; i <= 6; i++) {
	    // Jika i adalah 4, maka abaikan perintah printf()
        if (i == 4) {
            continue;
        }
        printf("%d\n",i);
    }
    return 0;
}
```

# Infinite Loop

Infinite loop adalah kasus di mana perulangan tidak akan pernah berhenti. Hal ini terjadi karena perulangan tidak akan pernah menemui kondisi yang membuatnya berhenti. Contoh di bawah akan menghasilkan infinite loop.

```c
#include <stdio.h>

int main()
{
    int i;
    for (i = 1; i <= 100; i--) {
        // Perulangan tak akan pernah berhenti
    }
}
```

# Soal Latihan

## Soal 1

Buatlah program yang menggunakan perulangan for untuk mencetak angka dari n hingga 0 dengan langkah pengurangan 2.

**Sample Input 1**
```
12
```
**Sample Output 1**
```
12 10 8 6 4 2 0
```

**Sample Input 2**
```
15
```
**Sample Output 2**
```
15 13 11 9 7 5 3 1 0
```

## Soal 2

Buatlah program yang menggunakan perulangan for untuk menghitung faktorial dari suatu bilangan. Faktorial dari bilangan n (dinyatakan sebagai n!) adalah hasil perkalian semua bilangan bulat dari 1 hingga n.

**Sample Input 1**
```
Input bilangan bulat positif: 5
```
**Sample Output 1**
```
Faktorial dari 5 adalah 120
```

**Sample Input 2**
```
Input bilangan bulat positif: 10
```
**Sample Output 2**
```
Faktorial dari 5 adalah 3628800
```