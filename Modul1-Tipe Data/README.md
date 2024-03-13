![Screenshot 2024-03-13 102019](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/f88bf87e-7ade-4be6-8f8b-eb49ce51997d)# <h1 align="center">Laporan Praktikum Modul Tipe Data</h1>
<p align="center">Wahyu Hidayat</p>
<p align="center">2311102178 / 11-E-IF</p>


## Dasar Teori

Tipe Data adalah klasifikasi data berdasarkan jenisnya yang dibutuhkan oleh kompiler untuk mengelola pengunaan data tersebut. Ada beberapa jenis tipe data yang umum digunakan:
1. Tipe Data Primitif: ini adalah tipe data bawaan yang sudah ditentukan oleh sistem. contohnya:
   Int: untuk bilangan bulat.
   Float: untuk bilangan desimal.
   Char: untuk menyimpan karakter.
   Boolean: untuk menyimpan nilai kebenaran(true/false).
2. Tipe Data Abstrak: Tipe data abstrak (ADT) berisi berbagai tipe data yang berbeda. Fitur kunci di sini adalah penggunaan         struktur data seperti struct(dalam bahasa C) atau class (dalam C++), yang dapat membungkus beberapa tipe data sebagai anggota    didalamnya. perbedaan utama antara struct dan class adalah dalam tingkat akses defaultnya, di mana struct biasanya bersifat      publik dan class bersifat pribadi.
3. Tipe Data Koleksi.
   ini adalah tipe data yang digunakan untuk mengelompokkan dan menyimpan beberapa nilai atau objek secara bersamaan. beberapa      tipe data koleksi yang umum digunakan meliputi:
   Array: struktur data statis yang menyimpan elemen dengan tipe data yang sama dan memiliki ukuran tetap.
   Vector: Mirip dengan array, tetapi dapat menyesuaikan ukurannya secara dinamis dan memiliki berbagai fitur tambahan seperti      akses elemen, iterator, kapasitas, dan modifikasi.
   Map: Mirip dengan array, tetapi indeksnya dapat berupa tipe data selain integer dan menggunakan struktur data pohon              keseimbangan khusus seperti Red-Black Tree untuk penyimpanannya.
## Guided 

### 1. TIPE DATA PRIMITIF

```C++
#include <iostream>
using namespace std;

int main()
{
    char op;
    float num1, num2;
    cin >> op;
    cin >> num1 >> num2;
    switch (op)
    {
    case '+':
    cout <<num1 + num2;
    break;
    case '-':
    cout <<num1 - num2;
    break;
    case '*':
    cout <<num1 * num2;
    break;
    case '/':
    cout << num1 / num2;
    break;

    default:
    cout << "Error! operator is not correct";
    }
    return 0;
}

```
#### Output:

![Screenshot 2024-03-13 102019](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/f57da27e-cf91-4795-aa28-6f4596483dc8)

Kode di atas digunakan untuk mencetak teks "ini adalah file code guided praktikan" ke layar menggunakan function cout untuk mengeksekusi nya.

#### Full code Screenshot:
![Screenshot 2024-03-13 102004](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/dc316aa6-b050-48c4-984f-58c9862987ab)

Kode di atas digunakan untuk mencetak teks "ini adalah file code guided praktikan" ke layar menggunakan function cout untuk mengeksekusi nya.

## Unguided 

### 1. [Soal]

```C++
#include <iostream>
using namespace std;

int main() {
    cout << "ini adalah file code unguided praktikan" << endl;
    return 0;
}
```


## Kesimpulan
Ringkasan dan interpretasi pandangan kalia dari hasil praktikum dan pembelajaran yang didapat[1].

## Referensi
Karumanchi, N. (2016). Data Structures and algorithms made easy: Concepts,
problems, Interview Questions. CareerMonk Publications.
TylerMSFT. (n.d.). Collections (C++/CX). diakses dari
https://learn.microsoft.com/en-us/cpp/cppcx/collections-c-cx?view=msvc-170
