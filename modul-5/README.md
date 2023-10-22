## Daftar Isi
- [String](#string)
    + [Pengenalan String](#pengenalan-string)
    + [Representasi String](#representasi-string)
    + [Fungsi-Fungsi String](#fungsi-fungsi-string)
        ++ [Fungsi `strcpy`](#fungsi-strcpy)
        ++ [Fungsi `strcat`](#fungsi-strcat)
        ++ [Fungsi `strcmp`](#fungsi-strcmp)
        ++ [Fungsi `strlen`](#fungsi-strlen)
- [Soal Latihan](#soal-latihan)
    + [Soal 1](#soal-1)
    + [Soal 2](#soal-2)
    + [Soal 3](#soal-3)



# String

## Pengenalan String

Secara umum, string merupakan kumpulan dari satu atau lebih karakter. Spesifik pada bahasa C, string didefinisikan sebagai kumpulan karakter yang diakhiri oleh karakter null (`'\0'`).

Misalkan string `"Dasar"`, pada bahasa C direpresentasikan sebagai kumpulan karakter `'D'`, `'a'`, `'s'`, `'a'`, `'r'`, dan `'\0'`.

## Representasi String

Pada bahasa C, string direpresentasikan oleh array bertipe `char`.
Contoh pendeklarasian string:
```c
#include <stdio.h>

int main () 
{  
	char str[] = "Halo"; 
	return 0;
}
```

Contoh di atas akan mendeklarasikan string bernama str dengan kapasitas 5 karakter, di mana `str[0] = 'H'`, `str[1] = 'a'`, `str[2] = 'l'`, `str[3] = 'o'`, dan `str[4] = '\0'`.
Perhatikan bahwa str[4] berisi karakter '\0' (null character), walaupun dalam literal string di atas tidak ada karakter tersebut. 

Dalam bahasa C, karakter null digunakan untuk menandakan akhir dari sebuah string.

Contoh pendeklarasian string (2):
```c
#include <stdio.h>

int main () {
  
  char array[10];
  
  return 0;
}
```

Contoh di atas akan mendeklarasikan string bernama array yang dapat menampung maksimal 10 karakter, termasuk null character.

Untuk menerima input string dari user, kita dapat menggunakan `scanf` atau `gets`. Perintah `scanf` akan membaca inputan string dari user dan berhenti ketika ada whitespace ataupun interupsi dari pengguna. Sedangkan `gets` akan membaca satu baris kumpulan karakter hingga enter atau interupsi dari pengguna.

Contoh source code penggunaan `scanf` untuk membaca string:
```c
#include <stdio.h>

int main () {
  
	char arr[10];
	while(1)
	{
		scanf("%s", arr);
		printf("-- %s\n", arr);
	}
	return 0;

}
```

Contoh penggunaan `gets` untuk membaca string:
```c
#include <stdio.h>

int main () {
  
	char arr[100];
	while(true)
	{
		gets(arr);
		
		printf("-- %s\n", arr);
	}
  return 0;

}
```
String yang dibaca dengan mengunakan `scanf` atau `gets` akan secara otomatis memiliki null character di akhir.

## Fungsi-Fungsi String

Dalam bahasa pemrograman C, terdapat library yang dibuat dengan tujuan memudahkan pengguna dalam mengolah string. Library tersebut tersimpan dalam `<string.h>`, oleh karena itu, untuk mengakses library ini, diperlukan tambahan preprocessor, yaitu:

```c
#include <string.h>
```

Berikut adalah fungsi-fungsi yang dibagi berdasarkan kegunaannya dalam mengolah sebuah string (diambil dari www.cplusplus.com):
- **Copying**
  + `memcpy` (Copy block of memory)
  + `memmove` (Move block of memory)
  + `strcpy` (Copy string)
  + `strncpy` (Copy characters from string)
- **Concatenation**
  + `strcat` (Concatenate strings)
  + `strncat` (Append character from string)
- **Comparison**
  + `memcmp` (Compare two blocks of memory)
  + `strcmp` (Compare two strings)
  + `strcoll` (Compare two strings using locale)
  + `strncmp` (Compare characters of two strings)
  + `strxfrm` (Transform string using locale)
- **Searching**
  + `memchr` (Locate character in block of memory)
  + `strchr` (Locate first occurrence of character in string)
  + `strcspn` (Get span until character in string)
  + `strpbrk` (Locate characters in string)
  + `strrchr` (Locate last occurrence of character in string)
  + `strspn` (Get span of character set in string)
  + `strstr` (Locate substring)
  + `strtok` (Split string into tokens)
- **Other**
  + `memset` (Fill block of memory)
  + `strerror` (Get pointer to error message string)
  + `strlen` (Get string length)

Berikut adalah beberapa fungsi dan penjelasannya.

### Fungsi `strcpy` 
```c
char * strcpy ( char * destination, const char * source );
```
Fungsi strcpy digunakan untuk melakukan **copy** dari sebuah string ke string lainnya. 
Contoh penggunaan dalam kode program:
```c
#include <stdio.h>
#include <string.h>

int main () {
  
	char a[] = "Halo";
	char b[10];
	
	// Copy string a ke string b
	strcpy(b, a);
	
	printf("%s\n", b);
	
	return 0;

}
```

### Fungsi `strcat` 
```c
char * strcat ( char * destination, const char * source );
```
Fungsi strcat digunakan untuk melakukan penempelan sebuah string pada **akhir** string yang lain. 
Contoh penggunaan dalam kode program:

```c
#include <stdio.h>
#include <string.h>

int main () {
  
	char a[] = "Halo";
	char b[] = " Kawan";
	char c[20];
	
	// Copy string a ke string b
	strcpy(b, a);
	
	// Tempelkan string b ke akhir string c
	strcat(c, b);
	
	printf("%s\n", c);
	
	return 0;

}
```

### Fungsi `strcmp`
```c
int strcmp ( const char * str1, const char * str2 );
```
Fungsi `strcmp` digunakan untuk melakukan **pembandingan** sebuah string dengan string yang lain. Return value dari fungsi ini dapat berupa bilangan negatif, nol ataupun positif. Jika fungsi ini mengembalikan nilai negatif, maka *str1* memiliki tingkat leksikografi lebih kecil dari *str2*. Sedangkan jika fungsi ini mengembalikan nilai postifi, maka *str1* memiliki tingkat leksikografi lebih besar dari *str2*. Terakhir, jika return value-nya nol, maka *str1* sama dengan *str2*. 

Berikut adalah contoh penggunaan fungsi ini dalam kode progam:
```c
#include <stdio.h>
#include <string.h>

int main () {
  
    char a[] = "Halo";
	char b[] = "Hai";
	char c[] = "Halo";
	
	if(strcmp(a, b) == 0) printf("String a sama dengan b\n");
	else printf("String a tidak sama dengan b\n");
	
	if(strcmp(a, c) == 0) printf("String a sama dengan c\n");
	else printf("String a tidak sama dengan c\n");
	
	return 0;

}
```

### Fungsi `strlen`
```c
size_t strlen ( const char * str );
```
Fungsi `strlen` digunakan untuk mengetahui **panjang** dari sebuah string.
```c
#include <stdio.h>
#include <string.h>

int main () {
  
	char a[] = "Halo";
	
	printf("Panjang string a adalah %d\n", strlen(a));
	
	return 0;

}
```

# Soal Latihan

## Soal 1

Buat program untuk mencari sebuah substring dalam string utama yang diberikan. Program harus mencari substring dalam string utama dan menghitung berapa kali substring tersebut muncul dalam string utama.

**Sample Input**

```
String utama: "Pemrograman adalah kunci keberhasilan. Pemrograman membuka pintu peluang."
Substring: "Pemrograman"
```

**Sample Output**

```
Substring "Pemrograman" muncul sebanyak 2 kali dalam string utama.
```


## Soal 2

Buatlah sebuah program untuk menghitung jumlah huruf vokal yang terdapat pada sebuah string S. Panjang string S tidak melebihi 100 karakter dan terdiri dari huruf lowercase, uppercase dan spasi.

**Sample Input**

```
Dasar Pemograman Keren
```

**Sample Output**

```
A/a : 4
I/i : 0
U/u : 0
E/e : 3
O/o : 1
```

## Soal 3

Diberikan sebuah nama variabel dalam bentuk **snake_case**. Buatlah program untuk mengubah nama variabel tersebut menjadi bentuk **camelCase**. Nama variabel hanya terdiri dari huruf lowercase, uppercase, dan simbol underscore.

**Sample Input 1**

```
skor_pemain
```

**Sample Output 1**

```
skorPemain
```

**Sample Input 2**

```
VariabEl_Satu
```

**Sample Output 2**

```
variabelSatu
```