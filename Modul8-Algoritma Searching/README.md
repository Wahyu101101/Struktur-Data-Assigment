![Screenshot 2024-05-22 140329](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/b98c52d8-b585-4c6e-a45e-017c24e2efad)<p align="center">Wahyu Hidayat</p>
<p align="center">2311102178 / 11-E-IF</p>


## Dasar Teori

## **Algoritma Searching**

#### Pengertian Queue
**Algoritma searching** atau pencarian adalah serangkaian langkah-langkah sistematis yang digunakan untuk menemukan elemen tertentu dalam sekumpulan data atau struktur data[1]. Tujuan utama dari algoritma pencarian adalah untuk menemukan lokasi atau indeks dari elemen yang dicari dalam waktu yang efisien[2]. Algoritma pencarian sangat penting dalam berbagai bidang, seperti pengolahan data, struktur data, dan pemrograman komputer[3].
Implementasi queue dapat dilakukan dengan menggunakan array atau linked list. Struktur data queue terdiri dari dua pointer yaitu front dan rear. Front/head adalah pointer ke elemen pertama dalam queue dan rear/tail/back adalah pointer ke elemen terakhir dalam queue[1].

Pencarian (Searching) yaitu proses menemukan suatu nilai tertentu pada kumpulan data. Hasil pencarian adalah salah satu dari tiga keadaan ini: data ditemukan, data ditemukan lebih dari satu, atau data tidak ditemukan. Searching juga dapat dianggap sebagai proses pencarian suatu data di dalam sebuah array dengan cara mengecek satu persatu pada setiap index baris atau setiap index kolomnya dengan menggunakan teknik perulangan untuk melakukan pencarian data[6].

Terdapat beberapa algoritma pencarian yang umum digunakan, antara lain:
#### 1. Sequential Search
- Sequential Search merupakan salah satu algoritma pencarian data yang biasa digunakan untuk data yang berpola acak atau belum terurut. Sequential search juga merupakan teknik pencarian data dari array yang paling mudah, dimana data dalam array dibaca satu demi satu dan diurutkan dari index terkecil ke index terbesar, maupunsebaliknya. Konsep Sequential Search yaitu:
● Membandingkan setiap elemen pada array satu per satu secara berurut.
● Proses pencarian dimulai dari indeks pertama hingga indeks terakhir.
● Proses pencarian akan berhenti apabila data ditemukan. Jika hingga akhir array data masih juga tidak ditemukan, maka proses pencarian tetap akan dihentikan.
● Proses perulangan pada pencarian akan terjadi sebanyak jumlah N elemen pada array.

#### Algoritma pencarian berurutan dapat dituliskan sebagai berikut :
#### 1) i ← 0
#### 2) ketemu ← false
#### 3) Selama (tidak ketemu) dan (i <= N) kerjakan baris 4
#### 4) Jika (Data[i] = x) maka ketemu ← true, jika tidak i ← i + 1
#### 5) Jika (ketemu) maka i adalah indeks dari data yang dicari, jika tidak data tidak ditemukan.

#### Di bawah ini merupakan fungsi untuk mencari data menggunakan pencarian sekuensial.

![Screenshot 2024-05-22 140117](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/5623b0b9-ff09-428f-9f7c-6020c0c37e60)

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
-Binary search adalah algoritma pencarian efisien yang digunakan pada kumpulan data yang telah diurutkan. Algoritma ini membagi array menjadi dua bagian pada setiap iterasi dan memilih salah satu bagian untuk diperiksa selanjutnya, tergantung pada nilai elemen yang dicari. Algoritma ini memiliki kompleksitas waktu O(log n), di mana n adalah jumlah elemen dalam kumpulan data[5].

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

#### 1. Ubahlah penerapan konsep queue pada bagian guided dari array menjadi linked list

```C++
#include <iostream>
using namespace std;

// Struktur Node untuk linked list
struct Node {
    string data; // Data yang disimpan dalam node
    Node* next;  // Pointer ke node berikutnya
};

Node* front = nullptr; // Pointer ke elemen depan antrian
Node* back = nullptr;  // Pointer ke elemen belakang antrian

// Fungsi untuk memeriksa apakah antrian penuh
bool isFull() {
    return false; // Pada linked list, antrian tidak pernah penuh kecuali memori habis
}

// Fungsi untuk memeriksa apakah antrian kosong
bool isEmpty() {
    return front == nullptr; // Antrian kosong jika front adalah nullptr
}

// Fungsi untuk menambahkan elemen ke antrian
void enqueueAntrian(string data) {
    Node* newNode = new Node(); // Membuat node baru
    newNode->data = data;       // Menetapkan data ke node baru
    newNode->next = nullptr;    // Node baru akan menjadi node terakhir, jadi next adalah nullptr
    if (isEmpty()) {            // Jika antrian kosong
        front = back = newNode; // Node baru menjadi front dan back
    } else {
        back->next = newNode;   // Menghubungkan node terakhir saat ini ke node baru
        back = newNode;         // Memperbarui back ke node baru
    }
}

// Fungsi untuk menghapus elemen dari antrian
void dequeueAntrian() {
    if (isEmpty()) {
        cout << "Antrian kosong" << endl;
    } else {
        Node* temp = front;    // Menyimpan node depan sementara
        front = front->next;   // Memperbarui front ke node berikutnya
        if (front == nullptr) { // Jika antrian menjadi kosong setelah dequeue
            back = nullptr;   // Back juga harus nullptr
        }
        delete temp;          // Menghapus node depan lama
    }
}

// Fungsi untuk menghitung jumlah elemen dalam antrian
int countQueue() {
    int count = 0;
    Node* current = front;     // Mulai dari front
    while (current != nullptr) { // Iterasi melalui semua node
        count++;                // Tambah hitungan
        current = current->next; // Pindah ke node berikutnya
    }
    return count;              // Mengembalikan jumlah node
}

// Fungsi untuk mengosongkan antrian
void clearQueue() {
    while (!isEmpty()) {       // Selama antrian tidak kosong
        dequeueAntrian();      // Hapus elemen depan
    }
}

// Fungsi untuk melihat semua elemen dalam antrian
void viewQueue() {
    cout << "Data antrian teller:" << endl;
    Node* current = front;     // Mulai dari front
    int position = 1;
    while (current != nullptr) { // Iterasi melalui semua node
        cout << position << ". " << current->data << endl;
        current = current->next; // Pindah ke node berikutnya
        position++;
    }
    if (isEmpty()) {           // Jika antrian kosong
        for (int i = position; i <= 5; i++) { // Tampilkan kosong sampai posisi kelima
            cout << i << ". (kosong)" << endl;
        }
    }
}

int main() {
    enqueueAntrian("Wahyu");    // Menambahkan "Wahyu" ke antrian
    enqueueAntrian("Hasanah");    // Menambahkan "Hasanah" ke antrian
    viewQueue();               // Melihat antrian
    cout << "Jumlah antrian = " << countQueue() << endl; // Menampilkan jumlah antrian
    dequeueAntrian();          // Menghapus satu elemen dari antrian
    viewQueue();               // Melihat antrian lagi
    cout << "Jumlah antrian = " << countQueue() << endl; // Menampilkan jumlah antrian
    clearQueue();              // Mengosongkan antrian
    viewQueue();               // Melihat antrian setelah dikosongkan
    cout << "Jumlah antrian = " << countQueue() << endl; // Menampilkan jumlah antrian
    return 0;
}



```
#### Output:
![Screenshot 2024-05-18 061122](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/e1f0b949-6951-4dd5-8b9e-940f76fac8d1)


- #### Kode diatas adalah implementasi dari struktur data antrian (queue) menggunakan linked list. Struktur data antrian adalah struktur data linear di mana elemen-elemennya ditambahkan di ujung belakang dan dihapus dari ujung depan. Dalam kode tersebut, setiap elemen antrian direpresentasikan sebagai node dalam linked list, dengan setiap node memiliki dua bagian: data yang menyimpan informasi dan pointer yang menunjukkan ke node berikutnya. Pointer front digunakan untuk menunjukkan ke elemen depan antrian, sedangkan pointer back menunjukkan ke elemen belakang antrian.

- #### Fungsi-fungsi utama dalam kode tersebut mencakup operasi dasar pada antrian. Fungsi enqueueAntrian digunakan untuk menambahkan elemen baru ke belakang antrian, sementara dequeueAntrian digunakan untuk menghapus elemen dari depan antrian. Terdapat pula fungsi-fungsi pendukung seperti isEmpty untuk memeriksa apakah antrian kosong, countQueue untuk menghitung jumlah elemen dalam antrian, dan clearQueue untuk mengosongkan antrian. Dengan menggunakan linked list, struktur antrian ini dapat memperluas atau menyusut secara dinamis sesuai dengan kebutuhan, karena memori dialokasikan secara dinamis saat penambahan atau penghapusan elemen.

- #### Di dalam fungsi main, beberapa operasi dasar antrian diuji, seperti menambahkan elemen baru, menghapus elemen dari antrian, dan mengosongkan antrian. Hasil operasi tersebut dicetak ke layar untuk memverifikasi kebenaran implementasi. 
  
#### Full code Screenshot:
![Screenshot 2024-05-18 061133](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/c2ed1be8-d2b0-4b96-9d48-f8df0d11fdd0)



#### 2. Dari nomor 1 buatlah konsep antri dengan atribut Nama mahasiswa dan NIM Mahasiswa

```C++
#include <iostream>
using namespace std;

// Struktur Node untuk linked list
struct Node {
    string nama; // Nama mahasiswa
    string nim;  // NIM mahasiswa
    Node* next;  // Pointer ke node berikutnya
};

Node* front = nullptr; // Pointer ke elemen depan antrian
Node* back = nullptr;  // Pointer ke elemen belakang antrian

// Fungsi untuk memeriksa apakah antrian penuh
bool isFull() {
    return false; // Pada linked list, antrian tidak pernah penuh kecuali memori habis
}

// Fungsi untuk memeriksa apakah antrian kosong
bool isEmpty() {
    return front == nullptr; // Antrian kosong jika front adalah nullptr
}

// Fungsi untuk menambahkan elemen ke antrian
void enqueueAntrian(string nama, string nim) {
    Node* newNode = new Node(); // Membuat node baru
    newNode->nama = nama;       // Menetapkan nama ke node baru
    newNode->nim = nim;         // Menetapkan NIM ke node baru
    newNode->next = nullptr;    // Node baru akan menjadi node terakhir, jadi next adalah nullptr
    if (isEmpty()) {            // Jika antrian kosong
        front = back = newNode; // Node baru menjadi front dan back
    } else {
        back->next = newNode;   // Menghubungkan node terakhir saat ini ke node baru
        back = newNode;         // Memperbarui back ke node baru
    }
}

// Fungsi untuk menghapus elemen dari antrian
void dequeueAntrian() {
    if (isEmpty()) {
        cout << "Antrian kosong" << endl;
    } else {
        Node* temp = front;    // Menyimpan node depan sementara
        front = front->next;   // Memperbarui front ke node berikutnya
        if (front == nullptr) { // Jika antrian menjadi kosong setelah dequeue
            back = nullptr;   // Back juga harus nullptr
        }
        delete temp;          // Menghapus node depan lama
    }
}

// Fungsi untuk menghitung jumlah elemen dalam antrian
int countQueue() {
    int count = 0;
    Node* current = front;     // Mulai dari front
    while (current != nullptr) { // Iterasi melalui semua node
        count++;                // Tambah hitungan
        current = current->next; // Pindah ke node berikutnya
    }
    return count;              // Mengembalikan jumlah node
}

// Fungsi untuk mengosongkan antrian
void clearQueue() {
    while (!isEmpty()) {       // Selama antrian tidak kosong
        dequeueAntrian();      // Hapus elemen depan
    }
}

// Fungsi untuk melihat semua elemen dalam antrian
void viewQueue() {
    cout << "Data antrian mahasiswa:" << endl;
    Node* current = front;     // Mulai dari front
    int position = 1;
    while (current != nullptr) { // Iterasi melalui semua node
        cout << position << ". Nama: " << current->nama << ", NIM: " << current->nim << endl;
        current = current->next; // Pindah ke node berikutnya
        position++;
    }
    if (isEmpty()) {           // Jika antrian kosong
        for (int i = position; i <= 5; i++) { // Tampilkan kosong sampai posisi kelima
            cout << i << ". (kosong)" << endl;
        }
    }
}

int main() {
    enqueueAntrian("Wahyu", "2311102178");    // Menambahkan "Wahyu" ke antrian
    enqueueAntrian("Hasanah", "231111212");    // Menambahkan "Hasanah" ke antrian
    viewQueue();               // Melihat antrian
    cout << "Jumlah antrian = " << countQueue() << endl; // Menampilkan jumlah antrian
    dequeueAntrian();          // Menghapus satu elemen dari antrian
    viewQueue();               // Melihat antrian lagi
    cout << "Jumlah antrian = " << countQueue() << endl; // Menampilkan jumlah antrian
    clearQueue();              // Mengosongkan antrian
    viewQueue();               // Melihat antrian setelah dikosongkan
    cout << "Jumlah antrian = " << countQueue() << endl; // Menampilkan jumlah antrian
    return 0;
}



```
#### Output:
![Screenshot 2024-05-18 062553](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/74ecad8c-c62c-4498-80f2-f26e6ff76c7f)

- #### Kode diatas adalah implementasi sederhana dari struktur data antrian menggunakan linked list. Dalam struktur data antrian, elemen-elemennya diatur dalam urutan linear di mana penambahan elemen baru dilakukan di satu ujung (disebut "enqueue") dan penghapusan elemen dilakukan di ujung yang lain (disebut "dequeue"). Dalam kode tersebut, struktur Node digunakan untuk merepresentasikan setiap elemen dalam antrian, dengan setiap Node menyimpan informasi Nama dan NIM mahasiswa serta pointer yang menunjukkan ke Node berikutnya dalam antrian. Fungsi-fungsi seperti enqueueAntrian(), dequeueAntrian(), dan viewQueue() digunakan untuk menambah, menghapus, dan melihat elemen-elemen dalam antrian, sementara fungsi-fungsi lainnya seperti isEmpty() dan countQueue() membantu dalam memeriksa keadaan antrian dan menghitung jumlah elemen dalamnya.

- #### Implementasi tersebut memungkinkan penggunaan antrian dengan data mahasiswa, di mana setiap elemen antrian memiliki Nama dan NIM mahasiswa yang terkait. Dengan menggunakan linked list, antrian bisa dikelola secara dinamis, dan tidak ada batasan ukuran yang diberlakukan, kecuali keterbatasan memori. Fungsi-fungsi yang disediakan dalam kode tersebut memungkinkan pengguna untuk menambah, menghapus, melihat, dan mengosongkan antrian sesuai kebutuhan. Dengan cara ini, struktur data antrian dapat digunakan dalam berbagai konteks, termasuk dalam pengelolaan antrian penerimaan mahasiswa, antrean layanan, atau skenario lain di mana pengelolaan antrian diperlukan untuk mengatur urutan operasi.

#### Full code Screenshot:
![Screenshot 2024-05-18 062608](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/2497745f-5beb-4014-92e4-142dec5bff37)


## Kesimpulan
- A. Antrian (queue) adalah struktur data linear yang mengikuti prinsip FIFO (First-In First-Out), di mana elemen yang pertama masuk akan menjadi yang pertama keluar.
- B. Implementasi antrian dapat dilakukan menggunakan array atau linked list, dengan dua pointer penting: front dan rear.
- C. Operasi dasar pada antrian meliputi enqueue (menambah elemen), dequeue (menghapus elemen), serta operasi lain seperti peek, size, isEmpty, dan isFull.
- D. Kompleksitas waktu operasi antrian tergantung pada implementasinya, dengan kompleksitas waktu rata-rata O(1) untuk operasi enqueue dan dequeue pada linked list, dan O(1) untuk operasi enqueue dan dequeue pada array statis, namun dapat mencapai O(n) pada kasus terburuk saat relokasi memori diperlukan.
- E. Dalam implementasi linked list, antrian dapat memperluas atau menyusut secara dinamis sesuai dengan kebutuhan, membuatnya sangat fleksibel untuk digunakan dalam berbagai konteks aplikasi.
  
## Referensi
[1] Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2022). Introduction to Algorithms (4th Edition). MIT Press.
[2] Sedgewick, R., & Wayne, K. (2021). Algorithms (4th Edition). Addison-Wesley Professional.
[3] Grokking Algorithms: An Illustrated Guide for Programmers and Other Curious People by Aditya Bhargava (2019)
[4] Skiena, S. S. (2020). The Algorithm Design Manual (3rd Edition). Springer.
[5] Karumanchi, N. (2022). Data Structures and Algorithms Made Easy: Data Structure and Algorithmic Puzzles (6th Edition). CareerMonk Publications.
[6] Asisten Praktikum, “Modul 8 Algoritma Searching", Googgle Classroom, 2024.
