# <h1 align="center">Laporan Praktikum Modul Tipe Data</h1>
<p align="center">Wahyu Hidayat</p>
<p align="center">2311102178 / 11-E-IF</p>


## Dasar Teori

Array atau dalam bahasa indonesia disebut larik, merupakan sebuah teknik pemrograman di mana array tersebut dianalogikan sebagai wadah untuk menyimpan data-data yang berjumlah banyak dan memiliki tipe data yang sama. 
Adapun Array terbagi menjadi bebrapa jenis, yaitu :

1. Array satu dimensi adalah kumpulan data dengan tipe yang sama yang disusun dalam satu baris. Setiap elemen memiliki indeks yang dimulai dari 0 hingga jumlah elemen dikurangi satu.

2. Array dua dimensi adalah variabel yang terdiri dari kumpulan array satu dimensi dengan tipe yang sama yang disusun dalam baris dan kolom. Setiap elemen memiliki dua indeks: indeks baris dan indeks kolom.

3. Array multidimensi memiliki kapasitas memori yang lebih besar dan digunakan untuk merepresentasikan array dengan dimensi lebih dari dua atau array yang memiliki lebih dari dua indeks, seperti array tiga dimensi, array empat dimensi, dan seterusnya.

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

Kode diatas merupakan sebuah program aritmatika sederhana yang meminta pengguna untuk memasukkan operator matematika seperti pertambahan, pengurangan, pembagian dan perkalian antara kedua bilangan. jika operator yang dimasukkan tidak sesuai, maka program mengirimkan pesan "Error! operator is not correct".

#### Full code Screenshot:
![Screenshot 2024-03-13 102004](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/dc316aa6-b050-48c4-984f-58c9862987ab)

### 2. TIPE DATA ABSTRAK

```C++
#include <stdio.h>

struct Mahasiswa 
{
    const char *name;
    const char *address;
    int age;
};

 int main ()
 {
    struct Mahasiswa mhs1, mhs2;
    mhs1.name = "Dian";
    mhs1.address = "Mataram";
    mhs1.age = 22;
    mhs2.name = "Bambang";
    mhs2.address ="Surabaya";
    mhs2.age = 23;

    printf("## Mahasiswa 1 ##\n");
    printf("Nama: %s\n", mhs1.name);
    printf("Alamat: %s\n", mhs1.address);
    printf("Umur: %d\n", mhs1.age);
    printf("## Mahasiswa 2 ##\n");
    printf("Nama: %s\n", mhs2.name);
    printf("Alamat: %s\n", mhs2.address);
    printf("Umur: %d\n", mhs2.age);
    return 0;

 }
```
#### Output:
![Screenshot 2024-03-13 103529](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/e3b0916b-5d66-4d41-b7ac-025f8cf73f83)

Kode di atas digunakan untuk mendefinisikan struktur "Mahasiswa" dan menginisialisasikan nilai-nilai anggota struktur untuk masing-masing mahasiswa. setelah itu, program mencetak informasi masing-masing mahasiswa ke layar menggunakan fungsi "printf".

#### Full code Screenshot:
![Screenshot 2024-03-13 103516](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/720931c1-59f3-42cc-a7f3-d9761d21a6bd)

### 3. TIPE DATA KOLEKSI

```C++
#include <iostream>
using namespace std;
int main()
{
    int nilai[5];
    nilai[0] = 23;
    nilai[1] = 50;
    nilai[2] = 34;
    nilai[3] = 78;
    nilai[4] = 90;

    cout << "Isi Array pertama :" << nilai[0] <<endl;
    cout << "Isi Array kedua :" << nilai[1] <<endl;
    cout << "Isi Array ketiga :" << nilai[2] <<endl;
    cout << "Isi Array keempat :" << nilai[3] <<endl;
    cout << "Isi Array kelima :" << nilai[4] <<endl;
    return 0;
}

```
#### Output:
![Screenshot 2024-03-13 103610](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/8eb934ba-5a93-4179-be55-2ad74176d65c)

Kode di atas digunakan untuk mendemonstrasikan penggunaan array. program ini membuat sebuah array bernama "nilai' dengan ukuran 5, kemudian menginisialisasikan setiap elemen array dengan nilai tertentu. selanjutnya, program mencetak isi masing-masing elemen array ke layar menggunakan  perintah "cout".

#### Full code Screenshot:
![Screenshot 2024-03-13 103547](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/43eb94f5-9c5d-48c1-bbea-3967459477b1)

## Unguided 

### 1. Buatlah program menggunakan tipe data primitif minimal dua fungsi dan bebas. Menampilkan program, jelaskan program tersebut dan ambil kesimpulan dari materi tipe data primitif!

```C++
#include <iostream>
using namespace std;
void tambah(int a, int b) {
    int hasil = a + b;
    cout << "Hasil Penjumlahan: " << hasil <<endl;
}

void kali(double x, double y) {
    double hasil = x*y;
    cout << "Hasil Perkalian: " << hasil <<endl;
}

int main(){
    int bilangan1 = 5;
    int bilangan2 = 3;
    double bilangan3 = 2.5;
    double bilangan4 = 1.5;

    tambah(bilangan1, bilangan2);
    kali(bilangan3, bilangan4);

    return 0;
}
```
#### Output:
![Screenshot 2024-03-13 115019](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/4ec6adce-56fc-4e7d-b46c-7bd7daeb6248)
Kode tersebut merupakan contoh sederhana penggunaan tipe data primitif int dan double. kode ini memiliki dua fungsi 'tambah()' untuk menjumlahkan dua bilangan bulat dan 'kali()' untuk mengalikan dua bilangan rill.
kesimpulannya, tipe data primitif sangat penting dalam pemprograman karena menyediakan dasar untuk melakukan operasi matematika dan manipulasi data dalam program. dalam contoh ini, int digunakan untuk bilangan bulat dan double untuk bilangan rill. program tersebut menunjukkan cara menggunakan tipe data primitif untuk melakukan operasi matematika dasar seperti penjumlahan dan perkalian.
#### Full code Screenshot:
![Screenshot 2024-03-13 115009](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/ffd26eed-528b-4841-87af-8901c62e0a14)

### 2. Jelaskan fungsi dari class dan struct secara detail dan berikan contoh programnya.
## Class
```C++
#include <iostream>
#include <string>
using namespace std;

class Mahasiswa {
    private:
    string nama;
    int umur;
    
    public:
    Mahasiswa(string n, int u){
        nama = n;
        umur = u;
    }


void tampilkanData(){
    cout << "Nama : " << nama << ", Umur: " << umur << " tahun" <<endl;
}
};

int main(){
    Mahasiswa mhs1("Wahyu Hidayat", 20);
    Mahasiswa mhs2("Nor Jatil Hasanah", 21
    );

    mhs1.tampilkanData();
    mhs2.tampilkanData();
    return 0;
}
```
#### Output:

![Screenshot 2024-03-13 115304](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/a103bb82-2e6e-4afe-9fef-fa2aff611e0a)

Kode di atas digunakan untuk mendefinisikan sebuah kelas 'Mahasiswa'. kelas ini memiliki dua atribut: 'nama' (bertipe string) dan 'umur' (bertipe integer), serta memiliki satu metode publik 'tampilanData()' yang digunakan untuk mencetak nama dan umur mahasiswa ke layar. didalam fungsi 'main', dua objek dari kelas 'Mahasiswa' dibuat dengan menggunakan konstruktor, yang menginisialisasi nama dan umur masing-masing mahasiswa. kemudian, metode 'tampilanData()' dipanggil untuk setiap objek, sehingga informasi nama dan umur dari kedua mahasiswa akan ditampilkan ke layar.

#### Full code Screenshot:
![Screenshot 2024-03-13 115254](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/428506aa-231e-449e-9a0e-1d0f26bbeb0b)

## Struct
```C++
#include <iostream>
#include <string>
using namespace std;

struct Mahasiswa {
    string nama;
    int umur;
    
    Mahasiswa(string n, int u){
        nama = n;
        umur = u;
    }


void tampilkanData(){
    cout << "Nama : " << nama << ", Umur: " << umur << " tahun" <<endl;
}
};

int main(){
    Mahasiswa mhs1("Wahyu Hidayat", 20);
    Mahasiswa mhs2("Nor Jatil Hasanah", 21);

    mhs1.tampilkanData();
    mhs2.tampilkanData();
    return 0;
}
```
#### Output:
![Screenshot 2024-03-13 115734](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/eda2d3a0-2b15-4ecb-873c-adeb3b5b570f)

kode diatas menggunakan struktur (struct) bernama 'Mahasiswa' untuk merepresentasikan data mahasiswa. struktur ini memiliki dua atribut: nama(bertipe string) dan umur(bertipe integer), serta sebuah konstruktor yang menginisialisasi nilai 'nama' dan 'umur' saat objek 'Mahasiswa' dibuat. selain itu, terdapat pula sebuah fungsi 'tampilanData()' yang mencetak informasi nama dan umur mahasiswa ke layar.
#### Full code Screenshot:
![Screenshot 2024-03-13 115724](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/8b4da5b4-1088-42dc-9af2-f4bf6098f064)

### 3. Buat dan jelaskan program menggunakan fungsi map dan jelaskan perbedaan dari array dengan map.
```C++
#include <iostream>
#include <map>
using namespace std;

int main(){
    map<string, int > umur;

    umur["Wahyu"] = 20;
    umur["Hasanah"] = 21;
    umur["supra"] = 22;
    cout << "Umur Wahyu : " << umur["Wahyu"] << " tahun" <<endl;
    cout << "Umur Hasanah : " << umur["Hasanah"] << " tahun" <<endl;
    cout << "Umur supra : " << umur["supra"] << " tahun" <<endl;

}
```
#### Output:
![Screenshot 2024-03-13 115758](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/d1d4ff39-6ab5-4b0f-a426-0d6c4c147080)

Kode di atas menggunakan struktur data 'map' untuk menyimpan pasangan kunci-nilai. dalam hal ini, kunci adalah nama(bertipe string) dan nilai adalah umur (bertipe integer) dari seseorang. tiga pasangan kunci-nilai dimasukkan ke dalam 'map'. kemudian, program mencetak umur dari tiga orang yang berbeda ke layar dengan mengakses nilai-nilai yang sesuai dari 'map'.

#### Full code Screenshot:
![Screenshot 2024-03-13 115751](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/3d758f39-ca7f-47c6-adf6-8f603e076749)

## Kesimpulan
dari materi ini dapat disimpulkam bahwa tipe data terdiri dari data primitif, abstrak dan juga koleksi untuk menyimpan nilai dan adapula class dan struct digunakan untuk mengelompokkan data dan fungsi terkait kedalam satu kesatuan. begitu juga fungsi map berguna untuk menyimpan pasangan kunci-nilai yang dapat diakses dengan efesien. serta yang terakhir array cocok untuk menyimpan kumpulan data dengan indeks yang berurutan, sementara map lebih fleksibel dalam hal penugasan indeks.
## Referensi
Karumanchi, N. (2016). Data Structures and algorithms made easy: Concepts,
problems, Interview Questions. CareerMonk Publications.
TylerMSFT. (n.d.). Collections (C++/CX). diakses dari
https://learn.microsoft.com/en-us/cpp/cppcx/collections-c-cx?view=msvc-170
