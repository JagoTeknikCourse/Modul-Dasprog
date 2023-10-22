## Daftar Isi
- [Array](#array)
    + [Pengenalan Array](#pengenalan-array)
    + [Deklarasi Array](#deklarasi-array)
    + [Inisialisasi Array](#inisialisasi-array)
    + [Mengakses Array](#mengakses-array)
    + [Dimensi Array](#dimensi-array)
        ++ [Array Satu Dimensi](#array-satu-dimensi)
        ++ [Array Multidimensi](#array-multidimensi)
- [Soal Latihan](#soal-latihan)
    + [Soal 1](#soal-1)
    + [Soal 2](#soal-2)
    + [Soal 3](#soal-3)



# Array

## Pengenalan Array

Array merupakan jenis struktur data yang menampung elemen betipe data sama secara sekuensial dengan ukuran (kapasitas) yang tetap (_fixed-size_). Bayangkanlah sebuah array sebagai sekumpulan elemen sejenis yang disusun secara berurutan pada satu _identifier_ (nama).

## Deklarasi Array

Array juga sama seperti variabel, perlu dideklarasikan terlebih dahulu sebelum bisa digunakan. Deklarasi array sama seperti variabel, hanya saja saat pendeklarasiannya perlu dituliskan ukurannya.

```
tipe_data identifier_array[size];
```

## Inisialisasi Array

Kita juga bisa menginisialisasi elemen-elemen pada array setelah dideklarasikan. Sintaksnya adalah seperti berikut.

```
tipe_data identifier_array[size] = {elem1, elem2, elem3, ....}
```

## Mengakses Array

Seperti yang telah dijelaskan sebelumnya, array disimpan secara sekuensial (pada blok memori secara berurutan). Lalu bagaimana kita mengakses tiap elemennya? Pengaksesan elemen pada array dilakukan dengan menuliskan _identifier_ array-nya lalu digabung dengan menggunakan operator subscript `[]` dengan menyertakan indeks didalamnya.

![akses_array](https://github.com/AlproITS/DP_modul-2/blob/master/img/Array_access.png)

Indeks pada array menggunakan _zero-based index_, yang artinya elemen pertama pada array ditunjukkan oleh indeks ke 0 (bukan ke 1) dan elemen terakhir ditunjukkan oleh indeks ke N-1 (misal N adalah panjang array).
Elemen-elemen pada array dapat diperlakukan sama seperti halnya variabel. Kita dapat melakukan assignment, operasi aritmatika, dan lain-lain.

Contoh:

```c
int main () 
{

  int a[10]; //Deklarasi Array
  
  int b[5] = {1, 2, 3, 4, 5}; //Inisialisasi Array
  
  a[0] = 50;
  a[1] = 20;
  
  printf("%d %d\n", a[0], a[1]);
  
  return 0;

}
```

Mengapa kita perlu array? Andaikan kita membutuhkan 1000 inputan data, kita tidak perlu membuat deklarasi variabel berjumlah 1000, misalkan variabel a1 hinga a1000. Namun, kita cukup menuliskan 1 identifier array berkapasitas 1000.

Contoh program tanpa array:
```c
int main () {

  int a, b, c, d, e; //Deklarasi 5 variabel integer
  
  scanf("%d %d %d %d %d", &a, &b, &c, &d, &e);
  
  printf("Bilangan pertama adalah %d\n", a);
  printf("Bilangan kedua adalah %d\n", b);
  printf("Bilangan ketiga adalah %d\n", c);
  printf("Bilangan keempat adalah %d\n", d);
  printf("Bilangan kelima adalah %d\n", e);
  return 0;

}
```

Bayangkan kita tidak hanya memasukkan 5 data, melainkan 1000 data, bagaimana kita mendeklarasikan semuanya dalam variabel dan kemudian mencetaknya? Maka dari itulah array digunakan.

Contoh program menggunakan array:
```c
int main () 
{
	int a[5], i; 
	for(i = 0; i < 5; i++) {
		scanf("%d", &a[i]); //Input array
	}

	for(i = 0; i < 5; i++) {
		prinf("Bilangan ke-%d adalah %d\n", i+1, a[i]; // Output array
	}

	return 0;

}
```
## Dimensi Array

### Array Satu Dimensi

Sebuah array dikatan berdimensi satu apabila tiap elemennya hanya menyimpan satu data/objek. Contoh-contoh pada penjelasan sebelumnya merupakan array satu dimensi.

Contoh array satu dimensi:

```c
int main()
{
	int arr[5];
	arr[0] = 4;
	arr[1] = 2;
	arr[2] = 3;
	return 0;
}
```

Jika diilustrasikan, maka array tersebut akan tampak seperti di bawah.

![array-satu-dimens](https://github.com/AlproITS/DP_modul-2/blob/master/img/1D_Array.png)

### Array Multidimensi

Sebuah array dikatakan multidimensional apabila tiap elemen array  menampung array lainnya. Apabila array satu dimensi hanya memiliki sebuah index, array multidimensi memiliki dua atau lebih index untuk mengakses elemen dalam array tersebut. 

Cara deklarasinya pun berbeda dari array satu dimensi. Kita memerlukan N buah kurung siku untuk membuat array dengan N-dimensi.

Berikut adalah contoh program dengan array dua dimensi:
```c
int main () 
{
	int matriks[5][6];
	matriks[2][3] = 100;
	matriks[1][4] = 200;
	return 0;
}
```

Apabila diilustrasikan, bentuk array dua dimensi layaknya baris dan kolom, seperti gambar di bawah.

![array-dua-dimensi](https://github.com/AlproITS/DP_modul-2/blob/master/img/2D_Array.png)

Selain bentuk dua dimensi, kita dapat membuat array hingga N-dimensi, sesuai kebutuhan.


# Soal Latihan

## Soal 1

Buat program untuk mencetak asterisk, `*`, untuk bilangan genap, dan bilangan aslinya untuk bilangan ganjil, dari n buah bilangan mulai 1 s.d n.

**Sample Input**

```
6
```

**Sample Output**

```
1 * 3 * 5 *
```
    
## Soal 2

Buat program untuk mencetak asterisk, `*`, untuk bilangan prima, dan angka asli untuk bilangan non-prima dari n buah bilangan mulai 2 s.d n.

**Sample Input**

```
10
```

**Sample Output**

```
* * 4 * 6 * 8 9 10
```


## Soal 3

Buatlah program untuk mencetak N buah angka yang diinput secara terbalik. Input baris pertama adalah N yang merupakan banyaknya angka yang akan diinput. Baris berikutnya terdapat N buah angka (dipisahkan spasi).

**Sample Input**

```
5
1 4 3 2 9
```

**Sample Output**

```
9
2
3
4
1
```