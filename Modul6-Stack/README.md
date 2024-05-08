![image](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/a4f395de-d350-4061-9cd4-3ca5d61c44a3)# <h1 align="center">Laporan Praktikum Modul Stack</h1>
<p align="center">Wahyu Hidayat</p>
<p align="center">2311102178 / 11-E-IF</p>


## Dasar Teori

## **Stack**

#### Pengertian Stack
Stack adalah struktur data sederhana yang digunakan untuk menyimpan data (mirip dengan Linked Lists). Dalam tumpukan, urutan kedatangan data penting. Sebuah tumpukan piring di kafetaria adalah contoh bagus dari tumpukan. Piring ditambahkan
ke tumpukan saat mereka dibersihkan dan ditempatkan di bagian atas. Ketika sebuah piring dibutuhkan, diambil dari bagian atas tumpukan. Piring pertama yang ditempatkan di tumpukan adalah yang terakhir digunakan[1]. 

Stack, atau tumpukan, adalah struktur data abstrak yang mengikuti aturan Last In, First Out (LIFO) [2]. Artinya, elemen yang terakhir dimasukkan ke dalam stack akan menjadi elemen pertama yang dikeluarkan. Analogi sederhananya seperti tumpukan piring: piring yang paling atas adalah yang terakhir diletakkan dan akan menjadi yang pertama diambil.

##### Definisi: Sebuah tumpukan adalah daftar terurut di mana penyisipan dan penghapusan dilakukan di satu ujung, disebut atas. Elemen terakhir yang dimasukkan adalah yang pertama dihapus. Oleh karena itu, disebut daftar Last in First out (LIFO)[1].


![Screenshot 2024-05-08 131258](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/0bbf6944-e070-4cbd-98a1-dc5e3398949b)

#### Pembahasan Stack

#### Stack memiliki beberapa operasi dasar:

- Push: Menambahkan elemen baru ke puncak stack [2].
- Pop: Menghapus elemen dari puncak stack dan mengembalikan nilainya [2].
- Top: Melihat nilai elemen di puncak stack tanpa menghapusnya [2].
- Empty: Memeriksa apakah stack kosong atau tidak [2].
- IsFull (Penuh): Memeriksa apakah tumpukan penuh atau tidak (terutama pad implementasi tumpukan dengan kapasitas terbatas)[1].
- Size (Ukuran): Mengembalikan jumlah elemen yang ada dalam tumpukan[1].
- Peek (Lihat): Melihat nilai atau elemen pada posisi tertentu dalam tumpukan tanpa menghapusnya[1].
- Clear (Hapus Semua): Mengosongkan atau menghapus semua elemen dari tumpukan[1].
- Search (Cari): Mencari keberadaan elemen tertentu dalam tumpukan[1].

##### Stack memiliki banyak aplikasi dalam pemrograman, seperti:

- Membatalkan operasi: Tombol undo/redo di banyak aplikasi menggunakan stack untuk menyimpan status program sebelumnya [3].
- Ekspresi matematika: Stack digunakan untuk mengevaluasi ekspresi matematika dengan urutan operasi yang benar [3].
- Kompilasi: Stack digunakan untuk menyimpan informasi tentang variabel dan label selama proses kompilasi [3].
- Algoritma: Stack digunakan dalam berbagai algoritma, seperti backtracking dan pencarian pohon [3].



## Guided 
### Guided 1

```C++
#include <iostream>
using namespace std;

string arrayBuku[5];
int maksimal = 5, top = 0;

bool isFull(){
    return(top == maksimal);
}

bool isEmpety(){
    return (top == 0);
}

void pushArrayBuku (string data ){
    if (isFull()){
        cout <<"Data telah penuh" <<endl;
    }
    else{
        arrayBuku[top] = data;
        top++;
    }
}

void popArrayBuku(){
    if (isEmpety()){
        cout <<" Tidak ada data yang dihapus" <<endl;
    }else {
        arrayBuku[top - 1] = "";
        top--;
    }
}

void peekArrayBuku (int posisi){
    if (isEmpety()){
        cout <<"Tidak ada data yang bisa dilihat"<<endl;
    }else {
        int index = top;
        for(int i = 1; i <= posisi; i++){
            index--;
        }
        cout << "Posisi ke " << posisi << " adalah " << arrayBuku[index] <<endl;
    }
}

int countStack (){
    return top;
}

void changeArrayBuku (int posisi, string data){
    if (posisi > top){
        cout << "Posisi melebihi data yang ada"<<endl;
    }else{
        int index = top;
        for (int i = 1; i <= posisi; i++){
            index--;
        }
        arrayBuku[index]= data;
    }
}

void destroyArraybuku(){
    for (int i = top; i >= 0; i--){
        arrayBuku[i] = "";
    }
    top = 0;
}

void cetakArrayBuku(){
    if (isEmpety()){
        cout << "Tidak ada data yang dicetak" <<endl;
    }else{
        for (int i = top -1; i >= 0; i--){
            cout << arrayBuku[i] <<endl;
        }
    }
}

int main(){
    pushArrayBuku("Kalkulus");
    pushArrayBuku("Struktur Data");
    pushArrayBuku("Matematika Diskrit");
    pushArrayBuku("Dasar Multimedia");
    pushArrayBuku("Inggris");

    cetakArrayBuku();
    cout << "\n";

    cout << "Apakah data stack penuh? " <<isFull()<<endl;
    cout << "Apakah data stack kosong? " <<isEmpety()<<endl;

    peekArrayBuku(2);
    popArrayBuku();
    cout << "Banyaknya data = " << countStack()<<endl;

    changeArrayBuku(2, "Bahasa Jerman");
    cetakArrayBuku();

    cout <<"\n";
    destroyArraybuku();
    cout << "Jumlah data setelah dihapus: " << top <<endl;

    cetakArrayBuku();
    return 0;
}



```
#### Output:
![Screenshot 2024-05-08 134534](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/fb99bef8-8b86-4ad2-9a3a-c93b518c068f)


Kode diatas dibuat dengan konsep tumpukan (stack) yang mengikuti aturan LIFO (Last In, First Out). Artinya, buku yang terakhir dimasukkan ke dalam tumpukan akan menjadi buku pertama yang dikeluarkan.

#### Deklarasi Variabel dan Fungsi

- arrayBuku[5]: Array untuk menyimpan judul buku, maksimum 5 buah.
- maksimal: Nilai konstan (const) yang menyatakan kapasitas maksimal tumpukan (5).
- top: Variabel integer untuk menunjuk ke posisi elemen teratas dalam tumpukan (awalnya 0).

#### Fungsi-fungsi

##### Pemeriksaan Kondisi Tumpukan:
- isFull(): Memeriksa apakah tumpukan sudah penuh (top == maksimal) dan mengembalikan true jika penuh, false jika masih ada ruang.
- isEmpety(): Memeriksa apakah tumpukan kosong (top == 0) dan mengembalikan true jika kosong, false jika ada data.
##### Operasi terhadap Tumpukan:
- pushArrayBuku(string data): Menambahkan buku baru dengan judul data ke dalam tumpukan. Fungsi ini terlebih dahulu mengecek isFull(). Jika penuh, akan menampilkan pesan "Data telah penuh". Jika tidak penuh, judul buku (data) akan disimpan di indeks top pada array arrayBuku, kemudian top ditambah 1 (menunjuk ke posisi kosong berikutnya).
- popArrayBuku(): Menghapus buku teratas dari tumpukan. Fungsi ini terlebih dahulu mengecek isEmpety(). Jika kosong, akan menampilkan pesan "Tidak ada data yang dihapus". Jika tidak kosong, elemen pada indeks top-1 dikosongkan dengan memberi nilai kosong ("") dan top dikurangi 1 (menunjuk ke elemen teratas baru).
- peekArrayBuku(int posisi): Menampilkan judul buku pada posisi tertentu (posisi) dalam tumpukan. Fungsi ini terlebih dahulu mengecek isEmpety(). Jika kosong, akan menampilkan pesan "Tidak ada data yang bisa dilihat". Jika tidak kosong, posisi sebenarnya dalam array dihitung dengan top - posisi karena top menunjuk ke elemen teratas. Judul buku pada posisi tersebut kemudian ditampilkan.
##### Operasi Lain pada Tumpukan:
- countStack(): Mengembalikan jumlah buku yang ada dalam tumpukan dengan nilai top.
- changeArrayBuku(int posisi, string data): Mengubah judul buku pada posisi tertentu (posisi) dalam tumpukan dengan judul baru data. Fungsi ini terlebih dahulu mengecek apakah posisi melebihi top (melebihi jumlah buku yang ada). Jika ya, akan menampilkan pesan "Posisi melebihi data yang ada". Jika tidak, posisi sebenarnya dalam array dihitung dengan top - posisi dan judul buku pada posisi tersebut diubah menjadi data.
- destroyArraybuku(): Menghapus semua data buku dari tumpukan. Fungsi ini melakukan iterasi dari top ke 0, dan pada setiap indeks elemen dikosongkan dengan memberi nilai kosong ("") pada array arrayBuku. Terakhir, top diubah menjadi 0 (menandakan tumpukan kosong).
- cetakArrayBuku(): Menampilkan daftar judul buku dari tumpukan, dari atas ke bawah. Fungsi ini terlebih dahulu mengecek isEmpety(). Jika kosong, akan menampilkan pesan "Tidak ada data yang dicetak". Jika tidak kosong, iterasi dilakukan dari top-1 hingga 0, dan pada setiap indeks judul buku pada array arrayBuku akan ditampilkan.

#### Full code Screenshot:

![Screenshot 2024-05-08 133438](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/0ca8be10-31f7-47f2-b28f-a49451f3b56e)





## Unguided 

#### 1. Buatlah program untuk menentukan apakah kalimat tersebut yang diinputkan dalam program stack adalah palindrom/tidak. Palindrom kalimat yang dibaca dari depan dan belakang sama. Jelaskan bagaimana cara kerja programnya.

#### Contoh :

- Kalimat : ini
- Kalimat tersebut adalah polindrom

- Kalimat : Telkom
- Kalimat tersebut adalah bukan polindrom
```C++
#include <iostream>
#include <cstring>
#include <cctype>
using namespace std;

string arrayBuku[5]; // Array untuk menyimpan kalimat dalam stack
int maksimal = 5, top = 0; // Variabel untuk mengontrol ukuran stack dan posisi top

bool isFull(){
    return (top == maksimal); // Mengecek apakah stack penuh
}

bool isEmpety(){
    return (top == 0); // Mengecek apakah stack kosong
}

void pushArrayBuku(string data){
    if (isFull()){ // Jika stack penuh
        cout <<"Data telah penuh" <<endl; // Tampilkan pesan
    }
    else{
        arrayBuku[top] = data; // Masukkan data ke dalam stack pada posisi top
        top++; // Pindahkan posisi top ke atas
    }
}

void popArrayBuku(){
    if (isEmpety()){ // Jika stack kosong
        cout <<" Tidak ada data yang dihapus" <<endl; // Tampilkan pesan
    }else {
        arrayBuku[top - 1] = ""; // Hapus data teratas dengan mengosongkan nilainya
        top--; // Turunkan posisi top
    }
}

void cetakArrayBuku(){
    if (isEmpety()){ // Jika stack kosong
        cout << "Tidak ada data yang dicetak" <<endl; // Tampilkan pesan
    }else{
        for (int i = top -1; i >= 0; i--){ // Iterasi dari top ke bawah hingga indeks ke-0
            cout << arrayBuku[i] <<endl; // Tampilkan data pada setiap indeks
        }
    }
}

bool isPalindrome(string str) {
    int length = str.length(); // Simpan panjang string
    for (int i = 0; i < length / 2; i++) { // Iterasi hingga setengah panjang string
        if (tolower(str[i]) != tolower(str[length - i - 1])) { // Bandingkan karakter pertama dengan yang terakhir, kedua dengan yang kedua terakhir, dan seterusnya
            return false; // Jika ada perbedaan, string bukan palindrom
        }
    }
    return true; // Jika tidak ada perbedaan, string palindrom
}

int main(){
    string kata;
    cout << endl;

    // Meminta pengguna memasukkan kata-kata
    for (int i = 0; i < 2; ++i) {
        cout << "Masukkan kata" << ": ";
        cin >> kata;
        pushArrayBuku(kata); // Masukkan kata ke dalam stack
    }
    cout << endl;


    for (int i = 0; i < top; i++) { // Iterasi melalui stack
        if (isPalindrome(arrayBuku[i])) { // Jika kata dalam stack adalah palindrom
            cout << "Kalimat : " << arrayBuku[i] <<endl; 
            cout << "Kalimat tersebut adalah palindrom." << endl;       
            cout << endl;
 // Tampilkan pesan
        } else {
            cout << "Kalimat : " << arrayBuku[i] <<endl; 
            cout << "Kalimat tersebut adalah bukan palindrom." << endl; // Tampilkan pesan
            cout << endl;
        }
    }


    return 0; // Keluar dari program
}


```
#### Output:
![Screenshot 2024-05-08 141632](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/645cceff-c948-43c9-a2bf-22a043a9cf97)
#### Kode di atas berfungsi untuk menentukan apakah kata-kata yang dimasukkan pengguna merupakan palindrom atau tidak. Di bawah ini penjelasan dari setiap bagian kode:

**1.Deklarasi Variabel dan Fungsi**:
- arrayBuku: Array yang digunakan sebagai stack untuk menyimpan kata-kata.
- maksimal: Variabel yang menunjukkan maksimal kapasitas stack.
- top: Variabel yang menunjukkan posisi paling atas (top) pada stack.
- isFull(): Fungsi untuk memeriksa apakah stack penuh.
- isEmpety(): Fungsi untuk memeriksa apakah stack kosong.
- pushArrayBuku(): Fungsi untuk menambahkan kata ke dalam stack.
- popArrayBuku(): Fungsi untuk menghapus kata dari stack.
- cetakArrayBuku(): Fungsi untuk mencetak isi stack.
- isPalindrome(): Fungsi untuk memeriksa apakah sebuah string merupakan palindrom.
**2.Meminta Input Pengguna**:
- Pengguna diminta untuk memasukkan dua buah kata. Dalam contoh ini, jumlah kata yang dimasukkan disetel menjadi 2.
**3.Pengecekan Palindrom**:
- Setelah kata-kata dimasukkan ke dalam stack, program melakukan iterasi melalui stack.
- Untuk setiap kata, program memanggil fungsi isPalindrome() untuk memeriksa apakah kata tersebut merupakan palindrom atau bukan.
- Jika kata adalah palindrom, program mencetak pesan bahwa kata tersebut adalah palindrom. Jika tidak, program mencetak pesan bahwa kata tersebut bukan palindrom.
**4.Penjelasan Hasil**:
- Setelah iterasi selesai, program menampilkan hasil pengecekan palindrom untuk setiap kata yang dimasukkan pengguna.
- Untuk setiap kata, program mencetak kata tersebut beserta hasil pengecekan palindrom.

#### Full code Screenshot:
![Screenshot 2024-05-08 141648](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/a05872a5-3704-466a-a6b5-2d457b679c6e)



## Kesimpulan
A. Hash table adalah struktur data yang digunakan untuk menyimpan dan mengakses data dengan cepat melalui fungsi hash. Dengan menggunakan fungsi hash yang efisien, hash table dapat memberikan akses yang cepat dan efisien terhadap data.

B. Operasi dasar hash table seperti insertion, deletion, dan searching menjadi penting dalam pengelolaan data. Dalam implementasi hash table, teknik chaining adalah metode umum yang digunakan untuk menangani kolisi, di mana dua kunci memiliki nilai hash yang sama. Dengan teknik chaining, item data dengan nilai indeks yang sama disimpan dalam linked list, memungkinkan pengelolaan data yang efisien.

C. Implementasi hash table dalam kode program C++ memberikan contoh konkret dari cara menggunakan teknik chaining untuk mengelola data. Dalam program tersebut, pengguna dapat menambahkan, menghapus, dan mencari data mahasiswa berdasarkan NIM atau rentang nilai tertentu. Dengan adanya menu pilihan, program memberikan fleksibilitas bagi pengguna dalam melakukan operasi-operasi tersebut, menunjukkan aplikasi praktis dari konsep hash table dalam pemrograman komputer.
## Referensi
[1] Asisten Praktikum, “Modul 6 Stack", Googgle Classroom, 2024.

[2] "A Survey of Stack-Based Machine Learning" oleh D. Wang et al. (2019) 

[3] "Stack-Based Memory Allocation for Deep Learning" oleh Y. Wu et al. (2019) 



