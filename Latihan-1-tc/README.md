## Daftar Isi

- [Latihan Soal 1 (Pengenalan Bahasa C & Percabangan)](#Latihan-Soal-1-(Pengenalan-Bahasa-C-&-Percabangan))
    + [Soal 1.1](#Soal-1.1)
    + [Soal 1.2](#Soal-1.2)
    + [Soal 1.3](#Soal-1.3)
    + [Soal 1.4](#Soal-1.4)


# Latihan Soal 1 

## Soal 1.1
Fred adalah seorang astronot yang sedang bertugas pergi ke planet Mars. Dimana satu tahun di Mars sama dengan 672 hari di Bumi. Karena kebutuhan penelitian, saat Fred berada di Mars, dia memakai penanggalan planet Mars yang bernama Marso. Dimana 1 tahun Marso terdapat 8 bulan, 1 bulan terdapat 7 minggu, dan 1 minggu terdapat 12 hari. Semua bulan di penanggalan Marso mempunyai jumlah tanggal yang sama, dan tidak ada tahun kabisat dalam planet Mars. Supaya Fred tidak bingung untuk melaporkan penelitiannya ke Bumi, Bantulah Fred untuk membuat program konversi penanggalan Marso ke Masehi.

Jika Fred berangkat tanggal 29 Februari 2020 dan tiba di Mars pada hari yang sama. Maka input yang diberikan adalah lama Fred berada di Mars, semenjak keberangkatannya dari Bumi, dengan 

Format Input : "<Hari Marso> Hari <Bulan Marso> Bulan <Tahun Marso> Tahun"
Format Output : "Sekarang di Bumi tanggal dd-mm-yy"

Contoh Input 1 :
```c
45 Hari 7 Bulan 1 Tahun
```

Contoh Output 1 :
```c
Sekarang di Bumi tanggal 29-09-2023
```

Contoh Input 2 :
```c
9 Hari 2 Bulan 0 Tahun
```

Contoh Output 2 :
```c
Sekarang di Bumi tanggal 24-08-2023
```


## Soal 1.2
![Image 1.1](https://github.com/JagoTeknikCourse/Modul-Dasprog/blob/main/img/Chaesar-Chiper-img.png)

Rudeus adalah seorang hacker terkenal. Suatu hari dia mendapatkan data berisikan nomor telepon penduduk Wakanda, namun masih terenkripsi dengan baik. Karena Rudeus ingin mendekript data tersebut, ia menemukan bahwa enkripsi yang digunakan adalah algoritma Caesar Chiper. Chaesar Chiper adalah algoritma dengan menggeser nilai ASCII dengan offset tertentu. Bantulah Rudeus membuat program mendekript data-data tersebut. Anggap semua data nomor telepon yang ada berdigit 12 semua.

N : Nomor Telepon Terenkripsi
O : Offset Shifting

0 < N < 999999999999
0 < O < 11

Format Input : "<Nomor Telepon Terenkripsi> <Offset Shifting>"
Format Output : "<Nomor Telepon Sebenarnya>"

Contoh Input 1 :
```c
536012447825 5
```

Contoh Output 1 :
```c
081567992370
```

Contoh Input 2 :
```c
752557064923 7
```

Contoh Output 2 :
```c
085880397256
```