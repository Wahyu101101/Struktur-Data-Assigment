<p align="center">Wahyu Hidayat</p>
<p align="center">2311102178 / 11-E-IF</p>


## Dasar Teori

## **Graph dan Tree**

#### Pengertian Graph/graf
**Graf**(graph) adalah struktur data yang terdiri dari kumpulan node (vertex) dan sisi (edge) yang menghubungkan node-node tersebut. Graf dapat digunakan untuk merepresentasikan hubungan antara objek-objek tertentu dalam berbagai bidang seperti jaringan sosial, jaringan komputer, kimia, dan banyak lagi [1][2][3].
- **Graf atau graph** adalah struktur data yang digunakan untuk merepresentasikan hubungan antara objek dalam bentuk node atau vertex dan sambungan antara node tersebut dalam bentuk sisi atau edge[6]. Graf terdiri dari simpul dan busur yang secara matematis dinyatakan sebagai :
- G = (V, E)
Dimana G adalah Graph, V adalah simpul atau vertex dan E sebagai sisi atau edge. Dapat digambarkan:

![Screenshot 2024-05-26 061254](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/53a68266-1656-4534-ac51-233d1c6caed3)

Elemen-elemen dalam Graf:

  <img src="https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/2dcc3d0a-1513-420b-9694-11e1add40f2e" alt="Screenshot 2024-05-26 062321" width="300" style="display: block; margin: 0 auto;"/>
- Node (Vertex): Node merupakan objek yang terhubung dalam graf. Setiap node dapat memiliki nilai atau data tertentu. Node dapat mewakili berbagai entitas seperti orang, lokasi, atau objek lainnya. Dalam beberapa kasus, node juga dapat memiliki atribut tambahan seperti label atau warna. [3][4]

  ![images](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/a6a388cb-1c0d-4436-9daa-d0553c76db91)
  
- Sisi (Edge): Sisi adalah garis yang menghubungkan sepasang node dalam graf. Sisi dapat memiliki bobot (weight) atau tidak memiliki bobot. Bobot sisi dapat merepresentasikan jarak, biaya, atau kekuatan hubungan antara node. Sisi juga dapat memiliki atribut tambahan seperti label atau warna. [3][4]

  ![images](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/a180f22c-537d-4fc0-94ca-36b9e972810f)

- Adjacency: Dua node dikatakan adjacent (bertetangga) jika terhubung langsung oleh sisi. Sebuah node dapat memiliki beberapa node tetangga yang terhubung dengannya. Dalam graf berarah, sebuah node dapat memiliki node tetangga masuk (in-neighbors) dan node tetangga keluar (out-neighbors). [3][4]

  ![images](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/7571876b-3056-4112-9b23-8a2038261858)

- Derajat (Degree): Derajat suatu node adalah jumlah sisi yang terhubung dengan node tersebut. Dalam graf berarah, terdapat derajat masuk (in-degree) dan derajat keluar (out-degree). Dalam graf tidak berarah, derajat sebuah node adalah jumlah sisi yang terhubung dengannya. [1][4]

  ![images](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/0bbd5f3b-394c-475c-924d-f3fbc39c8bdf)

- Lintasan (Path): Lintasan adalah urutan node-node yang terhubung oleh sisi dalam graf. Panjang lintasan adalah jumlah sisi yang ada dalam lintasan tersebut. [1][4]

  ![images](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/50f4f598-463d-4058-8447-b29137069d6c)

- Siklus (Cycle): Siklus adalah lintasan di mana node awal dan node akhir adalah sama. Siklus tidak diperbolehkan dalam struktur data pohon (tree). [1][4]



Pencarian (Searching) yaitu proses menemukan suatu nilai tertentu pada kumpulan data. Hasil pencarian adalah salah satu dari tiga keadaan ini: data ditemukan, data ditemukan lebih dari satu, atau data tidak ditemukan. Searching juga dapat dianggap sebagai proses pencarian suatu data di dalam sebuah array dengan cara mengecek satu persatu pada setiap index baris atau setiap index kolomnya dengan menggunakan teknik perulangan untuk melakukan pencarian data[6].

Terdapat beberapa algoritma pencarian yang umum digunakan, antara lain:
#### 1. Sequential Search
Sequential Search merupakan salah satu algoritma pencarian data yang biasa digunakan untuk data yang berpola acak atau belum terurut. Sequential search juga merupakan teknik pencarian data dari array yang paling mudah, dimana data dalam array dibaca satu demi satu dan diurutkan dari index terkecil ke index terbesar, maupunsebaliknya. Konsep Sequential Search yaitu:
  1) Membandingkan setiap elemen pada array satu per satu secara berurut
  2) Proses pencarian dimulai dari indeks pertama hingga indeks terakhir.
  3) Proses pencarian akan berhenti apabila data ditemukan. Jika hingga akhir array data masih juga tidak ditemukan, maka proses pencarian tetap akan dihentikan.
  4) Proses perulangan pada pencarian akan terjadi sebanyak jumlah N elemen pada array.

#### Algoritma pencarian berurutan dapat dituliskan sebagai berikut :
1) i ← 0
2) ketemu ← false
3) Selama (tidak ketemu) dan (i <= N) kerjakan baris 4
4) Jika (Data[i] = x) maka ketemu ← true, jika tidak i ← i + 1
5) Jika (ketemu) maka i adalah indeks dari data yang dicari, jika tidak data tidak ditemukan.

#### Di bawah ini merupakan fungsi untuk mencari data menggunakan pencarian sekuensial.

```C++
int SequentialSearch (int x)  
{  
    int i = 0;  
    bool ketemu = false;  
    while ((!ketemu) && (i<Max))K  
        if (Data[i] == x)  
            ketemu = true;  
        else  
            i++;  
    }  
        if (ketemu)  
            return i;  
        else  
            return -1;

```
Fungsi diatas akan mengembalikan indeks dari data yang dicari. Apabila data tidak ditemukan maka fungsi diatas akan mengembalikan nilai –1. Contoh dari Sequential Search, yaitu:
- Int A[8] = {9,1,5,2,7,6,11,3}
![Screenshot 2024-05-22 141058](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/a7230ace-8151-4df2-bbe7-1ed6af991138)


Misalkan, dari data di atas angka yang akan dicari adalah angka 7 dalam array
A, maka proses yang akan terjadi yaitu:
- Pencarian dimulai pada index ke-0 yaitu angka 9, kemudian dicocokkan dengan angka yang akan dicari, jika tidak sama maka pencarian akan dilanjutkan ke index selanjutnya.
- Pada index ke-1, yaitu angka 1, juga bukan angka yang dicari, maka pencarian akan dilanjutkan pada index selanjutnya.
- Pada index ke-2 dan index ke-3 yaitu angka 5 dan 2, juga bukan angka yang dicari, sehingga pencarian dilanjutkan pada index selanjutnya.
- Pada index ke-4 yaitu angka 7 dan ternyata angka 7 merupakan angka yang dicari, sehingga pencarian akan dihentikan dan proses selesai.

#### 2. Binary Search (Pencarian Biner)
- Binary search adalah algoritma pencarian efisien yang digunakan pada kumpulan data yang telah diurutkan. Algoritma ini membagi array menjadi dua bagian pada setiap iterasi dan memilih salah satu bagian untuk diperiksa selanjutnya, tergantung pada nilai elemen yang dicari. Algoritma ini memiliki kompleksitas waktu O(log n), di mana n adalah jumlah elemen dalam kumpulan data[5].

Contoh dari Binary Search, yaitu:

![Screenshot 2024-05-22 141019](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/6eae5cf2-b7f2-4757-80f2-e60d8875890e)

- Terdapat sebuah array yang menampung 7 elemen seperti ilustrasi di atas. Nilai
yang akan dicari pada array tersebut adalah 13[6].
- Jadi karena konsep dari binary search ini adalah membagi array menjadi dua
bagian, maka pertama tama kita cari nilai tengahnya dulu, total elemen dibagi 2
yaitu 7/2 = 4.5 dan kita bulatkan jadi 4.
- Maka elemen ke empat pada array adalah nilai tengahnya, yaitu angka 9 pada
indeks ke 3.
- Kemudian kita cek apakah 13 > 9 atau 13 < 9?
- 13 lebih besar dari 9, maka kemungkinan besar angka 13 berada setelah 9 atau
di sebelah kanan. Selanjutnya kita cari ke kanan dan kita dapat mengabaikan
elemen yang ada di kiri.
- Setelah itu kita cari lagi nilai tengahnya, didapatlah angka 14 sebagai nilai
tengah. Lalu, kita bandingkan apakah 13 > 14 atau 13 < 14?
- Ternyata 13 lebih kecil dari 14, maka selanjutnya kita cari ke kiri.
- Karna tersisa 1 elemen saja, maka elemen tersebut adalah nilai tengahnya.
Setelah dicek ternyata elemen pada indeks ke-4 adalah elemen yang dicari, maka
telah selesai proses pencariannya.

#### 3. Linear Search (Pencarian Linear) 
- Linear search adalah algoritma pencarian yang paling sederhana. Dalam pencarian linear, elemen-elemen dalam kumpulan data diperiksa satu per satu secara berurutan hingga elemen yang dicari ditemukan atau seluruh elemen telah diperiksa. Algoritma ini memiliki kompleksitas waktu O(n), di mana n adalah jumlah elemen dalam kumpulan data[4].

#### 4. Hash Table (Tabel Hash)
- Hash table adalah struktur data yang menggunakan fungsi hash untuk memetakan kunci (key) ke nilai (value) yang sesuai. Pencarian dalam hash table dilakukan dengan menghitung nilai hash dari kunci yang dicari, dan kemudian menggunakan nilai hash tersebut untuk mengakses nilai yang sesuai dalam tabel hash. Pencarian dalam hash table memiliki kompleksitas waktu rata-rata O(1), yang berarti waktu pencarian tidak bergantung pada jumlah elemen dalam tabel hash[1].
  
#### 5. Depth-First Search (DFS) dan Breadth-First Search (BFS)
- DFS dan BFS adalah algoritma pencarian yang digunakan dalam struktur data seperti pohon dan graf. DFS menjelajahi setiap cabang pohon atau graf secara mendalam sebelum pindah ke cabang berikutnya, sedangkan BFS menjelajahi semua node pada tingkat yang sama sebelum pindah ke tingkat berikutnya[2].


## Guided 
### Guided 1
#### 1, Buatlah sebuah project dengan menggunakan sequential search sederhana untuk melakukan pencarian data.

```C++
#include <iostream>
using namespace std;

// Inisialisasi array dengan 10 elemen
int arr[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
// Elemen yang akan dicari dalam array
int cari = 6;
// Variabel untuk indeks iterasi
int i;
// Menghitung panjang array dengan membagi ukuran total array dengan ukuran satu elemen
int panjangArray = sizeof(arr) / sizeof(arr[0]);
// Flag untuk menandai apakah elemen ditemukan
bool ketemu = false;

int main() {
    // Loop untuk iterasi melalui elemen-elemen array
    for (i = 0; i < panjangArray; i++) {
        // Jika elemen saat ini sama dengan elemen yang dicari
        if (arr[i] == cari) {
            // Set flag ketemu menjadi true (penugasan, bukan perbandingan)
            ketemu = true; // Perbaiki kesalahan, harus menggunakan '=' untuk penugasan, bukan '==' untuk perbandingan
            break; // Keluar dari loop jika elemen ditemukan
        } 
        // else { // Kondisi ini tidak diperlukan, karena tanpa ini juga i akan bertambah satu di akhir iterasi
        //     i++;
        // }
    }
    // Mencetak panjang array
    cout << "panjangArray: " << panjangArray << endl;
    // Mencetak hasil pencarian
    // Jika elemen ditemukan, tampilkan indeksnya, jika tidak, tampilkan pesan tidak ditemukan
    if (ketemu) {
        cout << cari << " terdapat pada indeks ke " << i << endl;
    } else {
        cout << cari << " tidak ditemukan dalam array" << endl;
    }
}





```
#### Output:
![Screenshot 2024-05-22 143143](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/8342427a-17d7-47c5-9e5d-16590f5e53e2)


- Kode ini adalah program C++ sederhana yang bertujuan untuk mencari elemen tertentu dalam sebuah array. Dimulai dengan menyertakan pustaka input-output `<iostream>` dan menggunakan namespace standar `std` untuk memudahkan penulisan kode. Program ini mendefinisikan sebuah array `arr` yang berisi 10 elemen integer, dan mendeklarasikan variabel `cari` yang menyimpan elemen yang akan dicari, dalam hal ini angka 6. Untuk mengatur iterasi, variabel `i` dideklarasikan sebagai indeks, dan panjang array dihitung dengan membagi ukuran total array dalam byte (`sizeof(arr)`) dengan ukuran satu elemen dalam array (`sizeof(arr[0])`). Hasilnya adalah jumlah elemen dalam array, yang disimpan dalam variabel `panjangArray`.

- Dalam fungsi `main`, program menggunakan loop `for` untuk iterasi melalui setiap elemen dalam array. Di setiap iterasi, program memeriksa apakah elemen saat ini (`arr[i]`) sama dengan elemen yang dicari (`cari`). Jika ditemukan kecocokan, flag `ketemu` diatur menjadi `true`, dan loop dihentikan menggunakan perintah `break` untuk menghindari iterasi yang tidak perlu. Setelah loop selesai, program mencetak panjang array dan hasil pencarian. Jika elemen ditemukan (`ketemu` bernilai `true`), program mencetak indeks elemen tersebut. Jika elemen tidak ditemukan (`ketemu` bernilai `false`), program mencetak pesan bahwa elemen tidak ditemukan dalam array. Perbaikan dilakukan pada penugasan `ketemu` menggunakan `=` daripada `==`, yang digunakan untuk perbandingan. Hal ini memastikan bahwa flag diatur dengan benar ketika elemen yang dicari ditemukan.

#### Full code Screenshot:
![Screenshot 2024-05-22 143345](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/aa1b7058-822e-4c49-88c0-ed2970e1aad0)


### Guided 2
#### 2. Buatlah sebuah project untuk melakukan pencarian data dengan menggunakan Binary Search.

```C++
#include <iostream>  // Menyertakan pustaka input-output untuk penggunaan cout dan cin
#include <iomanip>   // Menyertakan pustaka untuk manipulasi I/O seperti setw
using namespace std;

// Deklarasi array dan variabel untuk pencarian
int arrayData[7] = {1, 8, 2, 5, 4, 9, 7}; // Array yang akan diurutkan dan dicari elemennya
int cari; // Variabel untuk menyimpan elemen yang akan dicari

// Fungsi untuk mengurutkan array dengan algoritma selection sort
void selection_sort(int arr[], int n) {
    int temp, min;
    for (int i = 0; i < n - 1; i++) { // Loop untuk setiap elemen kecuali elemen terakhir
        min = i; // Asumsikan elemen terkecil adalah elemen saat ini
        for (int j = i + 1; j < n; j++) { // Loop untuk menemukan elemen terkecil di sisa array
            if (arr[j] < arr[min]) {
                min = j; // Update indeks elemen terkecil
            }
        }
        // Tukar elemen terkecil dengan elemen saat ini
        temp = arr[i];
        arr[i] = arr[min];
        arr[min] = temp;
    }
}

// Fungsi untuk melakukan pencarian biner dalam array yang sudah diurutkan
void binary_search(int arr[], int n, int target) {
    int awal = 0, akhir = n - 1, tengah, b_flag = 0;
    while (b_flag == 0 && awal <= akhir) { // Loop sampai ditemukan atau tidak ada elemen yang tersisa
        tengah = (awal + akhir) / 2; // Tentukan elemen tengah
        if (arr[tengah] == target) { // Jika elemen tengah adalah target
            b_flag = 1; // Set flag ditemukan
            break; // Keluar dari loop
        } else if (arr[tengah] < target) { // Jika target lebih besar dari elemen tengah
            awal = tengah + 1; // Pindahkan batas awal ke kanan
        } else { // Jika target lebih kecil dari elemen tengah
            akhir = tengah - 1; // Pindahkan batas akhir ke kiri
        }
    }
    if (b_flag == 1)
        cout << "\nData ditemukan pada index ke-" << tengah << endl; // Tampilkan indeks jika ditemukan
    else
        cout << "\nData tidak ditemukan\n"; // Tampilkan pesan jika tidak ditemukan
}

int main() {
    cout << "\tBINARY SEARCH" << endl;
    cout << "\nData awal: ";
    // Tampilkan data awal
    for (int x = 0; x < 7; x++) {
        cout << setw(3) << arrayData[x];
    }
    cout << endl;
    cout << "\nMasukkan data yang ingin Anda cari: ";
    cin >> cari; // Baca elemen yang ingin dicari dari input pengguna
    
    // Urutkan data dengan selection sort
    selection_sort(arrayData, 7);
    
    cout << "\nData diurutkan: ";
    // Tampilkan data setelah diurutkan
    for (int x = 0; x < 7; x++) {
        cout << setw(3) << arrayData[x];
    }
    cout << endl;
    
    // Lakukan binary search
    binary_search(arrayData, 7, cari);
    
    return 0;
}





```
#### Output:
![Screenshot 2024-05-22 143859](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/512843f0-fda5-4939-be5e-bac64365c14e)



- Kode diatas adalah implementasi dari algoritma selection sort dan binary search dalam bahasa C++ untuk mengurutkan dan mencari elemen dalam sebuah array. Dimulai dengan menyertakan pustaka input-output <iostream> dan pustaka manipulasi I/O <iomanip>, program ini menggunakan namespace standar std untuk memudahkan penulisan kode. Program mendeklarasikan sebuah array arrayData yang berisi tujuh elemen integer dan sebuah variabel cari yang akan menyimpan elemen yang ingin dicari oleh pengguna.

- Fungsi selection_sort mengurutkan array menggunakan algoritma selection sort, di mana array diurutkan dengan menemukan elemen terkecil dalam bagian yang tidak diurutkan dari array dan menukarnya dengan elemen pertama dari bagian tersebut. Fungsi ini melakukan iterasi melalui array dengan dua loop bersarang: loop luar untuk setiap elemen kecuali elemen terakhir, dan loop dalam untuk menemukan elemen terkecil di sisa array.

- Fungsi binary_search melakukan pencarian biner pada array yang sudah diurutkan. Fungsi ini menggunakan dua indeks, awal dan akhir, untuk menentukan bagian array yang akan dicari, dan menghitung indeks tengah. Jika elemen di tengah sama dengan elemen yang dicari (target), maka pencarian selesai dan elemen ditemukan. Jika elemen tengah lebih kecil dari target, pencarian dilanjutkan di bagian kanan array; sebaliknya, jika elemen tengah lebih besar, pencarian dilanjutkan di bagian kiri array. Fungsi ini mencetak hasil pencarian, menunjukkan apakah elemen ditemukan dan pada indeks berapa.

- Fungsi main mengatur alur utama program. Pertama, program menampilkan data awal array sebelum pengurutan, kemudian meminta pengguna untuk memasukkan elemen yang ingin dicari. Setelah itu, array diurutkan menggunakan selection_sort, dan program menampilkan array setelah diurutkan. Selanjutnya, binary_search digunakan untuk mencari elemen yang dimasukkan oleh pengguna dalam array yang sudah diurutkan, dan hasil pencarian ditampilkan kepada pengguna, apakah elemen ditemukan atau tidak. Program ini memberikan pemahaman tentang penggunaan algoritma pengurutan dan pencarian dalam pengolahan data array.

#### Full code Screenshot:
![Screenshot 2024-05-22 143908](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/994f7a57-442a-4b79-9076-182140bc4936)



## Unguided 

#### 1. Buatlah sebuah program untuk mencari sebuah huruf pada sebuah kalimat yangsudah di input dengan menggunakan Binary Search!

```C++
#include <iostream>
#include <string>
#include <algorithm>
using namespace std;

// Fungsi untuk mengurutkan array karakter menggunakan selection sort
void selection_sort(char arr[], int n) {
    int min;
    char temp;
    for (int i = 0; i < n - 1; i++) {
        min = i;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[min]) {
                min = j;
            }
        }
        // Tukar elemen
        temp = arr[i];
        arr[i] = arr[min];
        arr[min] = temp;
    }
}

// Fungsi untuk melakukan pencarian biner pada array karakter yang sudah diurutkan
void binary_search(char arr[], int n, char target) {
    int awal = 0, akhir = n - 1, tengah;
    bool found = false;
    
    while (awal <= akhir) {
        tengah = (awal + akhir) / 2;
        if (arr[tengah] == target) {
            found = true;
            break;
        } else if (arr[tengah] < target) {
            awal = tengah + 1;
        } else {
            akhir = tengah - 1;
        }
    }

    if (found) {
        cout << "Huruf '" << target << "' ditemukan pada indeks ke-" << tengah << endl;
    } else {
        cout << "Huruf '" << target << "' tidak ditemukan dalam kalimat." << endl;
    }
}

int main() {
    string kalimat;
    char cari;

    // Meminta pengguna untuk memasukkan sebuah kalimat
    cout << "Masukkan sebuah kalimat: ";
    getline(cin, kalimat);

    // Meminta pengguna untuk memasukkan huruf yang ingin dicari
    cout << "Masukkan huruf yang ingin Anda cari: ";
    cin >> cari;

    // Mengonversi string menjadi array karakter
    int panjang = kalimat.length();
    char arr[panjang];
    for (int i = 0; i < panjang; i++) {
        arr[i] = kalimat[i];
    }

    // Mengurutkan array karakter
    selection_sort(arr, panjang);

    // Menampilkan kalimat setelah diurutkan
    cout << "Kalimat setelah diurutkan: ";
    for (int i = 0; i < panjang; i++) {
        cout << arr[i];
    }
    cout << endl;

    // Melakukan binary search
    binary_search(arr, panjang, cari);

    return 0;
}



```
#### Output:
![Screenshot 2024-05-22 145134](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/adfa9e1d-c5e1-45a8-ad69-3a215f12d142)


- Kode diatas menggunakan algoritma pengurutan Selection Sort untuk mengurutkan karakter-karakter dalam kalimat dan algoritma pencarian Binary Search untuk mencari huruf yang diinginkan.

- Fungsi selection_sort digunakan untuk mengurutkan array karakter menggunakan algoritma Selection Sort. Dalam algoritma ini, setiap iterasi, elemen terkecil dari sisa array dipilih dan ditukar dengan elemen saat ini. Ini dilakukan hingga seluruh array terurut.

- Setelah pengurutan, fungsi binary_search dipanggil untuk melakukan pencarian biner pada array karakter yang sudah diurutkan. Dalam pencarian biner, array dibagi menjadi dua bagian setiap iterasi dan pencarian dilanjutkan pada bagian yang relevan tergantung pada relasi antara elemen tengah dan target. Jika elemen ditemukan, pesan yang sesuai ditampilkan; jika tidak, pesan bahwa huruf tidak ditemukan dicetak.

- Di dalam main, pengguna diminta untuk memasukkan sebuah kalimat dan huruf yang ingin dicari. Kalimat yang dimasukkan dikonversi menjadi array karakter, kemudian diurutkan menggunakan selection_sort. Setelah pengurutan, kalimat yang sudah diurutkan ditampilkan, dan fungsi binary_search dipanggil untuk mencari huruf yang diinginkan dalam kalimat yang sudah diurutkan. 
  
#### Full code Screenshot:
![Screenshot 2024-05-22 145149](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/47f18ccc-30e4-42e1-9f4e-7961232e2654)



#### 2. Buatlah sebuah program yang dapat menghitung banyaknya huruf vocal dalam sebuah kalimat!

```C++
#include <iostream>
#include <string>
#include <cctype> // Untuk menggunakan fungsi isalpha dan tolower
#include <vector>

using namespace std;

// Fungsi untuk menghitung jumlah huruf vokal dalam sebuah kalimat
int hitungVokal(const string& kalimat, vector<int>& indeks) {
    int jumlahVokal = 0;
    // Membuat string yang berisi huruf vokal
    string vokal = "aeiouAEIOU";
    
    // Iterasi melalui setiap karakter dalam kalimat
    for (int i = 0; i < kalimat.length(); ++i) {
        char karakter = kalimat[i];
        // Jika karakter adalah huruf dan huruf tersebut adalah huruf vokal
        if (isalpha(karakter) && vokal.find(karakter) != string::npos) {
            jumlahVokal++;
            indeks.push_back(i);
        }
    }
    return jumlahVokal;
}

int main() {
    string kalimat;
    vector<int> indeksHurufVokal;

    // Meminta pengguna untuk memasukkan kalimat
    cout << "Masukkan sebuah kalimat: ";
    getline(cin, kalimat);

    // Menghitung jumlah huruf vokal dalam kalimat
    int jumlahVokal = hitungVokal(kalimat, indeksHurufVokal);

    // Menampilkan jumlah huruf vokal
    cout << "Jumlah huruf vokal dalam kalimat adalah: " << jumlahVokal << endl;

    // Menampilkan indeks huruf vokal
    cout << "Indeks huruf vokal dalam kalimat adalah: ";
    for (int i = 0; i < indeksHurufVokal.size(); ++i) {
        cout << indeksHurufVokal[i];
        if (i < indeksHurufVokal.size() - 1) {
            cout << ", ";
        }
    }
    cout << endl;

    return 0;
}



```
#### Output:
![Screenshot 2024-05-22 150137](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/0ac9bef0-b33f-4245-bcb0-afabb82fa959)

- Kode diatas menggunakan fungsi getline(cin, kalimat). Kalimat ini akan disimpan dalam variabel kalimat yang merupakan objek dari tipe data string.

- Selanjutnya, program memanggil fungsi hitungVokal untuk menghitung jumlah huruf vokal dalam kalimat tersebut. Fungsi ini menerima dua parameter, yaitu kalimat yang ingin dihitung dan vektor indeksHurufVokal untuk menyimpan indeks di mana huruf vokal ditemukan.

- Dalam fungsi hitungVokal, program melakukan iterasi melalui setiap karakter dalam kalimat menggunakan loop for. Pada setiap iterasi, program memeriksa apakah karakter tersebut adalah huruf dan apakah karakter tersebut termasuk dalam daftar huruf vokal (aeiouAEIOU). Jika ya, maka jumlah huruf vokal akan bertambah satu dan indeks karakter tersebut akan dimasukkan ke dalam vektor indeksHurufVokal.

- Setelah selesai melakukan iterasi, program akan mengembalikan jumlah huruf vokal yang telah dihitung.

- Setelah itu, program akan menampilkan jumlah huruf vokal yang telah dihitung dan juga indeks dari huruf vokal tersebut dalam kalimat. Program menggunakan loop for untuk mencetak setiap indeks yang disimpan dalam vektor indeksHurufVokal, dan menyertakan tanda koma untuk memisahkan antara indeks.

#### Full code Screenshot:
![Screenshot 2024-05-22 150151](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/9b4a6258-89ef-4d8e-afe1-c4681e0d89fe)

#### 3. Diketahui data = 9, 4, 1, 4, 7, 10, 5, 4, 12, 4. Hitunglah berapa banyak angka 4 dengan menggunakan algoritma Sequential Search!
```C++
#include <iostream>
#include <vector>

using namespace std;

// Fungsi untuk melakukan Sequential Search
int sequentialSearch(const vector<int>& data, int target) {
    int count = 0;
    // Iterasi melalui setiap elemen dalam data
    for (int num : data) {
        // Jika elemen sama dengan target, tambahkan 1 ke count
        if (num == target) {
            count++;
        }
    }
    return count;
}

int main() {
    vector<int> data = {9, 4, 1, 4, 7, 10, 5, 4, 12, 4};
    int target = 4;
    
    // Menghitung jumlah angka 4 dalam data menggunakan Sequential Search
    int jumlah_angka_4 = sequentialSearch(data, target);

    // Menampilkan hasil
    cout << "Jumlah angka 4 dalam data adalah: " << jumlah_angka_4 << endl;

    return 0;
}



```
#### Output:
![Screenshot 2024-05-22 150921](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/ecb83c0b-07c8-4605-823c-83f6fd81b1e8)

- Kode diatas menggunakan algoritma Sequential Search untuk menghitung berapa banyak angka 4 dalam data yang diberikan. Pertama-tama, fungsi sequentialSearch didefinisikan untuk menerima dua parameter: data, yang merupakan vektor dari integer, dan target, yang merupakan angka yang ingin dicari. Di dalam fungsi ini, variabel count diinisialisasi dengan nilai 0 yang akan digunakan untuk menghitung berapa banyak angka target yang ditemukan dalam data. Selanjutnya, dilakukan iterasi melalui setiap elemen dalam data menggunakan loop for. Pada setiap iterasi, dilakukan pengecekan apakah elemen tersebut sama dengan target. Jika ya, maka 1 ditambahkan ke count. Setelah selesai melakukan iterasi, nilai count yang merupakan jumlah kemunculan angka target dalam data dikembalikan.

- Di dalam fungsi main, data yang merupakan vektor dari angka yang diberikan dan target yang merupakan angka yang ingin dicari, didefinisikan. Selanjutnya, fungsi sequentialSearch dipanggil dengan data dan target sebagai argumennya, dan hasilnya disimpan dalam variabel jumlah_angka_4. Terakhir, jumlah angka 4 yang ditemukan dalam data dicetak. Dengan menggunakan algoritma Sequential Search ini, program ini memberikan cara sederhana untuk menghitung berapa banyak angka 4 dalam data yang diberikan.
  
#### Full code Screenshot:
![Screenshot 2024-05-22 150938](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/4a2b2a96-5633-4f00-a984-f3b07aecd7c3)


## Kesimpulan
- A. Algoritma pencarian adalah serangkaian langkah sistematis yang digunakan untuk menemukan elemen tertentu dalam sekumpulan data atau struktur data.
- B. Tujuan utama dari algoritma pencarian adalah untuk menemukan lokasi atau indeks dari elemen yang dicari dalam waktu yang efisien.
- C. Algoritma pencarian sangat penting dalam berbagai bidang, seperti pengolahan data, struktur data, dan pemrograman komputer.
- D. Terdapat beberapa algoritma pencarian yang umum digunakan, antara lain Sequential Search, Binary Search, Linear Search, dan Hash Table.
- Sequential Search adalah algoritma pencarian sederhana yang digunakan untuk data yang belum terurut.
- Binary Search adalah algoritma pencarian efisien yang digunakan pada kumpulan data yang telah diurutkan.
- Linear Search adalah algoritma pencarian yang paling sederhana, di mana elemen-elemen dalam kumpulan data diperiksa satu per satu secara berurutan.
- Hash Table adalah struktur data yang menggunakan fungsi hash untuk memetakan kunci ke nilai yang sesuai.
- E. DFS (Depth-First Search) dan BFS (Breadth-First Search) adalah algoritma pencarian yang digunakan dalam struktur data seperti pohon dan graf.
- F. Program C++ dapat mengimplementasikan berbagai algoritma pencarian, seperti Sequential Search, Binary Search, dan sebagainya, untuk menemukan elemen tertentu dalam sebuah array.
- G. Algoritma Sequential Search dan Binary Search dapat digunakan untuk mencari elemen tertentu dalam array dengan kompleksitas waktu yang berbeda.
- H. Implementasi algoritma pencarian dan pengurutan dalam program C++ memungkinkan penyelesaian tugas-tugas komputasi yang melibatkan manipulasi data dengan efisien.
  
## Referensi
[1] Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2022). Introduction to Algorithms (4th Edition). MIT Press.

[2] Sedgewick, R., & Wayne, K. (2021). Algorithms (4th Edition). Addison-Wesley Professional.

[3] Grokking Algorithms: An Illustrated Guide for Programmers and Other Curious People by Aditya Bhargava (2019)

[4] Skiena, S. S. (2020). The Algorithm Design Manual (3rd Edition). Springer.

[5] Karumanchi, N. (2022). Data Structures and Algorithms Made Easy: Data Structure and Algorithmic Puzzles (6th Edition). CareerMonk Publications.

[6] Asisten Praktikum, “Modul 8 Algoritma Searching", Googgle Classroom, 2024.
