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



