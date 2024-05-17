<p align="center">Wahyu Hidayat</p>
<p align="center">2311102178 / 11-E-IF</p>


## Dasar Teori

## **Queue**

#### Pengertian Queue
**Queue** adalah struktur data yang digunakan untuk menyimpan data dengan metode FIFO (First-In First-Out). Data yang pertama dimasukkan ke dalam queue akan menjadi data yang pertama pula untuk dikeluarkan dari queue. Queue mirip dengan konsep antrian pada kehidupan sehari-hari, dimana konsumen yang datang lebih dulu akan dilayani terlebih dahulu[1]. 
**Queue** adalah struktur data linear yang mengikuti prinsip First-In-First-Out (FIFO), di mana elemen yang pertama kali masuk akan menjadi elemen yang pertama kali keluar. Antrian terdiri dari dua ujung, yaitu front (depan) dan rear (belakang)[2].

Implementasi queue dapat dilakukan dengan menggunakan array atau linked list. Struktur data queue terdiri dari dua pointer yaitu front dan rear. Front/head adalah pointer ke elemen pertama dalam queue dan rear/tail/back adalah pointer ke elemen terakhir dalam queue[1].

![Screenshot 2024-05-16 071938](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/ddeaf4c2-05da-4e4b-bcea-7efc0c50f75c)


#### Operasi Dasar Queue
- Enqueue: Operasi untuk memasukkan elemen baru ke dalam antrian. Elemen baru akan ditempatkan di akhir (rear) antrian. Ilustrasi operasi enqueue pada antrian dengan linked list ditunjukkan pada Gambar 1.
  
![Linked-List-Enqueue-1024x320](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/0cc108a4-8c64-4e23-9aae-495b590225e3)


- Dequeue: Operasi untuk mengeluarkan elemen dari antrian. Elemen yang dikeluarkan adalah elemen yang paling awal masuk ke dalam antrian (front). Ilustrasi operasi dequeue pada antrian dengan linked list
ditunjukkan pada Gambar 2.

![Linked-List-Dequeue-1024x320](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/1db10261-38f3-4288-9f28-26ca899e0bfa)

- Front  : Operasi untuk mengakses elemen yang berada di depan antrian tanpa mengeluarkannya.
- Rear   : Operasi untuk mengakses elemen yang berada di akhir antrian.
- IsEmpty: Operasi untuk memeriksa apakah antrian kosong atau tidak.
- IsFull : Operasi untuk memeriksa apakah antrian sudah penuh atau masih dapat menampung elemen baru (khusus untuk implementasi menggunakan array statis).
- peek() : mengambil data dari queue tanpa menghapusnya.
- size() : menghitung jumlah elemen dalam queue.

#### Kompleksitas Waktu Operasi Antrian
- Kompleksitas waktu operasi enqueue dan dequeue pada implementasi antrian menggunakan array statis adalah O(1) untuk kasus rata-rata, namun dapat menjadi O(n) pada kasus terburuk ketika antrian harus direlokasi ke memori baru yang lebih besar. Kompleksitas waktu operasi enqueue dan dequeue pada implementasi antrian menggunakan linked list adalah O(1) untuk semua kasus[2].





## Guided 
### Guided 1

```C++
#include <iostream>
using namespace std;
const int maksimalQueue = 5; // Maksimal antrian
int front = 0; // Penanda antrian
int back = 0; // Penanda
string queueTeller[5]; // Fungsi pengecekan
bool isFull() { // Pengecekan antrian penuh atau tidak
if (back == maksimalQueue) {
return true; // =1
} else {
return false;
}
}
bool isEmpty() { // Antriannya kosong atau tidak
if (back == 0) {
return true;
} else {
return false;
}
}
void enqueueAntrian(string data) { // Fungsi menambahkan antrian
if (isFull()) {
cout << "Antrian penuh" << endl;
} else {
if (isEmpty()) { // Kondisi ketika queue kosong
queueTeller[0] = data;
front++;
back++;
} else { // Antrianya ada isi
queueTeller[back] = data;
back++;
}
}
}
void dequeueAntrian() { // Fungsi mengurangi antrian
if (isEmpty()) {
cout << "Antrian kosong" << endl;
} else {
for (int i = 0; i < back; i++) {
queueTeller[i] = queueTeller[i + 1];
}
back--;
}
}
int countQueue() { // Fungsi menghitung banyak antrian
return back;
}
void clearQueue() { // Fungsi menghapus semua antrian
if (isEmpty()) {
cout << "Antrian kosong" << endl;
} else {
for (int i = 0; i < back; i++) {
queueTeller[i] = "";
}
back = 0;
front = 0;
}
}
void viewQueue() { // Fungsi melihat antrian
cout << "Data antrian teller:" << endl;
for (int i = 0; i < maksimalQueue; i++) {
if (queueTeller[i] != "") {
cout << i + 1 << ". " << queueTeller[i] <<

endl;

} else {
cout << i + 1 << ". (kosong)" << endl;
}
}
}
int main() {
enqueueAntrian("Andi");
enqueueAntrian("Maya");
viewQueue();
cout << "Jumlah antrian = " << countQueue() << endl;
dequeueAntrian();
viewQueue();
cout << "Jumlah antrian = " << countQueue() << endl;
clearQueue();
viewQueue();
cout << "Jumlah antrian = " << countQueue() << endl;
return 0;
}




```
#### Output:
![Screenshot 2024-05-18 055502](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/9587b38c-f860-410a-9550-88d122b33383)


#### Kode di atas adalah implementasi dari antrian (queue) menggunakan array dengan kapasitas maksimum yang telah ditentukan (maksimalQueue sebesar 5). Kode ini menyediakan fungsi-fungsi dasar untuk antrian seperti menambah elemen (enqueue), menghapus elemen (dequeue), mengecek apakah antrian penuh atau kosong, menghitung jumlah elemen dalam antrian, mengosongkan antrian, dan menampilkan elemen-elemen dalam antrian.

#### Deklarasi Konstanta dan Variabel:
- maksimalQueue adalah kapasitas maksimal dari antrian.
- front dan back adalah indeks untuk melacak elemen di depan dan belakang antrian.
- queueTeller adalah array yang digunakan untuk menyimpan elemen-elemen antrian.

#### Fungsi isFull:
- Fungsi ini mengembalikan true jika antrian penuh (back mencapai maksimalQueue), dan false jika tidak penuh.

#### Fungsi isEmpty:
- Fungsi ini mengembalikan true jika antrian kosong (back sama dengan 0), dan false jika tidak kosong.

#### Fungsi enqueueAntrian:
- Fungsi ini menambahkan elemen ke antrian. Jika antrian penuh, mencetak pesan "Antrian penuh". Jika antrian kosong, elemen ditambahkan di posisi pertama. Jika tidak kosong, elemen ditambahkan di posisi back dan back diinkrementasi.

#### Fungsi dequeueAntrian:
- Fungsi ini menghapus elemen dari antrian. Jika antrian kosong, mencetak pesan "Antrian kosong". Jika tidak kosong, semua elemen digeser satu posisi ke kiri, dan back di-decrement.

#### Fungsi countQueue:
- Fungsi ini mengembalikan jumlah elemen dalam antrian.

#### Fungsi clearQueue:
- Fungsi ini menghapus semua elemen dalam antrian dengan mengosongkan array dan mengatur ulang back dan front menjadi 0.

#### Fungsi viewQueue:
- Fungsi ini menampilkan semua elemen dalam antrian, menunjukkan posisi mana yang kosong dan mana yang diisi.


#### Full code Screenshot:
![Screenshot 2024-05-18 055426](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/50abc100-30e1-40c7-9822-c18e517de1e4)





## Unguided 

#### 1. Buatlah program untuk menentukan apakah kalimat tersebut yang diinputkan dalam program stack adalah palindrom/tidak. Palindrom kalimat yang dibaca dari depan dan belakang sama. Jelaskan bagaimana cara kerja programnya.

#### Contoh :

- Kalimat : ini
  Kalimat tersebut adalah palindrom

- Kalimat : Telkom
  Kalimat tersebut adalah bukan palindrom
```C++
#include <iostream>
#include <cstring>
#include <cctype>
using namespace std;

string arrayBuku[5]; // Array untuk menyimpan kalimat dalam stack
int maksimal = 5, top = 0; // Variabel untuk mengontrol ukuran stack dan posisi top

void pushArrayBuku(string data) {
    if (top < maksimal) { // Periksa apakah masih ada ruang dalam stack
        arrayBuku[top] = data; // Masukkan data ke dalam stack pada posisi top
        top++; // Pindahkan posisi top ke atas
    } else {
        cout << "Stack penuh, tidak bisa menambahkan kata baru." << endl;
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

int main() {
    string kata;
    cout << endl;

    // Meminta pengguna memasukkan kata-kata
    for (int i = 0; i < 2; ++i) {
        cout << "Masukkan kata " << ": ";
        cin >> kata;
        pushArrayBuku(kata); // Masukkan kata ke dalam stack
    }
    cout << endl;

    for (int i = 0; i < top; i++) { // Iterasi melalui stack
        if (isPalindrome(arrayBuku[i])) { // Jika kata dalam stack adalah palindrom
            cout << "Kalimat : " << arrayBuku[i] << endl; 
            cout << "Kalimat tersebut adalah palindrom." << endl;       
            cout << endl;
        } else {
            cout << "Kalimat : " << arrayBuku[i] << endl; 
            cout << "Kalimat tersebut adalah bukan palindrom." << endl; 
            cout << endl;
        }
    }

    return 0; // Keluar dari program
}



```
#### Output:
![Screenshot 2024-05-08 143653](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/3b75e9ad-3989-41bc-b613-367412261b0c)

#### Kode di atas berfungsi untuk menentukan apakah kata-kata yang dimasukkan pengguna merupakan palindrom atau tidak. Di bawah ini penjelasan dari setiap bagian kode:

Kode di atas adalah sebuah program C++ yang mengimplementasikan konsep stack untuk menentukan apakah kata-kata yang dimasukkan pengguna merupakan palindrom atau tidak. Berikut adalah penjelasan singkat dari setiap bagian kode:

**1. Deklarasi Variabel dan Fungsi**:
- arrayBuku: Array yang digunakan sebagai stack untuk menyimpan kata-kata.
- maksimal: Variabel yang menunjukkan maksimal kapasitas stack.
- top: Variabel yang menunjukkan posisi paling atas (top) pada stack.
- pushArrayBuku(): Fungsi untuk menambahkan kata ke dalam stack.
- isPalindrome(): Fungsi untuk memeriksa apakah sebuah string merupakan palindrom.

**2. Fungsi pushArrayBuku()**:
- Fungsi ini digunakan untuk memasukkan kata ke dalam stack.
- Memeriksa apakah masih ada ruang dalam stack sebelum menambahkan kata.
- Jika masih ada ruang, kata dimasukkan ke dalam stack pada posisi top, dan posisi top dinaikkan satu tingkat.

**3. Fungsi isPalindrome()**:
- Fungsi ini digunakan untuk memeriksa apakah sebuah string merupakan palindrom.
- Membandingkan setiap karakter di posisi awal dengan karakter di posisi yang sama dari akhir string.
- Jika ada perbedaan antara karakter pertama dan terakhir, atau kedua dan kedua dari akhir, dst., maka string tersebut bukan palindrom.
- Jika tidak ada perbedaan, string tersebut adalah palindrom.
**4. main() Function**:
- Program meminta pengguna untuk memasukkan dua buah kata.
- Setelah kata dimasukkan, program memeriksa apakah setiap kata dalam stack adalah palindrom atau tidak menggunakan fungsi isPalindrome().
- Hasil dari pengecekan palindrom ditampilkan ke layar, bersama dengan kata-kata yang telah dimasukkan pengguna.
  
#### Full code Screenshot:
![Screenshot 2024-05-08 143600](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/1eef34c8-c67d-4be2-be97-85527eaeae19)


#### 2. Buatlah program untuk melakukan pembalikan terhadap kalimat menggunakan stack dengan minimal 3 kata. Jelaskan output program dan source codenya beserta operasi/fungsi yang dibuat?

#### contoh :
- Kalimat : Telkom Purwokerto
- Hasil : otrekowruP mokleT 

```C++
#include <iostream>
#include <stack>
#include <string>
using namespace std;

// Fungsi untuk membalikkan kalimat menggunakan stack
string reverseSentence(string sentence) {
    stack<char> charStack; // Stack untuk menyimpan karakter
    string reversedSentence; // String untuk menyimpan kalimat terbalik

    // Push setiap karakter ke dalam stack
    for (char c : sentence) {
        charStack.push(c);
    }

    // Pop karakter dari stack dan tambahkan ke string hasil
    while (!charStack.empty()) {
        reversedSentence += charStack.top();
        charStack.pop();
    }

    return reversedSentence; // Mengembalikan kalimat terbalik
}

int main() {
    string kalimat;
    cout<<endl;

    // Meminta pengguna memasukkan kalimat
    cout << "Masukkan kalimat: ";
    getline(cin, kalimat);
    cout<<endl;

    // Mencetak kalimat yang dimasukkan pengguna
    cout << "Kalimat: " << kalimat << endl;

    // Memanggil fungsi untuk membalikkan kalimat
    string hasil = reverseSentence(kalimat);

    // Mencetak hasil pembalikan kalimat
    cout << "Hasil: " << hasil << endl;
    cout<<endl;

    return 0;
}



```
#### Output:
![Screenshot 2024-05-08 145631](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/033ab297-fb80-4f25-b7fa-4913c8b1f449)

#### Kode di atas merupakan sebuah program C++ yang menggunakan stack untuk membalikkan sebuah kalimat yang dimasukkan oleh pengguna. 

**1. Header Files**: Program menggunakan #include <iostream>, #include <stack>, dan #include <string> untuk menyertakan file header yang diperlukan.

**2. Namespace**: Digunakan using namespace std; untuk menghindari penulisan std:: sebelum setiap fungsi dari namespace std.

**3. Fungsi reverseSentence**:
- Menerima parameter sentence yang merupakan sebuah string, yaitu kalimat yang akan dibalik.
- Membuat sebuah stack (charStack) untuk menyimpan setiap karakter dari kalimat.
- Iterasi melalui setiap karakter dalam kalimat, kemudian push karakter tersebut ke dalam stack.
- Setelah semua karakter dimasukkan ke dalam stack, karakter-karakter tersebut dipop dari stack satu per satu dan ditambahkan ke dalam string reversedSentence, sehingga menghasilkan kalimat terbalik.
- Mengembalikan kalimat terbalik tersebut.
- 
**4. Fungsi main**:
- Mendeklarasikan variabel kalimat untuk menyimpan kalimat yang dimasukkan oleh pengguna.
- Meminta pengguna untuk memasukkan sebuah kalimat menggunakan getline(cin, kalimat).
- Memanggil fungsi reverseSentence untuk membalikkan kalimat yang dimasukkan oleh pengguna.
- Mencetak kalimat asli dan hasil pembalikan kalimat menggunakan cout.
- 
**5.Output**: Program akan meminta pengguna untuk memasukkan sebuah kalimat. Setelah pengguna memasukkan kalimat, program akan mencetak kalimat tersebut, kemudian mencetak hasil pembalikan kalimat.

#### Full code Screenshot:
![Screenshot 2024-05-08 145646](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/b48d5ef5-9773-4d3e-9a00-bec634468e92)


## Kesimpulan
- A. Definisi Stack: Stack adalah struktur data abstrak yang mengikuti aturan Last In, First Out (LIFO), yang berarti elemen terakhir yang dimasukkan akan menjadi yang pertama dikeluarkan. Analogi sederhananya adalah tumpukan piring di kafetaria, di mana piring yang paling atas adalah yang terakhir dimasukkan dan pertama kali diambil.
- B. Operasi pada Stack: Ada beberapa operasi dasar yang dapat dilakukan pada stack, antara lain push (menambahkan elemen baru ke puncak stack), pop (menghapus elemen dari puncak stack), top (melihat nilai elemen di puncak stack tanpa menghapusnya), dan empty (memeriksa apakah stack kosong).
- C. Implementasi Stack: Stack dapat diimplementasikan menggunakan array atau linked list. Dalam implementasi menggunakan array, diperlukan penanganan khusus saat stack penuh atau kosong.
  
Dari program yang dibuat, kita dapat melihat bagaimana stack digunakan untuk membalikkan urutan kata dalam sebuah kalimat, serta bagaimana konsep LIFO diterapkan dalam proses tersebut. Hal ini menunjukkan fleksibilitas dan kegunaan stack dalam memecahkan berbagai masalah pemrograman.
## Referensi
[1] Asisten Praktikum, “Modul 7 Queue", Googgle Classroom, 2024.

[2] "A. Samara dan M. S. Watfa, "The Queue Data Structure: An In-Depth Study," IEEE Access, vol. 7, hlm. 172586–172607, 2019



