# <h1 align="center">Laporan Praktikum Modul Tipe Data</h1>
<p align="center">Wahyu Hidayat</p>
<p align="center">2311102178 / 11-E-IF</p>


## Dasar Teori

Array atau dalam bahasa indonesia disebut larik, merupakan sebuah teknik pemrograman di mana array tersebut dianalogikan sebagai wadah untuk menyimpan data-data yang berjumlah banyak dan memiliki tipe data yang sama. 
Adapun Array terbagi menjadi bebrapa jenis, yaitu :

1. Array satu dimensi adalah kumpulan data dengan tipe yang sama yang disusun dalam satu baris. Setiap elemen memiliki indeks yang dimulai dari 0 hingga jumlah elemen dikurangi satu.

2. Array dua dimensi adalah variabel yang terdiri dari kumpulan array satu dimensi dengan tipe yang sama yang disusun dalam baris dan kolom. Setiap elemen memiliki dua indeks: indeks baris dan indeks kolom.

3. Array multidimensi memiliki kapasitas memori yang lebih besar dan digunakan untuk merepresentasikan array dengan dimensi lebih dari dua atau array yang memiliki lebih dari dua indeks, seperti array tiga dimensi, array empat dimensi, dan seterusnya.

### 1. Program Input Array Tiga Dimensi

```C++
#include <iostream>
using namespace std;

//program input array 3 dimensi
int main(){
    //deklarasi array
int arr[2][3][3];
//input elemen
for  (int x = 0; x < 2; x++){

for (int y = 0; y < 3; y++){
    for (int z = 0; z< 3; z++){
        cout << "Input Array [" << x <<"]["<< y <<"][" << z <<"]=";
        cin >> arr[x][y][z];
    }
}
cout <<endl;
}
// Output Array
for (int x = 0; x < 2; x++){
    for (int y = 0; y< 3; y++){
    for (int z = 0; z < 3; z++){
        cout << "Data Array["<< x <<"]["<< y <<"]["<< z <<"]=" << arr [x][y][z] <<endl;
    }
    }
}
 cout <<endl;
 //Tampilan Array 
 for (int x =0; x<2; x++){
    for (int y = 0; y < 3; y++){
        for (int z =0; z<3; z++ ){
            cout << arr [x][y][z]<<endl;
        }
        cout <<endl;
    }
    cout<<endl;
 }


}

```
#### Output:

![Screenshot 2024-03-19 094234](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/4d092f5b-2f98-49e7-8f80-759116b63174)

Kode di atas menggunakan array tiga dimensi untuk menyimpan data. program ini mengisi array dengan input dari pengguna menggunakan loop bersarang tiga tingkat, kemudian mencetak nilai elemen array tersebut dalam berabgai format, termasuk satu per satu dan dengan memisahkan setiap lapisan dan baris array.

#### Full code Screenshot:

![Screenshot 2024-03-19 094225](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/7c86e237-3d63-4581-a1b3-1c16599782be)

### 2. Program Mencari Nilai Maksimal pada Array
```C++
#include <iostream>
using namespace std;
int main(){
    int maks, a, i=1, lokasi;
    cout << "Masukkan Panjang : ";
    cin >> a;
    int array [a];
    cout << "Masukkan "<< a << " angka\n";
    for(i = 0; i < a; i++)
    {
        cout <<"Array ke-" << (i)<< ":";
        cin>> array[i];
    }
    //penjelasan tentang mencari nilai terbesar / searching
    maks = array[0]; // nilai maksimal nya indeks ke 0
    for (i = 0; i < a; i++) 
    {
        if (array[i] > maks) // jika array indeks ke 0 bernilai 1 >  nilai maksimal indeks ke 0
        {
            maks = array[i]; //jika tidak terpenuhi maka melakukan update terhadap perulangan sampai selesai sebanyak 5 indeks
            lokasi = i;
        }
    }
    cout<< "Nilai Maksimum Adalah " << maks << " berada di Array ke " << lokasi << endl;
}
```
#### Output:

![Screenshot 2024-03-19 095026](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/ff88dce0-3761-4593-9b05-4db86f1127d0)

Kode di atas meminta untuk memasukkan panjang array dan sejumlah angka. setelah itu, program menyimpan angka-angka tersebut ke dalam array dan mencari nilai maksimumnya. proses pencarian nilai maksimum dilakukan dengan menggunakan perulangan untuk membandingkan setiap elemen array dengan nilai maksimum yang disimpan secara sementara, jika nilai elemen tersebut lebih besar dari nilai maksimum sementara, maka nilai maksimum akan diupdate dengan nilai elemen tersebut dan lokasi indeksnya akan disimpan. setelah selesai, program akan menampilkan nilai maksimum beserta indeksnya dalam array.

#### Full code Screenshot:
![Screenshot 2024-03-19 095014](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/ae617c2f-228e-40e6-bafd-113b580c7d52)

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
