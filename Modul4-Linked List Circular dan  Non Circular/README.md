# <h1 align="center">Laporan Praktikum Modul Single and Double Linked List</h1>
<p align="center">Wahyu Hidayat</p>
<p align="center">2311102178 / 11-E-IF</p>


## Dasar Teori

**Linked List**

#### 1. Linked List Non Circular
Linked list non circular merupakan linked list dengan node pertama (head) dan node terakhir (tail) yang tidak saling terhubung. Pointer terakhir (tail) pada Linked List ini selalu bernilai ‘NULL’ sebagai pertanda data terakhir dalam list nya. Linked list non circular dapat digambarkan sebagai berikut[1].

![Screenshot 2024-04-02 233253](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/881b40a6-0e82-4fb4-9303-6befd0ca39a7)

<center>Gambar 1. Single Linked List Non Circular</center>


#### A. Singly Linked List
Pada list jenis ini, tiap node nya memiliki field yang berisi pointer ke node berikutnya dan juga memiliki field yang berisi data. Akhir linked list ditandai dengan node terakhir yang menunjuk ke null yang akan digunakan sebagai kondisi berhenti saat pembacaan linked list[2].

![Screenshot 2024-04-02 232506](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/b2b8e5e8-b7b7-498d-8924-68b72c68c410)

<center>Gambar 2. Ilustrasi singly linked list</center>


#### B. Doubly Linked List
Merupakan linked list dengan menggunakan pointer, dimana setiap node memiliki tiga buah field, yaitu : field pointer yang menunjuk ke pointer berikutnya, field pointer yang menunjuk ke pointer sebelumnya dan field yang berisi data dari node tersebut. Semenatara pointer next dan prev-nya menunjuk ke null[2].

![Screenshot 2024-04-02 232637](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/2cfe424b-0842-4190-9739-4a08e42b0a84)


<center>Gambar 3. Ilustrasi doubly linked list</center>



#### 2. Linked List Circular
Linked list circular merupakan linked list yang tidak memiliki akhir karena node terakhir (tail) tidak bernilai ‘NULL’, tetapi terhubung dengan node pertama (head). Saat menggunakan linked list circular kita membutuhkan dummy node atau node pengecoh yang biasanya dinamakan dengan node current supaya program dapat berhenti menghitung data ketika node current mencapai node pertama (head). Linked list circular dapat digunakan untuk menyimpan data yang perlu diakses secara berulang, seperti daftar putar lagu, daftar pesan dalam antrian, atau penggunaan memori berulang dalam suatu aplikasi. Linked list circular dapat digambarkan sebagai berikut[1].

![Screenshot 2024-04-02 232847](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/09b1cd81-40b1-4bd1-8f31-921f2d4fda23)


<center>Gambar 4. Single Linked List Circular</center>


#### A. Singly Circular Linked List
Adalah singly linked list yang pointer next-nya menunjuk ke dirinya sendiri (proses rekursif), jika terdiri dari beberapa node maka pointer terakhirnya akan menunjuk ke pointer terdepannya[2]. 

![Screenshot 2024-04-02 230935](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/6bd1c853-b49a-48aa-aaa9-be074be78cde)


<center>Gambar 5. Ilustrasi singly circular linked list</center>

#### B. Doubly Circular Linked List
Merupakan sutau double linked list yang pointer next dan pointer prev-nya menunjuk ke dirinya sendiri secara circular[2].

![Screenshot 2024-04-02 231209](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/912221f0-1c2e-4dce-afff-4a48e3e9e0de)


<center>Gambar 6. Ilustrasi Doubly circular linked list </center>



## Guided 
### 1. Linked List Non Circular

```C++
#include <iostream>
using namespace std;

// Struktur Node untuk merepresentasikan elemen dalam linked list
struct Node {
    int data;       // Data yang disimpan dalam node
    Node *next;     // Pointer yang menunjukkan ke node selanjutnya dalam linked list
};

// Deklarasi variabel global untuk menandai kepala (head) dan ekor (tail) dari linked list
Node *head;
Node *tail;

// Fungsi untuk menginisialisasi linked list, dijalankan di awal program
void init() {
    head = NULL;    // Kepala dan ekor diatur ke NULL untuk menandakan linked list kosong
    tail = NULL;
}

// Fungsi untuk memeriksa apakah linked list kosong
bool isEmpty() {
    return head == NULL;
}

// Fungsi untuk menambahkan elemen di depan linked list
void insertDepan(int nilai) {
    Node *baru = new Node;  // Membuat node baru
    baru->data = nilai;     // Mengisi data node baru
    baru->next = NULL;      // Mengatur pointer next node baru ke NULL
    if (isEmpty()) {        // Jika linked list kosong, maka node baru menjadi kepala dan ekor
        head = tail = baru;
    } else {                // Jika tidak kosong, node baru ditambahkan di depan dan diatur sebagai kepala baru
        baru->next = head;
        head = baru;
    }
}

// Fungsi untuk menambahkan elemen di belakang linked list
void insertBelakang(int nilai) {
    Node *baru = new Node;  // Membuat node baru
    baru->data = nilai;     // Mengisi data node baru
    baru->next = NULL;      // Mengatur pointer next node baru ke NULL
    if (isEmpty()) {        // Jika linked list kosong, maka node baru menjadi kepala dan ekor
        head = tail = baru;
    } else {                // Jika tidak kosong, node baru ditambahkan di belakang dan diatur sebagai ekor baru
        tail->next = baru;
        tail = baru;
    }
}

// Fungsi untuk menghitung jumlah elemen dalam linked list
int hitungList() {
    Node *hitung = head;    // Pointer untuk traversal linked list
    int jumlah = 0;         // Variabel untuk menyimpan jumlah elemen
    while (hitung != NULL) {
        jumlah++;           // Increment jumlah saat traversal
        hitung = hitung->next;  // Pindah ke node berikutnya
    }
    return jumlah;
}

// Fungsi untuk menambahkan elemen di posisi tengah linked list
void insertTengah(int data, int posisi) {
    if (posisi < 1 || posisi > hitungList()) {  // Memeriksa apakah posisi valid
        cout << "Posisi diluar jangkauan" << endl; // Jika tidak, tampilkan pesan kesalahan
    } else if (posisi == 1) {   // Jika posisi adalah 1, tambahkan di depan
        insertDepan(data);
    } else {
        Node *baru = new Node;  // Membuat node baru
        baru->data = data;      // Mengisi data node baru
        Node *bantu = head;     // Pointer untuk traversal
        int nomor = 1;          // Variabel untuk menyimpan nomor posisi saat traversal
        while (nomor < posisi - 1) {    // Traversal hingga posisi sebelumnya
            bantu = bantu->next;
            nomor++;
        }
        baru->next = bantu->next;   // Mengatur pointer next node baru
        bantu->next = baru;
    }
}

// Fungsi untuk menghapus elemen di depan linked list
void hapusDepan() {
    if (!isEmpty()) {           // Memeriksa apakah linked list tidak kosong
        Node *hapus = head;     // Menunjukkan node yang akan dihapus
        if (head->next != NULL) {   // Jika masih ada node lain setelah kepala
            head = head->next;      // Kepala diubah menjadi node berikutnya
        } else {
            head = tail = NULL;     // Jika tidak ada node lain, kepala dan ekor diatur ke NULL
        }
        delete hapus;           // Menghapus node yang dihapus
    } else {
        cout << "List kosong!" << endl;    // Jika linked list kosong, tampilkan pesan
    }
}

// Fungsi untuk menghapus elemen di belakang linked list
void hapusBelakang() {
    if (!isEmpty()) {           // Memeriksa apakah linked list tidak kosong
        if (head != tail) {     // Jika masih ada lebih dari satu elemen dalam linked list
            Node *hapus = tail; // Menunjukkan node yang akan dihapus
            Node *bantu = head; // Pointer untuk traversal
            while (bantu->next != tail) {  // Traversal hingga sebelum ekor
                bantu = bantu->next;
            }
            tail = bantu;       // Ekor diatur ke node sebelumnya
            tail->next = NULL;  // Mengatur pointer next ekor ke NULL
        } else {
            delete head;        // Jika hanya ada satu elemen, hapus node tersebut
            head = tail = NULL; // Kepala dan ekor diatur ke NULL
        }
    } else {
        cout << "List kosong!" << endl;    // Jika linked list kosong, tampilkan pesan
    }
}

// Fungsi untuk menghapus elemen di posisi tengah linked list
void hapusTengah(int posisi) {
    if (posisi < 1 || posisi > hitungList()) {  // Memeriksa apakah posisi valid
        cout << "Posisi di luar jangkauan" << endl; // Jika tidak, tampilkan pesan kesalahan
    } else if (posisi == 1) {   // Jika posisi adalah 1, hapus elemen di depan
        hapusDepan();
    } else {
        Node *bantu = head;     // Pointer untuk traversal
        Node *hapus;            // Menunjukkan node yang akan dihapus
        int nomor = 1;          // Variabel untuk menyimpan nomor posisi saat traversal
        while (nomor < posisi - 1) {    // Traversal hingga posisi sebelumnya
            bantu = bantu->next;
            nomor++;
        }
        hapus = bantu->next;    // Menunjukkan node yang akan dihapus
        bantu->next = hapus->next; // Mengatur pointer next node sebelumnya
        delete hapus;           // Menghapus node yang dihapus
    }
}

// Fungsi untuk mengubah data elemen di depan linked list
void ubahDepan(int data) {
    if (!isEmpty()) {           // Memeriksa apakah linked list tidak kosong
        head->data = data;      // Mengubah data pada kepala
    } else {
        cout << "List masih kosong!" << endl;   // Jika linked list kosong, tampilkan pesan
    }
}

// Fungsi untuk mengubah data elemen di belakang linked list
void ubahBelakang(int data) {
    if (!isEmpty()) {           // Memeriksa apakah linked list tidak kosong
        tail->data = data;      // Mengubah data pada ekor
    } else {
        cout << "List masih kosong!" << endl;   // Jika linked list kosong, tampilkan pesan
    }
}

// Fungsi untuk mengubah data elemen di posisi tengah linked list
void ubahTengah(int data, int posisi) {
    if (!isEmpty()) {           // Memeriksa apakah linked list tidak kosong
        if (posisi < 1 || posisi > hitungList()) {  // Memeriksa apakah posisi valid
            cout << "Posisi di luar jangkauan" << endl; // Jika tidak, tampilkan pesan kesalahan
        } else if (posisi == 1) {   // Jika posisi adalah 1, ubah elemen di depan
            ubahDepan(data);
        } else {
            Node *bantu = head;     // Pointer untuk traversal
            int nomor = 1;          // Variabel untuk menyimpan nomor posisi saat traversal
            while (nomor < posisi) {    // Traversal hingga posisi yang diinginkan
                bantu = bantu->next;
                nomor++;
            }
            bantu->data = data;     // Mengubah data pada posisi yang diinginkan
        }
    } else {
        cout << "List masih kosong!" << endl;   // Jika linked list kosong, tampilkan pesan
    }
}

// Fungsi untuk membersihkan linked list dari semua elemen
void clearList() {
    Node *bantu = head;     // Pointer untuk traversal
    while (bantu != NULL) { // Loop hingga semua elemen terhapus
        Node *hapus = bantu;    // Menunjukkan node yang akan dihapus
        bantu = bantu->next;    // Pindah ke node berikutnya
        delete hapus;           // Menghapus node yang dihapus
    }
    head = tail = NULL;     // Kepala dan ekor diatur ke NULL setelah linked list kosong
    cout << "List berhasil terhapus!" << endl;    // Menampilkan pesan berhasil
}

// Fungsi untuk menampilkan semua elemen dalam linked list
void tampil() {
    Node *bantu = head;     // Pointer untuk traversal
    if (!isEmpty()) {       // Memeriksa apakah linked list tidak kosong
        while (bantu != NULL) { // Loop hingga mencapai akhir linked list
            cout << bantu->data << " ";    // Menampilkan data dari setiap node
            bantu = bantu->next;    // Pindah ke node berikutnya
        }
        cout << endl;   // Mencetak baris baru setelah selesai menampilkan semua elemen
    } else {
        cout << "List masih kosong!" << endl;   // Jika linked list kosong, tampilkan pesan
    }
}

// Fungsi utama program
int main() {
    init(); // Inisialisasi linked list
    insertDepan(3); // Menambahkan elemen 3 di depan linked list
    tampil();   // Menampilkan isi linked list
    insertBelakang(5);  // Menambahkan elemen 5 di belakang linked list
    tampil();   // Menampilkan isi linked list
    insertDepan(2); // Menambahkan elemen 2 di depan linked list
    tampil();   // Menampilkan isi linked list
    insertDepan(1); // Menambahkan elemen 1 di depan linked list
    tampil();   // Menampilkan isi linked list
    hapusDepan();   // Menghapus elemen di depan linked list
    tampil();   // Menampilkan isi linked list
    hapusBelakang();    // Menghapus elemen di belakang linked list
    tampil();   // Menampilkan isi linked list
    insertTengah(7, 2); // Menambahkan elemen 7 di posisi tengah ke-2 linked list
    tampil();   // Menampilkan isi linked list
    hapusTengah(2); // Menghapus elemen di posisi tengah ke-2 linked list
    tampil();   // Menampilkan isi linked list
    ubahDepan(1);   // Mengubah elemen di depan linked list menjadi 1
    tampil();   // Menampilkan isi linked list
    ubahBelakang(8);    // Mengubah elemen di belakang linked list menjadi 8
    tampil();   // Menampilkan isi linked list
    ubahTengah(11, 2);  // Mengubah elemen di posisi tengah ke-2 linked list menjadi 11
    tampil();   // Menampilkan isi linked list
    clearList();    // Menghapus semua elemen dalam linked list
    return 0;   // Mengakhiri program
}


```
#### Output:

![Screenshot 2024-04-03 141850](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/ef8e8b3e-0554-48d3-b86c-447a740b58d5)

Program ini mendemonstrasikan penggunaan berbagai fungsi untuk mengelola linked list dengan elemen bertipe integer. Fungsi-fungsi tersebut meliputi inisialisasi linked list (init), pengecekan kosong (isEmpty), penambahan elemen di depan (insertDepan), belakang (insertBelakang), dan posisi tengah (insertTengah), penghapusan elemen di depan (hapusDepan), belakang (hapusBelakang), dan posisi tengah (hapusTengah), serta pengubahan data elemen di depan, belakang, dan posisi tengah (ubahDepan, ubahBelakang, ubahTengah). Selain itu, program ini juga mencakup fungsi untuk menghitung jumlah elemen dalam linked list (hitungList), menampilkan semua elemen (tampil), dan membersihkan linked list dari semua elemen (clearList). Dalam fungsi main, program ini menunjukkan cara menggunakan fungsi-fungsi tersebut untuk melakukan operasi pada linked list, seperti menambahkan elemen di depan dan belakang, menghapus elemen di depan dan belakang, menambahkan elemen di posisi tengah, menghapus elemen di posisi tengah, mengubah data elemen di depan, belakang, dan posisi tengah, serta menampilkan isi linked list sebelum dan setelah setiap operasi. Ini menunjukkan fleksibilitas dan kegunaan linked list dalam berbagai operasi data.


#### Full code Screenshot:

![Screenshot 2024-04-03 142106](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/d86bec18-41a8-4b31-9981-d9dc2fa0c65e)


### 2. Linked List Circular
```C++
#include <iostream>
using namespace std;

struct Node
{
    string data;
    Node *next;
};

Node *head, *tail, *baru, *bantu, *hapus;

void init()
{
    head = NULL;
    tail = head;
}

// Pengecekan
int isEmpety()
{
    if (head == NULL)
        return 1; //true
    else
        return 0; //false
}

//Buat Node baru
void buatNode(string data)
{
    baru = new Node;
    baru->data = data;
    baru->next = NULL;
}

//Hitung List
int hitungList()
{
    bantu = head;
    int jumlah = 0;

    while (bantu != NULL)
    {
        jumlah++;
        bantu = bantu->next;
    }

    return jumlah;
}

//Tambah Depan
void insertDepan(string data)
{
    //Buat Node baru
    buatNode(data);

    if (isEmpety() == 1)
    {
        head = baru;
        tail = head;
        baru->next = head;
    }
    else
    {
        while (tail->next != head)
        {
            tail = tail->next;
        }
        baru->next = head;
        head = baru;
        tail->next = head;
    }
}

//Tambah Belakang
void insertBelakang(string data)
{
    buatNode(data);

    if (isEmpety() == 1)
    {
        head = baru;
        tail = head;
        baru->next = head;
    }
    else
    {
        while (tail->next != head)
        {
            tail = tail->next;
        }
        tail->next = baru;
        baru->next = head;
        tail = baru;
    }
}

//Tambah Tengah
void insertTengah(string data, int posisi)
{
    if (isEmpety() == 1)
    {
        head = baru;
        tail = head;
        baru->next = head;
    }
    else
    {
        // transversing
        int nomor = 1;
        bantu = head;
        while (nomor < posisi - 1)
        {
            bantu = bantu->next;
            nomor++;
        }
        buatNode(data);
        baru->next = bantu->next;
        bantu->next = baru;
    }
}

//Hapus Depan
void hapusDepan()
{
    if (isEmpety() == 0)
    {
        hapus = head;
        tail = head;

        if (hapus->next == head)
        {
            head = NULL;
            tail = NULL;

            delete hapus;
        }
        else
        {
            while (tail->next != hapus)
            {
                tail = tail->next;
            }
            head = head->next;
            tail->next = head;
            hapus->next = NULL;

            delete hapus;
        }
    }
    else
    {
        cout << "List masih kosong" << endl;
    }
}

//Hapus Belakang
void hapusBelakang()
{
    if (isEmpety() == 0)
    {
        hapus = head;
        tail = head;
        if (hapus->next == head)
        {
            head = NULL;
            tail = NULL;

            delete hapus;
        }
        else
        {
            while (hapus->next != head)
            {
                hapus = hapus->next;
            }
            while (tail->next != hapus)
            {
                tail = tail->next;
            }
            tail->next = head;
            hapus->next = NULL;

            delete hapus;
        }
    }
    else
    {
        cout << "List Masih Kosong" << endl;
    }
}

//Hapus Tengah
void hapusTengah(int posisi)
{
    if (isEmpety() == 0)
    {
        //Transversing
        int nomor = 1;
        bantu = head;

        while (nomor < posisi - 1)
        {
            bantu = bantu->next;
            nomor++;
        }
        hapus = bantu->next;
        bantu->next = hapus->next;

        delete hapus;
    }
    else
    {
        cout << "List masih kosong" << endl;
    }
}

//Hapus List
void clearList()
{
    if (head != NULL)
    {
        hapus = head->next;

        while (hapus != head)
        {
            bantu = hapus->next;
            delete hapus;
            hapus = bantu;
        }
        delete head;
        head = NULL;
    }
    cout << "List berhasil terhapus" << endl;
}

//Tampilkan List
void tampil()
{
    if (isEmpety() == 0)
    {
        tail = head;
        do
        {
            cout << tail->data << ends;
            tail = tail->next;
        } while (tail != head);
        cout << endl;
    }
    else
    {
        cout << "List Masih Kosong" << endl;
    }
}

int main()
{
    init();
    insertDepan("Ayam");
    tampil();
    insertDepan("Bebek");
    tampil();
    insertBelakang("Cicak");
    tampil();
    insertBelakang("Domba");
    tampil();
    hapusBelakang();
    tampil();
    hapusDepan();
    tampil();
    insertTengah("sapi", 2);
    tampil();
    hapusTengah(2);
    tampil();

    return 0;
}


```
#### Output:

![Screenshot 2024-04-03 142236](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/52aa3df3-490e-490f-a643-935ed12a51e8)


Kode yang diberikan mengimplementasikan struktur data linked list dengan elemen bertipe string. Kode ini mendefinisikan struktur Node dengan dua anggota: data yang bertipe string dan next yang merupakan pointer ke node berikutnya. Fungsi-fungsi yang disediakan dalam kode ini meliputi inisialisasi linked list (init), pengecekan kosong (isEmpety), penambahan elemen di depan (insertDepan), belakang (insertBelakang), dan posisi tengah (insertTengah), penghapusan elemen di depan (hapusDepan), belakang (hapusBelakang), dan posisi tengah (hapusTengah), serta penghapusan semua elemen (clearList) dan menampilkan semua elemen (tampil). Program ini juga mencakup fungsi main yang mendemonstrasikan penggunaan fungsi-fungsi tersebut untuk melakukan operasi pada linked list.
secara lebih rincinya sebegai berikut:
init(): Menginisialisasi linked list dengan mengatur head dan tail menjadi NULL, menandakan bahwa linked list kosong.
isEmpety(): Mengembalikan 1 jika linked list kosong (head adalah NULL), dan 0 jika tidak.
buatNode(string data): Membuat node baru dengan data yang diberikan dan mengatur next menjadi NULL.
hitungList(): Menghitung jumlah node dalam linked list dengan melakukan traversal dari head sampai NULL.
insertDepan(string data): Menambahkan node baru di depan linked list. Jika linked list kosong, node baru menjadi head dan tail. Jika tidak, node baru menjadi head dan tail diperbarui untuk menunjuk ke node baru.
insertBelakang(string data): Menambahkan node baru di belakang linked list. Jika linked list kosong, node baru menjadi head dan tail. Jika tidak, node baru ditambahkan setelah tail dan tail diperbarui untuk menunjuk ke node baru.
insertTengah(string data, int posisi): Menambahkan node baru pada posisi tertentu dalam linked list. Fungsi ini melakukan traversal sampai mencapai posisi sebelum posisi yang diinginkan, lalu menambahkan node baru setelah node tersebut.
hapusDepan(): Menghapus node di depan linked list. Jika linked list hanya memiliki satu node, head dan tail diatur menjadi NULL. Jika lebih dari satu node, head diperbarui untuk menunjuk ke node berikutnya dan tail diperbarui jika perlu.
hapusBelakang(): Menghapus node di belakang linked list dengan mencari node sebelum tail dan mengatur next dari node tersebut menjadi NULL, lalu menghapus tail.
hapusTengah(int posisi): Menghapus node pada posisi tertentu dalam linked list dengan mencari node sebelum posisi yang diinginkan dan mengatur next dari node tersebut menjadi node setelah node yang dihapus.
clearList(): Menghapus semua node dalam linked list dengan melakukan traversal dan menghapus setiap node.
tampil(): Menampilkan semua elemen dalam linked list dengan melakukan traversal dari head sampai tail.

#### Full code Screenshot:

![Screenshot 2024-04-03 142847](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/36d88913-a497-495a-a159-6946997b1b84)

## Unguided 

### Buatlah program menu Linked List Non Circular untuk menyimpan Nama dan NIM mahasiswa, dengan menggunakan input dari user.
#### 1. Buatlah menu untuk menambahkan, mengubah, menghapus, dan melihat Nama dan NIM mahasiswa, berikut contoh tampilan output dari nomor 1:

• Tampilan Menu:
PROGRAM SINGLE LINKED LIST NON-CIRCULAR
1. Tambah Depan
2. Tambah Belakang
3. Tambah Tengah
4. Ubah Depan
5. Ubah Belakang
6. Ubah Tengah
7. Hapus Depan
8. Hapus Belakang
9. Hapus Tengah
10. Hapus List
11. TAMPILKAN
0. KELUAR
Pilih Operasi :
• Tampilan Operasi Tambah:

-Tambah Depan-
Masukkan Nama :

Masukkan NIM :
Data telah ditambahkan

-Tambah Tengah-
Masukkan Nama :

Masukkan NIM :
Masukkan Posisi :
Data telah ditambahkan
• Tampilan Operasi Hapus:

-Hapus Belakang-
Data (nama mahasiswa yang dihapus) berhasil dihapus

-Hapus Tengah-
Masukkan posisi :

Data (nama mahasiswa yang dihapus) berhasil dihapus

• Tampilan Operasi Ubah:

-Ubah Belakang-
Masukkan nama :

Masukkan NIM :
Data (nama lama) telah diganti dengan data (nama baru)

-Ubah Belakang-
Masukkan nama :

Masukkan NIM :
Masukkan posisi :
Data (nama lama) telah diganti dengan data (nama baru)

• Tampilan Operasi Tampil Data:
DATA MAHASISWA
NAMA NIM
Nama1 NIM1
Nama2 NIM2

*Buat tampilan output sebagus dan secantik mungkin sesuai kreatifitas anda
masing-masing, jangan terpaku pada contoh output yang diberikan
```C++
#include <iostream>
#include <string>
using namespace std;

// Struktur Node untuk merepresentasikan elemen dalam linked list
struct Node {
    string nama;
    string nim;
    Node *next;
};

// Deklarasi variabel global untuk menandai kepala (head) dan ekor (tail) dari linked list
Node *head;
Node *tail;

// Fungsi untuk menginisialisasi linked list, dijalankan di awal program
void init() {
    head = NULL;    // Kepala dan ekor diatur ke NULL untuk menandakan linked list kosong
    tail = NULL;
}

// Fungsi untuk memeriksa apakah linked list kosong
bool isEmpty() {
    return head == NULL;
}

// Fungsi untuk menambahkan elemen di depan linked list
void insertDepan(string nama, string nim) {
    Node *baru = new Node;
    baru->nama = nama;
    baru->nim = nim;
    baru->next = head;
    head = baru;
    if (tail == NULL) tail = baru;
}

// Fungsi untuk menambahkan elemen di belakang linked list
void insertBelakang(string nama, string nim) {
    Node *baru = new Node;
    baru->nama = nama;
    baru->nim = nim;
    baru->next = NULL;
    if (isEmpty()) {
        head = tail = baru;
    } else {
        tail->next = baru;
        tail = baru;
    }
}

// Fungsi untuk menambahkan elemen di posisi tengah linked list
void insertTengah(string nama, string nim, int posisi) {
    Node *baru = new Node;
    baru->nama = nama;
    baru->nim = nim;
    if (isEmpty()) {
        head = tail = baru;
        baru->next = NULL;
    } else {
        if (posisi == 1) {
            insertDepan(nama, nim);
        } else {
            Node *bantu = head;
            int nomor = 1;
            while (nomor < posisi - 1 && bantu->next != NULL) {
                bantu = bantu->next;
                nomor++;
            }
            baru->next = bantu->next;
            bantu->next = baru;
            if (baru->next == NULL) tail = baru;
        }
    }
}

// Fungsi untuk menghapus elemen di depan linked list
void hapusDepan() {
    if (!isEmpty()) {
        Node *hapus = head;
        head = head->next;
        if (head == NULL) tail = NULL;
        delete hapus;
    } else {
        cout << "List kosong!" << endl;
    }
}

// Fungsi untuk menghapus elemen di belakang linked list
void hapusBelakang() {
    if (!isEmpty()) {
        if (head != tail) {
            Node *bantu = head;
            while (bantu->next != tail) {
                bantu = bantu->next;
            }
            delete tail;
            tail = bantu;
            tail->next = NULL;
        } else {
            delete head;
            head = tail = NULL;
        }
    } else {
        cout << "List kosong!" << endl;
    }
}

// Fungsi untuk menghapus elemen di posisi tengah linked list
void hapusTengah(int posisi) {
    if (!isEmpty()) {
        Node *bantu = head;
        Node *hapus;
        int nomor = 1;
        while (nomor < posisi - 1) {
            bantu = bantu->next;
            nomor++;
        }
        hapus = bantu->next;
        bantu->next = hapus->next;
        delete hapus;
    } else {
        cout << "List kosong!" << endl;
    }
}

// Fungsi untuk mengubah data elemen di depan linked list
void ubahDepan(string nama, string nim) {
    if (!isEmpty()) {
        head->nama = nama;
        head->nim = nim;
    } else {
        cout << "List masih kosong!" << endl;
    }
}

// Fungsi untuk mengubah data elemen di belakang linked list
void ubahBelakang(string nama, string nim) {
    if (!isEmpty()) {
        tail->nama = nama;
        tail->nim = nim;
    } else {
        cout << "List masih kosong!" << endl;
    }
}

// Fungsi untuk mengubah data elemen di posisi tengah linked list
void ubahTengah(string nama, string nim, int posisi) {
    if (!isEmpty()) {
        Node *bantu = head;
        int nomor = 1;
        while (nomor < posisi) {
            bantu = bantu->next;
            nomor++;
        }
        bantu->nama = nama;
        bantu->nim = nim;
    } else {
        cout << "List masih kosong!" << endl;
    }
}

// Fungsi untuk membersihkan linked list dari semua elemen
void clearList() {
    Node *bantu = head;
    while (bantu != NULL) {
        Node *hapus = bantu;
        bantu = bantu->next;
        delete hapus;
    }
    head = tail = NULL;
    cout << "List berhasil terhapus!" << endl;
}

// Fungsi untuk menampilkan semua elemen dalam linked list
void tampil() {
    Node *bantu = head;
    if (!isEmpty()) {
        cout << "DATA MAHASISWA" << endl;
        cout << "NAMA\tNIM" << endl;
        while (bantu != NULL) {
            cout << bantu->nama << "\t" << bantu->nim << endl;
            bantu = bantu->next;
        }
    } else {
        cout << "List masih kosong!" << endl;
    }
}

// Fungsi utama program
int main() {
    init(); // Inisialisasi linked list
    int pilihan;
    string nama, nim;
    int posisi;

    do {
        cout << "PROGRAM SINGLE LINKED LIST NON-CIRCULAR" << endl;
        cout << "1. Tambah Depan" << endl;
        cout << "2. Tambah Belakang" << endl;
        cout << "3. Tambah Tengah" << endl;
        cout << "4. Ubah Depan" << endl;
        cout << "5. Ubah Belakang" << endl;
        cout << "6. Ubah Tengah" << endl;
        cout << "7. Hapus Depan" << endl;
        cout << "8. Hapus Belakang" << endl;
        cout << "9. Hapus Tengah" << endl;
        cout << "10. Hapus List" << endl;
        cout << "11. TAMPILKAN" << endl;
        cout << "0. KELUAR" << endl;
        cout << "Pilih Operasi : ";
        cin >> pilihan;

        switch (pilihan) {
            case 1:
                cout << "Masukkan Nama : ";
                cin >> nama;
                cout << "Masukkan NIM : ";
                cin >> nim;
                insertDepan(nama, nim);
                cout << "Data telah ditambahkan" << endl;
                break;
            case 2:
                cout << "Masukkan Nama : ";
                cin >> nama;
                cout << "Masukkan NIM : ";
                cin >> nim;
                insertBelakang(nama, nim);
                cout << "Data telah ditambahkan" << endl;
                break;
            case 3:
                cout << "Masukkan Nama : ";
                cin >> nama;
                cout << "Masukkan NIM : ";
                cin >> nim;
                cout << "Masukkan Posisi : ";
                cin >> posisi;
                insertTengah(nama, nim, posisi);
                cout << "Data telah ditambahkan" << endl;
                break;
            case 4:
                cout << "Masukkan Nama : ";
                cin >> nama;
                cout << "Masukkan NIM : ";
                cin >> nim;
                ubahDepan(nama, nim);
                cout << "Data telah diubah" << endl;
                break;
            case 5:
                cout << "Masukkan Nama : ";
                cin >> nama;
                cout << "Masukkan NIM : ";
                cin >> nim;
                ubahBelakang(nama, nim);
                cout << "Data telah diubah" << endl;
                break;
            case 6:
                cout << "Masukkan Nama : ";
                cin >> nama;
                cout << "Masukkan NIM : ";
                cin >> nim;
                cout << "Masukkan Posisi : ";
                cin >> posisi;
                ubahTengah(nama, nim, posisi);
                cout << "Data telah diubah" << endl;
                break;
            case 7:
                hapusDepan();
                cout << "Data telah dihapus" << endl;
                break;
            case 8:
                hapusBelakang();
                cout << "Data telah dihapus" << endl;
                break;
            case 9:
                cout << "Masukkan posisi : ";
                cin >> posisi;
                hapusTengah(posisi);
                cout << "Data telah dihapus" << endl;
                break;
            case 10:
                clearList();
                cout << "List telah dibersihkan" << endl;
                break;
            case 11:
                tampil();
                break;
            case 0:
                cout << "Keluar dari program" << endl;
                break;
            default:
                cout << "Pilihan tidak valid!" << endl;
                break;
        }
    } while (pilihan != 0);

    return 0;
}



```
#### Output:
![Screenshot 2024-04-03 144028](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/fcb181ae-6950-4452-b59d-cdf847bff28b)

Kode di atas mengimplementasikan operasi dasar pada struktur data linked list dengan elemen yang berisi informasi mahasiswa seperti nama dan NIM (Nomor Induk Mahasiswa) menggunakan bahasa pemrograman C++. Linked list adalah struktur data yang terdiri dari elemen-elemen yang terhubung secara langsung, di mana setiap elemen memiliki referensi ke elemen berikutnya dalam urutan. Kode ini mendefinisikan struktur Node yang berisi data string untuk nama dan NIM, serta pointer ke node berikutnya. Fungsi-fungsi yang disediakan memungkinkan inisialisasi linked list, pengecekan kosong, penambahan elemen di depan, belakang, dan posisi tengah, penghapusan elemen di depan, belakang, dan posisi tengah, serta pengubahan data elemen di depan, belakang, dan posisi tengah. Selain itu, kode ini juga mencakup fungsi untuk membersihkan linked list dari semua elemen dan menampilkan semua elemen.

Dalam fungsi main, program ini menyediakan menu interaktif untuk pengguna untuk memilih operasi yang ingin dilakukan pada linked list, seperti menambahkan, mengubah, menghapus, dan menampilkan elemen. Setiap operasi meminta pengguna untuk memasukkan informasi yang diperlukan, seperti nama, NIM, dan posisi untuk operasi tertentu. Program ini menggunakan loop do-while untuk menampilkan menu sampai pengguna memilih untuk keluar.

Fungsi insertDepan, insertBelakang, dan insertTengah digunakan untuk menambahkan elemen ke linked list. Fungsi hapusDepan, hapusBelakang, dan hapusTengah digunakan untuk menghapus elemen dari linked list. Fungsi ubahDepan, ubahBelakang, dan ubahTengah digunakan untuk mengubah data elemen dalam linked list. Fungsi clearList digunakan untuk menghapus semua elemen dalam linked list, dan fungsi tampil digunakan untuk menampilkan semua elemen dalam linked list.

Program ini menunjukkan bagaimana linked list dapat digunakan untuk menyimpan dan mengelola data dalam berbagai bentuk, dan bagaimana operasi dasar seperti penambahan, penghapusan, dan pengubahan data dapat dilakukan pada linked list.


#### 2. Setelah membuat menu tersebut, masukkan data sesuai urutan berikut, lalu tampilkan data yang telah dimasukkan. (Gunakan insert depan, belakang atau tengah)

Nama NIM
Jawad 23300001
[Nama Anda] [NIM Anda]
Farrel 23300003
Denis 23300005
Anis 23300008
Bowo 23300015
Gahar 23300040
Udin 23300048
Ucok 23300050
Budi 23300099

#### Output:
#### Menambahkan di depan dan belakang
![Screenshot 2024-04-03 145058](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/bfc8fbde-e205-4f6e-815f-c971f3319d9e)
#### Menambahkan di tengah
![Screenshot 2024-04-03 145156](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/45a40697-caf7-408b-9d66-eb39201c7579)

#### Tampilan Hasil
![Screenshot 2024-04-03 145218](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/38a27d60-3765-410f-b9f2-ad3f9c616637)

![Screenshot 2024-04-03 145224](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/3ee3a9b0-466e-4707-bb18-d6b404388432)

#### Full code Screenshot:
![Screenshot 2024-04-03 145701](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/8e7c69d2-d122-4ed8-821a-e8a6e2dab072)

#### 3. Lakukan perintah berikut:

a) Tambahkan data berikut diantara Farrel dan Denis: Wati 2330004
b) Hapus data Denis
c) Tambahkan data berikut di awal: Owi 2330000
d) Tambahkan data berikut di akhir: David 23300100
e) Ubah data Udin menjadi data berikut: Idin 23300045
f) Ubah data terkahir menjadi berikut: Lucy 23300101
g) Hapus data awal
h) Ubah data awal menjadi berikut: Bagas 2330002
i) Hapus data akhir
j) Tampilkan seluruh data


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



