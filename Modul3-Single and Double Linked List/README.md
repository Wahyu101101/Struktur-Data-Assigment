# <h1 align="center">Laporan Praktikum Modul Single and Double Linked List</h1>
<p align="center">Wahyu Hidayat</p>
<p align="center">2311102178 / 11-E-IF</p>


## Dasar Teori
###Linked List

Linked List dalam ilmu komputer merupakan sebuah struktur data yang digunakan untuk menyimpan sejumlah objek data biasanyan secara terurut sehingga memungkinkan penambahan, pengurangan, dan pencarian data atas elemen data yang tersimpan dalam senarai dilakukan secara lebih efektif. Pada praktiknya sebuah struktur data memiliki elemen yang digunakan untuk saling menyimpan rujukan antara satu rujukan dengan lainnya sehingga membentuk sebuah senarai abstrak, tiap – tiap elemen yang terdapat pada senarai abstrak ini seringkali disebut sebagai node karena mekanisme rujukan yang saling terkait inilah disebut sebagai senarai berantai[1]. Linked List (Senarai berantai) Senarai berantai(bahasa Inggris:linked list) atau kadang-kadang disebut dengan senarai bertaut atau daftar bertaut dalam ilmu computer merupakan sebuah struktur data yang digunakan untuk menyimpan sejumlah objek data biasanya secara terurut sehingga memungkinkan penambahan, pengurangan, dan pencarian atas elemen data yang tersimpan dalam senarai dilakukan secara lebih efektif[2].

![Screenshot 2024-03-26 101435](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/5e8e422f-2045-41cd-b0be-4c9af1fe88ec)


Linked List merupakan bentuk struktur data paling umum dan sederhana yang banyak digunakan untuk mengimplementasikan model struktur data lainnya, termasuk antrian, stack ataupun larik assosiatif. Linked List terdiri dari :

1. Single Linked List
Single Linked List adalah suatu kumpulan elemen data (yang disebut sebagai node) dimana urutannya ditentukan oleh suatu pointer. Single Linked List hanya memiliki 1 (satu) petunjuk/pointer (NEXT). Setiap elemen (node) dari suatu linked list terdiri atas dua bagian,
yaitu :
   A. INFO : berisi informasi tentang elemen data yang bersangkutan.
   B. NEXT (link field/next pointer field) : berisi alamat dari elemen (node) selanjutnya yang dituju.
Berikut ini sebuah contoh Single Linked List yang terdiri atas 4 node :

![Screenshot 2024-03-26 101744](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/7ef26062-b355-4832-94d7-a886f6cad408)

Pada node ke-4 field NEXT-nya berisi NULL, artinya node ke-4 tersebut adalah node terakhir.

2. Double Linked List
Pada Double Linked List, struktur data atas tiap-tiap node memiliki rujukan pada node sebelum (PREV) dan berikutnya (NEXT). Sebagian algoritma membutuhkan taut ganda, contohnya sorting dan reverse traversing.

![Screenshot 2024-03-26 102012](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/0dcbafd9-7905-4906-95f6-c172c37bb6ee)

Tiap node memiliki pointer yang menunjuk ke node sesudahnya dan pointer yang menunjuk ke node sebelumnya.
Keterangan:
Node Sesudahnya : Next(Node)
Node sebelumnya : Prior(Node)
Next(Prior(P)) = P dan P = Prior(next(P))
Double Linked List Kosong :

![Screenshot 2024-03-26 102603](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/f3d1098e-cd3b-4108-9246-588de4fc3552)

Keterangan:
next Prior(Head) = Head
Next(Head) = Head
Operasi pada Single Linked List dan Double Linked List:
1. Sisip Depan : menyisipkan node baru pada bagian awal node atau head dari Single Linked List.
2. Sisip Belakang : menyisipkan node baru pada bagian belakang node dari Single Linked List.
3. Sisip Posisi : menyisipkan node baru pada posisi tertentu dari Single Linked List.
4. Hapus Posisi : menghapus node baru pada posisi tertentu dari Single Linked List





## Guided 
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
![Screenshot 2024-03-19 115607](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/4c0ba241-57e6-4426-a3d8-34eebc0929e1)


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

### 1. Buatlah program untuk menampilkan Output seperti berikut dengan data yang diinputkan oleh user!
Data Array : 1  2 3 4 5 6 7 8 9 10
Nomor Genap : 2, 4, 6, 8, 10,
Nomor Ganjil : 1, 3, 5, 7, 9,

```C++
#include <iostream>
#include <vector>
using namespace std;

int main(){
    int maks, a, i = 1, lokasi;
    cout <<"Masukkan Panjang : ";
    cin >> a;
    int array[a];
    cout<< "Masukkan "<< a << " angka\n";
    for(i = 0; i < a; i++){
        cout<< "Array ke-" << (i + 1)<< ": ";
        cin >> array[i];
    }
    
    //Menampilkan data array
    cout<< "Data Array: ";
    for (i = 0; i < a; i++){
        cout << array[i]<< " ";
    }
    cout <<endl;
    
    //Menampilkan nomor genap
    cout<< "Nomor Genap: ";
    for(i = 0; i < a; i++){
        if (array[i] % 2 == 0){
            cout << array[i] << ", ";
        }
    }
    cout <<endl;

    //Menampilkan nomor ganjil
    cout << "Nomor Ganjil: ";
    for (i = 0; i < a; i++){
        if (array[i] % 2 != 0){
            cout << array[i] << ", ";
        }
    }
    cout <<endl;

    return 0;
}
```
#### Output:

![Screenshot 2024-03-19 101910](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/79a8b3b3-207f-4ef1-b745-db348a1d29ea)

Kode di atas meminta untuk memasukkan panjang array dan elemen-elemennya. Setelah menerima input, program menampilkan data array tersebut, serta memisahkan nomor genap dan ganjil dari array tersebut, kemudian menampilkan keduanya secara terpisah. Ini dilakukan dengan menggunakan perulangan untuk mengakses setiap elemen array dan memeriksa apakah mereka genap atau ganjil menggunakan operator modulus. Hasilnya adalah output yang mencakup data array, nomor genap, dan nomor ganjil berdasarkan input.

#### Full code Screenshot:
![Screenshot 2024-03-19 101901](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/382fe6d8-21b6-40cd-80c4-550b86426157)

### 2. Buatlah program Input array tiga dimensi (seperti pada guided) tetapi jumlah atau ukuran elemennya diinputkan oleh user!
```C++
#include <iostream>
using namespace std;

int main(){
    int x_ukuran, y_ukuran, z_ukuran;

    //Meminta pengguna untuk memasukkan ukuran array
    cout << "Memasukkan jumlah elemn untuk dimensi X: ";
    cin >> x_ukuran;
    cout << "Memasukkan jumlah elemn untuk dimensi Y: ";
    cin >> y_ukuran;
    cout << "Memasukkan jumlah elemn untuk dimensi Z: ";
    cin >> z_ukuran;

    //Deklarasi array tiga dimensi
    int arr[x_ukuran][y_ukuran][z_ukuran];

    //input elemen array
    for (int x = 0; x < x_ukuran; x++){
        for (int y = 0; y < y_ukuran; y++){
            for (int z = 0; z < z_ukuran; z++){
            cout << "Inputkan Array[" << x << "][" << y << "][" << z << "]: ";
            cin >> arr[x][y][z];
            }
        }
    }

    //Menampilkan array 
    cout << "Array yang Diinputkan:\n";
    for (int x = 0; x < x_ukuran; x++){
        for (int y = 0; y < y_ukuran; y++){
            for (int z = 0; z < z_ukuran; z++){
            cout << "Data Array[" << x << "][" << y << "][" << z << "]: " << arr[x][y][z] << endl;
            }
        }
    }

return 0;
}
```
#### Output:
![Screenshot 2024-03-19 105711](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/d94f0389-5004-4050-8a09-dea4bc4309cc)

Kode di atas digunakan untuk menginisialisasi, mengisi, dan menampilkan array tiga dimensi berdasarkan input ukuran dari pengguna. Program akan meminta untuk memasukkan ukuran untuk setiap dimensi array, kemudian akan mengalokasikan array sesuai dengan ukuran yang dimasukkan. Selanjutnya, program meminta untuk memasukkan nilai untuk setiap elemen array menggunakan nested loop. Setelah semua nilai dimasukkan, program akan menampilkan nilai dari setiap elemen array bersama dengan koordinatnya dalam format "[x][y][z]: nilai".
#### Full code Screenshot:
![Screenshot 2024-03-19 105659](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/5a2545a9-213a-47ab-9b94-1177bbf5e3d8)


### 3. Buatlah program menu untuk mencari nilai Maksimum, Minimum dan Nilai rata – rata dari suatu array dengan input yang dimasukan oleh user!
```C++
#include <iostream>
using namespace std;

int main(){
    int a;
    cout << "Masukkan Panjang Array: ";
    cin >> a;

    int array[a];
    cout << "Masukkan " << a << " angka:\n";
    for (int i = 0; i < a; i++){
        cout << "Array ke-" << (i+1) << ": ";
        cin >> array[i];
    }
    int menu;
    do{
        cout << "\nMenu\n";
        cout << "1. Cari Nilai Maksimum\n";
        cout << "2. Cari Nilai Minimum\n";
        cout << "3. Cari Nilai Rata-rata\n";
        cout << "0. Keluar\n";
        cout << "Pilih Operasi: ";
        cin >> menu;
    
    switch (menu){
        case 1: {
            int maks = array[0];
            for (int i = 1; i < a; i++ ){
                if (array[i] > maks){
                    maks = array[i];
                }
            }
            cout << "Nilai Maksimum Adalah " << maks <<endl;
            break;
        }
         case 2: {
            int min = array[0];
            for (int i = 1; i < a; i++ ){
                if (array[i] < min){
                    min = array[i];
                }
            }
            cout << "Nilai Minimum Adalah " << min <<endl;
            break;
        }
        case 3: {
            int sum = 0;
            for (int i = 0; i < a; i++ ){
                sum += array[i];

                }
                double rata = static_cast<double>(sum)/a;
                cout << "Nilai Rata-rata Adalah " << rata <<endl;
                break;
            }
            case 0: 
            cout << "Terima Kasih, Program selesai.\n";
            break;
            default :
            cout << "Pilihan tidak valid, silahkan pilih lagi.\n";
            }
    }while (menu != 0);
    return 0;
}

```
#### Output:
![Screenshot 2024-03-19 114137](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/3935d471-5bc0-47c8-8b3b-5c1b82b2a1be)

Kode diatas digunakan untuk memasukkan panjang sebuah array serta elemen-elemennya. Kemudian, program menampilkan sebuah menu yang memberikan opsi kepada pengguna untuk melakukan operasi tertentu, seperti mencari nilai maksimum, minimum, atau nilai rata-rata dari array yang dimasukkan. Setelah pengguna memilih sebuah operasi, program akan melakukan perhitungan sesuai dengan pilihan pengguna dan menampilkan hasilnya. Program akan terus menampilkan menu hingga pengguna memilih untuk keluar dengan memilih opsi "0".
#### Full code Screenshot:
![Screenshot 2024-03-19 114257](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/6dc479f7-2857-4ad8-b82a-b6b877c4c11c)

## Kesimpulan
Kesimpulannya, kode-kode tersebut menunjukkan penggunaan array dalam berbagai konteks dan dimensi. Array digunakan sebagai wadah untuk menyimpan data dengan tipe yang sama, dan setiap elemen diakses menggunakan indeks. Array satu dimensi digunakan untuk menyimpan data dalam satu baris, sedangkan array dua dimensi digunakan untuk menyusun data dalam baris dan kolom. Selain itu, ada juga array multidimensi yang digunakan untuk menyimpan data dengan dimensi lebih dari dua. Program-program tersebut memanfaatkan array untuk berbagai tujuan, seperti menyimpan dan mengolah data, mencari nilai maksimum, minimum, dan rata-rata, serta memisahkan data genap dan ganjil. Dengan menggunakan array, program-program tersebut dapat melakukan operasi secara efisien dan terstruktur sesuai dengan kebutuhan pengguna.
## Referensi
Putra, Muhammad Taufik Dwi, Deden Pradeka, and Ana Rahma Yuniarti. "BELAJAR DASAR PEMROGRAMAN DENGAN C++." (2022).

