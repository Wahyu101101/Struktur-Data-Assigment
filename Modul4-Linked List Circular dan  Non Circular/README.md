# <h1 align="center">Laporan Praktikum Modul Single and Double Linked List</h1>
<p align="center">Wahyu Hidayat</p>
<p align="center">2311102178 / 11-E-IF</p>


## Dasar Teori

**Linked List**

1. Linked List Non Circular
Linked list non circular merupakan linked list dengan node pertama (head) dan node terakhir (tail) yang tidak saling terhubung. Pointer terakhir (tail) pada Linked List ini selalu bernilai ‘NULL’ sebagai pertanda data terakhir dalam list nya. Linked list non circular dapat digambarkan sebagai berikut[1].

![Screenshot 2024-04-02 233253](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/881b40a6-0e82-4fb4-9303-6befd0ca39a7)

<center>Gambar 1. Single Linked List Non Circular</center>


A. Singly Linked List
Pada list jenis ini, tiap node nya memiliki field yang berisi pointer ke node berikutnya dan juga memiliki field yang berisi data. Akhir linked list ditandai dengan node terakhir yang menunjuk ke null yang akan digunakan sebagai kondisi berhenti saat pembacaan linked list[2].

![Screenshot 2024-04-02 232506](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/b2b8e5e8-b7b7-498d-8924-68b72c68c410)

<center>Gambar 2. Ilustrasi singly linked list</center>


B. Doubly Linked List
Merupakan linked list dengan menggunakan pointer, dimana setiap node memiliki tiga buah field, yaitu : field pointer yang menunjuk ke pointer berikutnya, field pointer yang menunjuk ke pointer sebelumnya dan field yang berisi data dari node tersebut. Semenatara pointer next dan prev-nya menunjuk ke null[2].

![Screenshot 2024-04-02 232637](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/2cfe424b-0842-4190-9739-4a08e42b0a84)


<center>Gambar 3. Ilustrasi doubly linked list</center>



2. Linked List Circular
Linked list circular merupakan linked list yang tidak memiliki akhir karena node terakhir (tail) tidak bernilai ‘NULL’, tetapi terhubung dengan node pertama (head). Saat menggunakan linked list circular kita membutuhkan dummy node atau node pengecoh yang biasanya dinamakan dengan node current supaya program dapat berhenti menghitung data ketika node current mencapai node pertama (head). Linked list circular dapat digunakan untuk menyimpan data yang perlu diakses secara berulang, seperti daftar putar lagu, daftar pesan dalam antrian, atau penggunaan memori berulang dalam suatu aplikasi. Linked list circular dapat digambarkan sebagai berikut[1].

![Screenshot 2024-04-02 232847](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/09b1cd81-40b1-4bd1-8f31-921f2d4fda23)


<center>Gambar 4. Single Linked List Circular</center>


A. Singly Circular Linked List
Adalah singly linked list yang pointer next-nya menunjuk ke dirinya sendiri (proses rekursif), jika terdiri dari beberapa node maka pointer terakhirnya akan menunjuk ke pointer terdepannya[2]. 

![Screenshot 2024-04-02 230935](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/6bd1c853-b49a-48aa-aaa9-be074be78cde)


<center>Gambar 5. Ilustrasi singly circular linked list</center>

B. Doubly Circular Linked List
Merupakan sutau double linked list yang pointer next dan pointer prev-nya menunjuk ke dirinya sendiri secara circular[2].

![Screenshot 2024-04-02 231209](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/912221f0-1c2e-4dce-afff-4a48e3e9e0de)


<center>Gambar 6. Ilustrasi Doubly circular linked list </center>



## Guided 
### 1. Latihan Single Linked List

```C++
#include <iostream>
using namespace std;

/// PROGRAM SINGLE LINKED LIST NON-CIRCULAR
// Deklarasi Struct Node
struct Node
{
    // komponen/member
    int data;
    Node *next;
};
Node *head;
Node *tail;
// Inisialisasi Node
void init()
{
    head = NULL;
    tail = NULL;
}
// Pengecekan
bool isEmpty()
{
    if (head == NULL)
        return true;
    else
        return false;
}
// Tambah Depan
void insertDepan(int nilai)
{
    // Buat Node baru
    Node *baru = new Node;
    baru->data = nilai;
    baru->next = NULL;
    if (isEmpty() == true)
    {
        head = tail = baru;
        tail->next = NULL;
    }
    else
    {
        baru->next = head;
        head = baru;
    }
}
// Tambah Belakang
void insertBelakang(int nilai)
{
    // Buat Node baru
    Node *baru = new Node;
    baru->data = nilai;
    baru->next = NULL;
    if (isEmpty() == true)
    {
        head = tail = baru;
        tail->next = NULL;
    }
    else
    {
        tail->next = baru;
        tail = baru;
    }
}
// Hitung Jumlah List
int hitungList()
{
    Node *hitung;
    hitung = head;
    int jumlah = 0;
    while (hitung != NULL)
    {
        jumlah++;
        hitung = hitung->next;
    }
    return jumlah;
}
// Tambah Tengah
void insertTengah(int data, int posisi)
{
    if (posisi < 1 || posisi > hitungList())
    {
        cout << "Posisi diluar jangkauan" << endl;
    }
    else if (posisi == 1)
    {
        cout << "Posisi bukan posisi tengah" << endl;
    }
    else
    {
        Node *baru, *bantu;
        baru = new Node();
        baru->data = data;
        // tranversing
        bantu = head;
        int nomor = 1;
        while (nomor < posisi - 1)
        {
            bantu = bantu->next;
            nomor++;
        }
        baru->next = bantu->next;
        bantu->next = baru;
    }
}
// Hapus Depan
void hapusDepan()
{
    Node *hapus;
    if (isEmpty() == false)
    {
        if (head->next != NULL)
        {
            hapus = head;
            head = head->next;
            delete hapus;
        }
        else
        {
            head = tail = NULL;
        }
    }
    else
    {
        cout << "List kosong!" << endl;
    }
}
// Hapus Belakang
void hapusBelakang()
{
    Node *hapus;
    Node *bantu;
    if (isEmpty() == false)
    {
        if (head != tail)
        {
            hapus = tail;
            bantu = head;
            while (bantu->next != tail)
            {
                bantu = bantu->next;
            }
            tail = bantu;
            tail->next = NULL;
            delete hapus;
        }
        else
        {
            head = tail = NULL;
        }
    }
    else
    {
        cout << "List kosong!" << endl;
    }
}
// Hapus Tengah
void hapusTengah(int posisi)
{
    Node *hapus, *bantu, *bantu2;
    if (posisi < 1 || posisi > hitungList())
    {
        cout << "Posisi di luar jangkauan" << endl;
    }
    else if (posisi == 1)
    {
        cout << "Posisi bukan posisi tengah" << endl;
    }
    else
    {
        int nomor = 1;
        bantu = head;
        while (nomor <= posisi)
        {
            if (nomor == posisi - 1)
            {
                bantu2 = bantu;
            }
            if (nomor == posisi)
            {
                hapus = bantu;
            }
            bantu = bantu->next;
            nomor++;
        }
        bantu2->next = bantu;
        delete hapus;
    }
}
// Ubah Depan
void ubahDepan(int data)
{
    if (isEmpty() == false)
    {
        head->data = data;
    }
    else
    {
        cout << "List masih kosong!" << endl;
    }
}
// Ubah Tengah
void ubahTengah(int data, int posisi)
{
    Node *bantu;
    if (isEmpty() == false)
    {
        if (posisi < 1 || posisi > hitungList())
        {
            cout << "Posisi di luar jangkauan" << endl;
        }
        else if (posisi == 1)
        {
            cout << "Posisi bukan posisi tengah" << endl;
        }
        else
        {
            bantu = head;
            int nomor = 1;
            while (nomor < posisi)
            {
                bantu = bantu->next;
                nomor++;
            }
            bantu->data = data;
        }
    }
    else
    {
        cout << "List masih kosong!" << endl;
    }
}
// Ubah Belakang
void ubahBelakang(int data)
{
    if (isEmpty() == false)
    {
        tail->data = data;
    }
    else
    {
        cout << "List masih kosong!" << endl;
    }
}
// Hapus List
void clearList()
{
    Node *bantu, *hapus;
    bantu = head;
    while (bantu != NULL)
    {
        hapus = bantu;
        bantu = bantu->next;
        delete hapus;
    }
    head = tail = NULL;
    cout << "List berhasil terhapus!" << endl;
}
// Tampilkan List
void tampil()
{
    Node *bantu;
    bantu = head;
    if (isEmpty() == false)
    {
        while (bantu != NULL)
        {
            cout << bantu->data << ends;
            bantu = bantu->next;
        }
        cout << endl;
    }
    else
    {
        cout << "List masih kosong!" << endl;
    }
}
int main()
{
    init();
    insertDepan(3);
    tampil();
    insertBelakang(5);
    tampil();
    insertDepan(2);
    tampil();
    insertDepan(1);
    tampil();
    hapusDepan();
    tampil();
    hapusBelakang();
    tampil();
    insertTengah(7, 2);
    tampil();
    hapusTengah(2);
    tampil();
    ubahDepan(1);
    tampil();
    ubahBelakang(8);
    tampil();
    ubahTengah(11, 2);
    tampil();
    return 0;
}

```
#### Output:
![Screenshot 2024-03-26 103743](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/94754a11-85d5-4532-bae8-4868d39f41c1)


Kode diatas mengimplementasikan struktur data Linked List (Daftar Terhubung) dalam bentuk non-circular, yang merupakan struktur data yang terdiri dari elemen-elemen yang saling terhubung melalui pointer. Setiap elemen dalam linked list, yang disebut node, memiliki dua bagian: data (nilai yang disimpan) dan pointer ke node berikutnya dalam list. Kode ini mencakup berbagai fungsi untuk mengelola linked list, termasuk inisialisasi list (`init()`), pengecekan apakah list kosong (`isEmpty()`), serta operasi penambahan node (`insertDepan()`, `insertBelakang()`, `insertTengah()`), penghapusan node (`hapusDepan()`, `hapusBelakang()`, `hapusTengah()`), pengubahan data node (`ubahDepan()`, `ubahTengah()`, `ubahBelakang()`), dan penghapusan semua node dalam list (`clearList()`). Fungsi `tampil()` digunakan untuk menampilkan semua data dalam list. Kode ini menunjukkan bagaimana menggunakan dan mengelola linked list dalam berbagai operasi, seperti menambahkan, menghapus, dan mengubah elemen, serta menampilkan elemen-elemen dalam list.

#### Full code Screenshot:
![Screenshot 2024-03-26 103727](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/dfea359a-275c-4354-ae65-edd2c9663e2e)



### 2. Latihan Double Linked List
```C++
#include <iostream>
using namespace std;

// Deklarasi kelas Node
class Node {
public:
    int data;    // Menyimpan nilai data dalam node
    Node* prev;  // Pointer ke node sebelumnya
    Node* next;  // Pointer ke node berikutnya
};

// Deklarasi kelas DoublyLinkedList
class DoublyLinkedList {
public:
    Node* head;  // Pointer ke node pertama dalam list
    Node* tail;  // Pointer ke node terakhir dalam list

    // Konstruktor DoublyLinkedList
    DoublyLinkedList() {
        head = nullptr;
        tail = nullptr;
    }

    // Metode untuk menambahkan node baru di depan list
    void push(int data) {
        Node* newNode = new Node;  // Membuat node baru
        newNode->data = data;      // Mengatur nilai data node baru
        newNode->prev = nullptr;   // Mengatur pointer prev node baru menjadi nullptr
        newNode->next = head;      // Mengatur pointer next node baru menjadi head

        if (head != nullptr) {     // Jika list tidak kosong
            head->prev = newNode;  // Mengatur pointer prev dari node pertama menjadi newNode
        } else {
            tail = newNode;        // Jika list kosong, newNode menjadi tail
        }

        head = newNode;            // Mengatur head menjadi newNode
    }

    // Metode untuk menghapus node pertama dari list
    void pop() {
        if (head == nullptr) {     // Jika list kosong, tidak perlu dilakukan apa-apa
            return;
        }

        Node* temp = head;         // Menyimpan pointer ke node pertama sementara
        head = head->next;         // Menggeser head ke node berikutnya

        if (head != nullptr) {     // Jika masih ada node lain setelahnya
            head->prev = nullptr;  // Mengatur pointer prev dari node pertama menjadi nullptr
        } else {
            tail = nullptr;        // Jika tidak ada node lain, tail menjadi nullptr
        }

        delete temp;               // Menghapus node pertama dari memori
    }

    // Metode untuk mencari dan memperbarui nilai data node tertentu
    bool update(int oldData, int newData) {
        Node* current = head;      // Pointer untuk iterasi melalui list

        while (current != nullptr) {  // Selama masih ada node dalam list
            if (current->data == oldData) {  // Jika nilai data node saat ini sama dengan oldData
                current->data = newData;     // Update nilai data node menjadi newData
                return true;                 // Kembalikan true karena update berhasil
            }
            current = current->next;  // Pindah ke node berikutnya
        }

        return false;  // Jika tidak ditemukan oldData, kembalikan false
    }

    // Metode untuk menghapus semua node dari list
    void deleteAll() {
        Node* current = head;  // Pointer untuk iterasi melalui list

        while (current != nullptr) {  // Selama masih ada node dalam list
            Node* temp = current;     // Menyimpan pointer ke node saat ini sementara
            current = current->next;  // Pindah ke node berikutnya
            delete temp;              // Menghapus node sementara dari memori
        }

        head = nullptr;  // Setelah semua node dihapus, head dan tail diatur menjadi nullptr
        tail = nullptr;
    }

    // Metode untuk menampilkan semua nilai data dalam list
    void display() {
        Node* current = head;  // Pointer untuk iterasi melalui list

        while (current != nullptr) {  // Selama masih ada node dalam list
            cout << current->data << " ";  // Tampilkan nilai data node saat ini
            current = current->next;       // Pindah ke node berikutnya
        }

        cout << endl;  // Tampilkan newline setelah semua nilai data ditampilkan
    }
};


int main() {
    DoublyLinkedList list;  // Membuat objek DoublyLinkedList baru bernama list

    while (true) {  // Loop tak terbatas untuk menu interaktif
        cout << "1. Add data" << endl;
        cout << "2. Delete data" << endl;
        cout << "3. Update data" << endl;
        cout << "4. Clear data" << endl;
        cout << "5. Display data" << endl;
        cout << "6. Exit" << endl;
        int choice;
        cout << "Enter your choice: ";
        cin >> choice;  // Membaca pilihan pengguna

        switch (choice) {  // Memproses pilihan pengguna
            case 1: {
                int data;
                cout << "Enter data to add: ";
                cin >> data;  // Membaca data yang ingin ditambahkan
                list.push(data);  // Menambahkan data ke list
                break;
            }
            case 2: {
                list.pop();  // Menghapus data dari list
                break;
            }
            case 3: {
                int oldData, newData;
                cout << "Enter old data: ";
                cin >> oldData;  // Membaca data yang ingin diubah
                cout << "Enter new data: ";
                cin >> newData;  // Membaca data baru
                bool updated = list.update(oldData, newData);  // Memperbarui data dalam list
                if (!updated) {
                    cout << "Data not found" << endl;  // Menampilkan pesan jika data tidak ditemukan
                }
                break;
            }
            case 4: {
                list.deleteAll();  // Menghapus semua data dari list
                break;
            }
            case 5: {
                list.display();  // Menampilkan semua data dalam list
                break;
            }
            case 6: {
                return 0;  // Keluar dari program
            }
            default: {
                cout << "Invalid choice" << endl;  // Menampilkan pesan jika pilihan tidak valid
                break;
            }
        }
    }

    return 0;
}
```
#### Output:

![Screenshot 2024-03-26 104519](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/190c2f6d-b732-434c-8cd1-b9b93a8ab342)


Kode di atas mengimplementasikan struktur data Doubly Linked List (Daftar Terhubung Ganda) yang memungkinkan akses ke node sebelum dan setelah node saat ini. Doubly Linked List terdiri dari node, di mana setiap node memiliki dua pointer, satu ke node sebelumnya (`prev`) dan satu ke node berikutnya (`next`). Kode mendefinisikan kelas `Node` untuk menyimpan data dan pointer ke node sebelum dan setelahnya, serta kelas `DoublyLinkedList` yang mengelola operasi pada list, termasuk menambahkan node di awal list (`push()`), menghapus node dari awal list (`pop()`), memperbarui data dalam list (`update()`), menghapus semua node dalam list (`deleteAll()`), dan menampilkan semua data dalam list (`display()`). Dalam fungsi `main()`, pengguna dapat memilih untuk menambahkan, menghapus, memperbarui, menampilkan, atau menghapus semua data dalam list melalui menu interaktif.
#### Full code Screenshot:

![Screenshot 2024-03-26 140919](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/568d6207-eebb-4d33-b582-2b2db93081a5)


## Unguided 

### 1. Soal mengenai Single Linked List
Buatlah program menu Single Linked List Non-Circular untuk
menyimpan Nama dan usia mahasiswa, dengan menggunakan inputan
dari user. Lakukan operasi berikut:
a. Masukkan data sesuai urutan berikut. (Gunakan insert depan,
belakang atau tengah). Data pertama yang dimasukkan adalah
nama dan usia anda.
[Nama_anda] [Usia_anda]
John 19
Jane 20
Michael 18
Yusuke 19
Akechi 20
Hoshino 18
Karin 18
b. Hapus data Akechi
c. Tambahkan data berikut diantara John dan Jane : Futaba 18
d. Tambahkan data berikut diawal : Igor 20
e. Ubah data Michael menjadi : Reyn 18
f. Tampilkan seluruh data
```C++
#include <iostream>
#include <string>
using namespace std;

// Mendefinisikan struktur Node untuk menyimpan data mahasiswa
struct Node {
    string nama;    // Menyimpan nama mahasiswa
    int usia;       // Menyimpan usia mahasiswa
    Node* next;     // Pointer ke node berikutnya dalam linked list
};

// Deklarasi variabel global head untuk menunjukkan awal dari linked list
Node* head = NULL;

// Fungsi untuk menyisipkan data di depan linked list
void insertDepan(string nama, int usia) {
    Node* newNode = new Node;   // Membuat node baru
    newNode->nama = nama;       // Menyimpan nama pada node baru
    newNode->usia = usia;       // Menyimpan usia pada node baru
    newNode->next = head;       // Mengatur node baru sebagai node pertama dalam linked list
    head = newNode;             // Mengatur head baru menjadi node baru
}

// Fungsi untuk menyisipkan data di belakang linked list
void insertBelakang(string nama, int usia) {
    Node* newNode = new Node;   // Membuat node baru
    newNode->nama = nama;       // Menyimpan nama pada node baru
    newNode->usia = usia;       // Menyimpan usia pada node baru
    newNode->next = NULL;       // Mengatur next dari node baru menjadi NULL

    if (head == NULL) {         // Jika linked list kosong
        head = newNode;         // Node baru menjadi node pertama
        return;
    }

    Node* temp = head;
    while (temp->next != NULL) {   // Mencari node terakhir
        temp = temp->next;
    }
    temp->next = newNode;          // Menyambungkan node baru di belakang
}

// Fungsi untuk menyisipkan data di posisi tertentu dalam linked list
void insertTertentu(string nama, int usia, int posisi) {
    Node* newNode = new Node;   // Membuat node baru
    newNode->nama = nama;       // Menyimpan nama pada node baru
    newNode->usia = usia;       // Menyimpan usia pada node baru

    if (posisi < 1) {           // Jika posisi tidak valid
        cout << "Posisi tidak valid." << endl;
        return;
    }

    if (posisi == 1 || head == NULL) {   // Jika posisi adalah posisi pertama atau linked list kosong
        insertDepan(nama, usia);         // Memanggil fungsi untuk menyisipkan di depan
        return;
    }

    Node* temp = head;
    for (int i = 1; i < posisi - 1 && temp->next != NULL; i++) {  // Mencari node sebelum posisi yang ditentukan
        temp = temp->next;
    }
    newNode->next = temp->next;      // Menyambungkan node baru dengan node setelahnya
    temp->next = newNode;            // Menyambungkan node sebelumnya dengan node baru
}

// Fungsi untuk menghapus data berdasarkan nama
void hapusData(string nama) {
    if (head == NULL) {             // Jika linked list kosong
        cout << "List kosong!" << endl;
        return;
    }

    Node* temp = head;
    Node* prev = NULL;

    if (temp->nama == nama) {      // Jika data yang akan dihapus berada pada node pertama
        head = temp->next;         // Mengubah head menjadi node berikutnya
        delete temp;               // Menghapus node pertama
        return;
    }

    while (temp != NULL && temp->nama != nama) {  // Mencari node yang berisi data yang akan dihapus
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL) {            // Jika data tidak ditemukan
        cout << "Data tidak ditemukan." << endl;
        return;
    }

    prev->next = temp->next;       // Menghubungkan node sebelumnya dengan node setelahnya
    delete temp;                   // Menghapus node yang berisi data yang akan dihapus
}

// Fungsi untuk mengubah data berdasarkan nama
void ubahData(string namaLama, string namaBaru, int usiaBaru) {
    if (head == NULL) {            // Jika linked list kosong
        cout << "List kosong!" << endl;
        return;
    }

    Node* temp = head;

    while (temp != NULL && temp->nama != namaLama) {  // Mencari node yang berisi data yang ingin diubah
        temp = temp->next;
    }

    if (temp == NULL) {            // Jika data tidak ditemukan
        cout << "Data tidak ditemukan." << endl;
        return;
    }

    temp->nama = namaBaru;         // Mengubah nama pada node yang bersangkutan
    temp->usia = usiaBaru;         // Mengubah usia pada node yang bersangkutan
}

// Fungsi untuk menampilkan seluruh data dalam linked list
void tampilkanData() {
    if (head == NULL) {            // Jika linked list kosong
        cout << "List kosong!" << endl;
        return;
    }

    Node* temp = head;
    cout << "Nama\tUsia" << endl;
    while (temp != NULL) {         // Menampilkan data pada setiap node
        cout << temp->nama << "\t" << temp->usia << endl;
        temp = temp->next;
    }
}

int main() {
    string nama, namaBaru;
    int usia, usiaBaru, posisi;
    int pilihan;

    cout << "Masukkan nama dan usia anda:" << endl;
    cout << "Nama: ";
    cin >> nama;
    cout << "Usia: ";
    cin >> usia;
    insertDepan(nama, usia);   // Menyisipkan data mahasiswa pertama

    do {
        cout << "\nMenu:\n";
        cout << "1. Tambah Data posisi yang diinginkan\n";
        cout << "2. Tambah Data\n";
        cout << "3. Hapus Data\n";
        cout << "4. Ubah Data\n";
        cout << "5. Tampilkan Seluruh Data\n";
        cout << "6. Keluar\n";
        cout << "Pilih menu: ";
        cin >> pilihan;

        switch (pilihan) {
            case 1:
                cout << "Masukkan nama: ";
                cin >> nama;
                cout << "Masukkan usia: ";
                cin >> usia;
                cout << "Masukkan posisi: ";
                cin >> posisi;
                insertTertentu(nama, usia, posisi);  // Menyisipkan data pada posisi tertentu
                break;
            case 2:
                cout << "Masukkan nama: ";
                cin >> nama;
                cout << "Masukkan usia: ";
                cin >> usia;
                insertBelakang(nama, usia);  // Menyisipkan data di belakang
                break;
            case 3:
                cout << "Masukkan nama yang ingin dihapus: ";
                cin >> nama;
                hapusData(nama);  // Menghapus data berdasarkan nama
                break;
            case 4:
                cout << "Masukkan nama yang ingin diubah: ";
                cin >> nama;
                cout << "Masukkan nama baru: ";
                cin >> namaBaru;
                cout << "Masukkan usia baru: ";
                cin >> usiaBaru;
                ubahData(nama, namaBaru, usiaBaru);  // Mengubah data berdasarkan nama
                break;
            case 5:
                cout << "Data yang dimasukkan:" << endl;
                tampilkanData();  // Menampilkan seluruh data
                break;
            case 6:
                cout << "Program selesai.\n";
                break;
            default:
                cout << "Pilihan tidak valid. Silakan pilih lagi.\n";
        }
    } while (pilihan != 6);

    return 0;
}


```
#### Output:


![Screenshot 2024-03-26 133652](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/f146759b-5802-4658-ad8e-565d9ee23a49)

Kode diatas menunjukkan implementasi dari singly linked list dengan berbagai operasi seperti penambahan node di depan, belakang, dan pada posisi tertentu, penghapusan node berdasarkan nama, modifikasi data node, dan menampilkan semua node. Struktur Node didefinisikan dengan nama, usia, dan pointer ke node berikutnya. Pointer head menunjuk ke node pertama dalam list. Program ini mencakup fungsi untuk memasukkan node di awal (insertDepan), di akhir (insertBelakang), di posisi tertentu (insertTertentu), menghapus node berdasarkan nama (hapusData), memperbarui data node (ubahData), dan menampilkan semua node (tampilkanData). Fungsi main menyediakan antarmuka berbasis menu untuk pengguna berinteraksi dengan linked list.

#### Full code Screenshot:
![Screenshot 2024-03-26 141607](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/74eaa999-5489-4a8e-a3df-01bdfdfa570f)


### 2. Soal mengenai Double Linked List
Modifikasi Guided Double Linked List dilakukan dengan penambahan operasi untuk menambah data, menghapus, dan update di tengah / diurutan tertentu yang diminta. Selain itu, buatlah agar tampilannyamenampilkan Nama produk dan harga.
Nama Produk  Harga
Originote    60.000
Somethinc    150.000
Skintific    100.000
Wardah       50.000
Hanasui      30.000

Case:
1. Tambahkan produk Azarine dengan harga 65000 diantara
Somethinc dan Skintific
2. Hapus produk wardah
3. Update produk Hanasui menjadi Cleora dengan harga 55.000
4. Tampilkan menu seperti dibawah ini
Toko Skincare Purwokerto
1. Tambah Data
2. Hapus Data
3. Update Data
4. Tambah Data Urutan Tertentu
5. Hapus Data Urutan Tertentu
6. Hapus Seluruh Data
7. Tampilkan Data
8. Exit
Pada menu 7, tampilan akhirnya akan menjadi seperti dibawah
ini :

Nama Produk Harga
Originote 60.000
Somethinc 150.000
Azarine 65.000
Skintific 100.000
Cleora 55.000
```C++
#include <iostream>
#include <string>
using namespace std;

class Node {
public:
    string namaProduk;  // Nama produk
    double harga;       // Harga produk
    Node* prev;         // Pointer ke node sebelumnya
    Node* next;         // Pointer ke node berikutnya
};

class DoublyLinkedList {
public:
    Node* head;         // Pointer ke node pertama
    Node* tail;         // Pointer ke node terakhir

    // Constructor untuk inisialisasi linked list kosong
    DoublyLinkedList() {
        head = nullptr;
        tail = nullptr;
    }

    // Menambahkan node baru di depan linked list
    void push(string namaProduk, double harga) {
        Node* newNode = new Node;   // Membuat node baru
        newNode->namaProduk = namaProduk;   // Menetapkan nama produk
        newNode->harga = harga;     // Menetapkan harga produk
        newNode->prev = nullptr;    // Mengatur node sebelumnya menjadi null

        // Menyambungkan node baru ke linked list
        newNode->next = head;       // Pointer next node baru menunjuk ke head (node pertama)

        // Jika linked list tidak kosong, atur prev head menjadi node baru
        if (head != nullptr) {
            head->prev = newNode;
        } else {
            tail = newNode;     // Jika linked list kosong, atur node baru sebagai tail
        }

        head = newNode;     // Atur node baru sebagai head
    }

    // Menghapus node pertama dari linked list
    void pop() {
        // Jika linked list kosong, langsung kembali
        if (head == nullptr) {
            return;
        }

        Node* temp = head;  // Simpan pointer ke head sementara
        head = head->next;  // Pindahkan head ke node berikutnya

        // Jika setelah penghapusan, linked list tidak kosong
        if (head != nullptr) {
            head->prev = nullptr;   // Atur prev dari head menjadi null
        } else {
            tail = nullptr;     // Jika setelah penghapusan linked list menjadi kosong, atur tail menjadi null
        }

        delete temp;    // Hapus node yang telah di-pop
    }

    // Mengupdate informasi produk berdasarkan nama produk yang diberikan
    bool update(string oldNamaProduk, string newNamaProduk, double newHarga) {
        Node* current = head;   // Pointer untuk traversing linked list
        while (current != nullptr) {
            // Jika nama produk pada node saat ini sama dengan nama produk yang ingin diupdate
            if (current->namaProduk == oldNamaProduk) {
                // Update informasi produk
                current->namaProduk = newNamaProduk;
                current->harga = newHarga;
                return true;    // Kembalikan true jika update berhasil
            }
            current = current->next;    // Pindah ke node berikutnya
        }
        return false;   // Kembalikan false jika nama produk tidak ditemukan
    }

    // Menghapus semua node dari linked list
    void deleteAll() {
        Node* current = head;   // Pointer untuk traversing linked list
        while (current != nullptr) {
            Node* temp = current;   // Simpan pointer ke node saat ini sementara
            current = current->next;    // Pindah ke node berikutnya
            delete temp;    // Hapus node yang disimpan
        }
        head = nullptr;     // Atur head dan tail menjadi null karena linked list kosong
        tail = nullptr;
    }

    // Menampilkan isi linked list
    void display() {
        Node* current = head;   // Pointer untuk traversing linked list
        while (current != nullptr) {
            // Tampilkan nama produk dan harganya
            cout << current->namaProduk << " " << current->harga << endl;
            current = current->next;    // Pindah ke node berikutnya
        }
    }

    // Menambahkan node baru setelah node dengan nama produk tertentu
    void insertAfter(string prevNamaProduk, string namaProduk, double harga) {
        Node* temp = head;   // Pointer untuk mencari node dengan nama produk tertentu
        // Mencari node dengan nama produk tertentu atau mencapai akhir linked list
        while (temp != nullptr && temp->namaProduk != prevNamaProduk) {
            temp = temp->next;  // Pindah ke node berikutnya
        }
        // Jika node dengan nama produk tertentu tidak ditemukan
        if (temp == nullptr) {
            cout << "Produk sebelumnya tidak ditemukan." << endl;
            return;
        }
        // Jika node ditemukan, buat node baru dan sisipkan setelah node tersebut
        Node* newNode = new Node;
        newNode->namaProduk = namaProduk;
        newNode->harga = harga;
        newNode->next = temp->next;
        newNode->prev = temp;
        // Sambungkan node baru ke linked list
        if (temp->next != nullptr) {
            temp->next->prev = newNode;
        }
        temp->next = newNode;
    }

    // Menambahkan node baru di awal linked list
    void insertAtBeginning(string namaProduk, double harga) {
        Node* newNode = new Node;   // Buat node baru
        newNode->namaProduk = namaProduk;   // Tetapkan nama produk
        newNode->harga = harga;     // Tetapkan harga produk
        newNode->next = head;       // Sambungkan node baru ke head
        newNode->prev = nullptr;    // Atur prev dari node baru menjadi null
        // Jika linked list tidak kosong, atur prev head menjadi node baru
        if (head != nullptr) {
            head->prev = newNode;
        } else {
            tail = newNode;     // Jika linked list kosong, atur node baru sebagai tail
        }
        head = newNode;     // Atur node baru sebagai head
    }

    // Menghapus node dengan nama produk tertentu
    void deleteNode(string namaProduk) {
        // Jika linked list kosong, langsung kembali
        if (head == nullptr)
            return;
        Node* temp = head;  // Pointer untuk mencari node dengan nama produk tertentu
        // Mencari node dengan nama produk tertentu atau mencapai akhir linked list
        while (temp != nullptr && temp->namaProduk != namaProduk) {
            temp = temp->next;  // Pindah ke node berikutnya
        }
        // Jika node dengan nama produk tertentu tidak ditemukan
        if (temp == nullptr)
            return;
        // Jika node ditemukan, hapus node tersebut dari linked list
        if (temp->prev != nullptr)            
            temp->prev->next = temp->next;
        if (temp->next != nullptr)
            temp->next->prev = temp->prev;
        if (temp == head)
            head = temp->next;
        if (temp == tail)
            tail = temp->prev;
        delete temp;    // Hapus node yang ditemukan
    }
};

int main() {
    DoublyLinkedList list;  // Membuat objek DoublyLinkedList
    while (true) {  // Loop utama program
        // Menampilkan menu utama
        cout << "Toko Skincare Purwokerto" << endl;
        cout << "1. Tambah Data" << endl;
        cout << "2. Hapus Data" << endl;
        cout << "3. Update Data" << endl;
        cout << "4. Tambah Data Urutan Tertentu" << endl;
        cout << "5. Hapus Data Urutan Tertentu" << endl;
        cout << "6. Hapus Seluruh Data" << endl;
        cout << "7. Tampilkan Data" << endl;
        cout << "8. Exit" << endl;
        int choice;
        cout << "Masukkan pilihan Anda: ";
        cin >> choice;  // Meminta input pilihan dari pengguna
        switch (choice) {  // Memproses pilihan pengguna
            case 1: {  // Pilihan untuk menambah data
                string namaProduk;
                double harga;
                cout << "Masukkan nama produk: ";
                cin >> namaProduk;  // Meminta input nama produk
                cout << "Masukkan harga: ";
                cin >> harga;   // Meminta input harga produk
                list.push(namaProduk, harga);  // Memanggil fungsi push untuk menambahkan data
                break;
            }
            case 2: {  // Pilihan untuk menghapus data
                string namaProduk;
                cout << "Masukkan nama produk yang ingin dihapus: ";
                cin >> namaProduk;  // Meminta input nama produk yang ingin dihapus
                list.deleteNode(namaProduk);  // Memanggil fungsi deleteNode untuk menghapus data
                break;
            }
            case 3: {  // Pilihan untuk memperbarui data
                string oldNamaProduk, newNamaProduk;
                double newHarga;
                cout << "Masukkan nama produk yang ingin diupdate: ";
                cin >> oldNamaProduk;  // Meminta input nama produk yang ingin diperbarui
                cout << "Masukkan nama produk baru: ";
                cin >> newNamaProduk;  // Meminta input nama produk baru
                cout << "Masukkan harga baru: ";
                cin >> newHarga;    // Meminta input harga baru
                bool updated = list.update(oldNamaProduk, newNamaProduk, newHarga);  // Memanggil fungsi update
                if (!updated) {
                    cout << "Data tidak ditemukan" << endl;  // Menampilkan pesan jika data tidak ditemukan
                }
                break;
            }
            case 4: {  // Pilihan untuk menambah data pada urutan tertentu
                string prevNamaProduk, namaProduk;
                double harga;
                cout << "Masukkan nama produk sebelumnya: ";
                cin >> prevNamaProduk;  // Meminta input nama produk sebelumnya
                cout << "Masukkan nama produk baru: ";
                cin >> namaProduk;  // Meminta input nama produk baru
                cout << "Masukkan harga: ";
                cin >> harga;   // Meminta input harga produk
                list.insertAfter(prevNamaProduk, namaProduk, harga);  // Memanggil fungsi insertAfter untuk menyisipkan data
                break;
            }
            case 5: {  // Pilihan untuk menghapus data pada urutan tertentu
                // Kode untuk menghapus data di urutan tertentu
                break;
            }
            case 6: {  // Pilihan untuk menghapus semua data
                list.deleteAll();  // Memanggil fungsi deleteAll untuk menghapus semua data
                break;
            }
            case 7: {  // Pilihan untuk menampilkan data
                cout << "Data Produk:" << endl;
                list.display();  // Memanggil fungsi display untuk menampilkan semua data
                break;
            }
            case 8: {  // Pilihan untuk keluar dari program
                return 0;  // Menghentikan program
            }
            default: {  // Pilihan tidak valid
                cout << "Pilihan tidak valid" << endl;
                break;
            }
        }
    }
    return 0;  // Mengakhiri program
}



```
#### Output:

![Screenshot 2024-03-26 113809](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/3425db6f-2c92-431f-8fd4-534e7a300e8c)

Kode di atas mengimplementasikan struktur data Doubly Linked List untuk menyimpan informasi tentang produk skincare, termasuk nama produk dan harga, dengan memungkinkan operasi seperti menambahkan data ke awal list, menghapus data berdasarkan nama produk, memperbarui nama dan harga produk, menambahkan data di tengah list berdasarkan nama produk yang ada sebelumnya, dan menampilkan semua data dalam list. Program ini menyediakan menu interaktif di `main()` yang memungkinkan pengguna untuk memilih operasi yang ingin dilakukan, seperti menambahkan data baru, menghapus data, memperbarui data, menambahkan data di tengah list, menghapus semua data, dan menampilkan data. Fungsi `push` digunakan untuk menambahkan produk baru ke awal list, `pop` untuk menghapus produk dari awal list, `update` untuk memperbarui nama dan harga produk, `deleteAll` untuk menghapus semua produk dalam list, dan `display` untuk menampilkan semua produk dalam list. Fungsi `insertAfter` memungkinkan penambahan produk di tengah list berdasarkan nama produk yang ada sebelumnya, dan `deleteNode` digunakan untuk menghapus produk berdasarkan nama produk. Program ini menunjukkan bagaimana mengelola dan memanipulasi data dalam Doubly Linked List dengan berbagai operasi yang diminta, termasuk penambahan, penghapusan, dan penampilan data, serta bagaimana menambahkan data ke posisi tertentu dalam list. Selain itu, program ini juga menunjukkan bagaimana menangani kasus khusus seperti memperbarui nama produk dan harga, serta menampilkan data produk dalam format yang mudah dibaca.
#### Full code Screenshot:
![Screenshot 2024-03-26 143054](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/f8713950-f9b1-4231-88b7-c99689ddac2c)



## Kesimpulan
Kesimpulannya, Dari materi dan guided ataupun unguided di atas membahas tentang struktur data Linked List dalam ilmu komputer, yang merupakan sebuah struktur data yang digunakan untuk menyimpan sejumlah objek data biasanya secara terurut. Linked List terdiri dari dua jenis utama: Single Linked List dan Double Linked List.
1. **Single Linked List**:
   - Merupakan kumpulan elemen data (node) yang urutannya ditentukan oleh suatu pointer.
   - Setiap node terdiri dari dua bagian: INFO (berisi informasi tentang elemen data) dan NEXT (berisi alamat dari elemen selanjutnya).
   - Operasi yang dapat dilakukan meliputi sisip depan, sisip belakang, sisip posisi, hapus posisi, ubah data, dan lainnya.
2. **Double Linked List**:
   - Memiliki struktur yang sama dengan Single Linked List, tetapi setiap node memiliki rujukan pada node sebelumnya (PREV) dan berikutnya (NEXT).
   - Tiap node memiliki pointer yang menunjuk ke node sesudahnya dan pointer yang menunjuk ke node sebelumnya.
   - Operasi yang dapat dilakukan mirip dengan Single Linked List, ditambah dengan operasi khusus yang memanfaatkan rujukan ke node sebelumnya.

Selain itu, kedua jenis Linked List tersebut juga dilengkapi dengan operasi pengelolaan data seperti sisip depan, sisip belakang, sisip posisi, hapus posisi, ubah data, dan lainnya.

Program-program yang diberikan sebagai contoh implementasi dari kedua jenis Linked List tersebut menunjukkan bagaimana cara menggunakan dan mengelola struktur data Linked List, termasuk operasi-operasi dasar seperti penambahan, penghapusan, pembaruan data, dan penampilan data. Program-program tersebut menyediakan menu interaktif bagi pengguna untuk melakukan operasi-operasi tersebut sesuai dengan kebutuhan.

Dengan demikian, materi tersebut membahas konsep dasar dan implementasi dari Linked List, serta memberikan contoh program yang dapat digunakan untuk memahami konsep tersebut secara praktis.
## Referensi
[1] Asisten Praktikum, “Modul 4 Linked List Circular And Non Circular", Googgle Classroom, 2024.
[2]Sihombing, Johnson. "Penerapan Stack Dan Queue Pada Array Dan Linked List Dalam Java." INFOKOM (Informatika & Komputer) 7.2 (2019): 15-24.



