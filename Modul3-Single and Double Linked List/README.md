# <h1 align="center">Laporan Praktikum Modul Single and Double Linked List</h1>
<p align="center">Wahyu Hidayat</p>
<p align="center">2311102178 / 11-E-IF</p>


## Dasar Teori

Linked List

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


class Node {
    public:int data;
    Node* prev;
    Node* next;
};
class DoublyLinkedList {
        public:
        Node* head;
        Node* tail;
        DoublyLinkedList() {
            head = nullptr;
            tail = nullptr;
    }
    void push(int data) {
        Node* newNode = new Node;
        newNode->data = data;
        newNode->prev = nullptr;
        newNode->next = head;
        if (head != nullptr) {
            head->prev = newNode;
        } 
        else {
            tail = newNode;
        }
        head = newNode;
    }
    void pop() {
        if (head == nullptr) {
            return;
        }
        Node* temp = head;
        head = head->next;
        if (head != nullptr) {
            head->prev = nullptr;
        } 
        else {
            tail = nullptr;
        }
        delete temp;
    }
    bool update(int oldData, int newData) {
        Node* current = head;while (current != nullptr) {
            if (current->data == oldData) {
                current->data = newData;
                return true;
            }
            current = current->next;
        }
        return false;
    }
    void deleteAll() {
        Node* current = head;
        while (current != nullptr) {
            Node* temp = current;
            current = current->next;
            delete temp;
        }
        head = nullptr;
        tail = nullptr;
    }
    void display() {
        Node* current = head;
        while (current != nullptr) {
            cout << current->data << " ";
            current = current->next;
        }
        cout << endl;
    }
};


int main() {
    DoublyLinkedList list;
    while (true) {
        cout << "1. Add data" << endl;
        cout << "2. Delete data" << endl;
        cout << "3. Update data" << endl;
        cout << "4. Clear data" << endl;
        cout << "5. Display data" << endl;
        cout << "6. Exit" << endl;int choice;
        cout << "Enter your choice: ";
        cin >> choice;
        switch (choice) {
            case 1: {
                int data;
                cout << "Enter data to add: ";
                cin >> data;
                list.push(data);
                break;
            }
            case 2: {
                list.pop();
                break;
            }
            case 3: {
                int oldData, newData;
                cout << "Enter old data: ";
                cin >> oldData;
                cout << "Enter new data: ";
                cin >> newData;
                bool updated = list.update(oldData, newData);
                if (!updated) {
                    cout << "Data not found" << endl;
                }
                break;
            }
            case 4: {
                list.deleteAll();
                break;
            }
            case 5: {
                list.display();
                break;
            }
            case 6: {
                return 0;
            }
            default: {
                cout << "Invalid choice" << endl;
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

![Screenshot 2024-03-26 104258](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/14404526-ad13-4719-8af5-ec5e3b306290)


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

struct Node {
    string nama;
    int usia;
    Node* next;
};

Node* head = nullptr;
Node* tail = nullptr;

void insertDepan(string nama, int usia) {
    Node* baru = new Node;
    baru->nama = nama;
    baru->usia = usia;
    baru->next = head;
    head = baru;
    if (tail == nullptr) tail = baru;
}

void insertBelakang(string nama, int usia) {
    Node* baru = new Node;
    baru->nama = nama;
    baru->usia = usia;
    baru->next = nullptr;
    if (tail != nullptr) tail->next = baru;
    else head = baru;
    tail = baru;
}

void insertTengah(string nama, int usia, string namaSebelum) {
    Node* baru = new Node;
    baru->nama = nama;
    baru->usia = usia;
    Node* bantu = head;
    while (bantu != nullptr && bantu->nama != namaSebelum) {
        bantu = bantu->next;
    }
    if (bantu == nullptr) {
        cout << "Nama sebelum tidak ditemukan." << endl;
        return;
    }
    baru->next = bantu->next;
    bantu->next = baru;
    if (baru->next == nullptr) tail = baru;
}

void hapus(string nama) {
    if (head == nullptr) return;
    if (head->nama == nama) {
        Node* hapus = head;
        head = head->next;
        delete hapus;
        return;
    }
    Node* bantu = head;
    while (bantu->next != nullptr && bantu->next->nama != nama) {
        bantu = bantu->next;
    }
    if (bantu->next != nullptr) {
        Node* hapus = bantu->next;
        bantu->next = hapus->next;
        if (hapus == tail) tail = bantu;
        delete hapus;
    }
}

void tampil() {
    Node* bantu = head;
    while (bantu != nullptr) {
        cout << bantu->nama << " " << bantu->usia << endl;
        bantu = bantu->next;
    }
}

int main() {
    insertDepan("John", 19);
    insertBelakang("Jane", 20);
    insertBelakang("Michael", 18);
    insertBelakang("Yusuke", 19);
    insertBelakang("Akechi", 20);
    insertBelakang("Hoshino", 18);
    insertBelakang("Karin", 18);

    hapus("Akechi");
    insertTengah("Futaba", 18, "John");
    insertDepan("Igor", 20);
    hapus("Michael");
    insertDepan("Reyn", 18);

    tampil();

    return 0;
}

```
#### Output:

![Screenshot 2024-03-26 105907](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/5f9deb6e-e31b-4083-920c-5289acca5767)


Kode di atas mengimplementasikan struktur data Single Linked List Non-Circular untuk menyimpan informasi tentang mahasiswa, yaitu nama dan usia, dengan memungkinkan operasi seperti menambahkan data ke depan, belakang, atau tengah list, menghapus data berdasarkan nama, dan menampilkan semua data dalam list. Program dimulai dengan menambahkan data mahasiswa ke list menggunakan fungsi `insertDepan`, `insertBelakang`, dan `insertTengah`, sesuai dengan urutan yang diminta. Fungsi `insertDepan` menambahkan node baru di awal list, `insertBelakang` menambahkan node baru di akhir list, dan `insertTengah` menambahkan node baru di posisi tertentu dalam list berdasarkan nama mahasiswa yang ada sebelumnya. Setelah menambahkan data mahasiswa, program melakukan operasi hapus untuk menghapus data mahasiswa bernama "Akechi" dari list menggunakan fungsi `hapus`, yang mencari node dengan nama yang sesuai dan menghapusnya dari list. Selanjutnya, program menambahkan data mahasiswa "Futaba" di antara "John" dan "Jane" menggunakan fungsi `insertTengah`, menambahkan "Igor" di awal list menggunakan `insertDepan`, menghapus "Michael" dari list menggunakan `hapus`, dan menambahkan "Reyn" di awal list menggunakan `insertDepan` lagi. Akhirnya, program menampilkan semua data dalam list menggunakan fungsi `tampil`, yang mencetak nama dan usia setiap mahasiswa dalam list. Program ini menunjukkan bagaimana mengelola dan memanipulasi data dalam Single Linked List Non-Circular dengan berbagai operasi yang diminta, termasuk penambahan, penghapusan, dan penampilan data, serta bagaimana menambahkan data ke posisi tertentu dalam list.

#### Full code Screenshot:

![Screenshot 2024-03-26 105830](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/29061433-6930-4aec-ac97-07155c750445)

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
    string namaProduk;
    double harga;
    Node* prev;
    Node* next;
};

class DoublyLinkedList {
public:
    Node* head;
    Node* tail;
    DoublyLinkedList() {
        head = nullptr;
        tail = nullptr;
    }
    void push(string namaProduk, double harga) {
        Node* newNode = new Node;
        newNode->namaProduk = namaProduk;
        newNode->harga = harga;
        newNode->prev = nullptr;
        newNode->next = head;
        if (head != nullptr) {
            head->prev = newNode;
        } else {
            tail = newNode;
        }
        head = newNode;
    }
    void pop() {
        if (head == nullptr) {
            return;
        }
        Node* temp = head;
        head = head->next;
        if (head != nullptr) {
            head->prev = nullptr;
        } else {
            tail = nullptr;
        }
        delete temp;
    }
    bool update(string oldNamaProduk, string newNamaProduk, double newHarga) {
        Node* current = head;
        while (current != nullptr) {
            if (current->namaProduk == oldNamaProduk) {
                current->namaProduk = newNamaProduk;
                current->harga = newHarga;
                return true;
            }
            current = current->next;
        }
        return false;
    }
    void deleteAll() {
        Node* current = head;
        while (current != nullptr) {
            Node* temp = current;
            current = current->next;
            delete temp;
        }
        head = nullptr;
        tail = nullptr;
    }
    void display() {
        Node* current = head;
        while (current != nullptr) {
            cout << current->namaProduk << " " << current->harga << endl;
            current = current->next;
        }
    }
    void insertAfter(string prevNamaProduk, string namaProduk, double harga) {
        Node* temp = head;
        while (temp != nullptr && temp->namaProduk != prevNamaProduk) {
            temp = temp->next;
        }
        if (temp == nullptr) {
            cout << "Produk sebelumnya tidak ditemukan." << endl;
            return;
        }
        Node* newNode = new Node;
        newNode->namaProduk = namaProduk;
        newNode->harga = harga;
        newNode->next = temp->next;
        newNode->prev = temp;
        if (temp->next != nullptr) {
            temp->next->prev = newNode;
        }
        temp->next = newNode;
    }
    void insertAtBeginning(string namaProduk, double harga) {
        Node* newNode = new Node;
        newNode->namaProduk = namaProduk;
        newNode->harga = harga;
        newNode->next = head;
        newNode->prev = nullptr;
        if (head != nullptr) {
            head->prev = newNode;
        } else {
            tail = newNode;
        }
        head = newNode;
    }
    void deleteNode(string namaProduk) {
        if (head == nullptr)
            return;
        Node* temp = head;
        while (temp != nullptr && temp->namaProduk != namaProduk) {
            temp = temp->next;
        }
        if (temp == nullptr)
            return;
        if (temp->prev != nullptr)
            temp->prev->next = temp->next;
        if (temp->next != nullptr)
            temp->next->prev = temp->prev;
        if (temp == head)
            head = temp->next;
        if (temp == tail)
            tail = temp->prev;
        delete temp;
    }
};

int main() {
    DoublyLinkedList list;
    while (true) {
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
        cin >> choice;
        switch (choice) {
            case 1: {
                string namaProduk;
                double harga;
                cout << "Masukkan nama produk: ";
                cin >> namaProduk;
                cout << "Masukkan harga: ";
                cin >> harga;
                list.push(namaProduk, harga);
                break;
            }
            case 2: {
                string namaProduk;
                cout << "Masukkan nama produk yang ingin dihapus: ";
                cin >> namaProduk;
                list.deleteNode(namaProduk);
                break;
            }
            case 3: {
                string oldNamaProduk, newNamaProduk;
                double newHarga;
                cout << "Masukkan nama produk yang ingin diupdate: ";
                cin >> oldNamaProduk;
                cout << "Masukkan nama produk baru: ";
                cin >> newNamaProduk;
                cout << "Masukkan harga baru: ";
                cin >> newHarga;
                bool updated = list.update(oldNamaProduk, newNamaProduk, newHarga);
                if (!updated) {
                    cout << "Data tidak ditemukan" << endl;
                }
                break;
            }
            case 4: {
                string prevNamaProduk, namaProduk;
                double harga;
                cout << "Masukkan nama produk sebelumnya: ";
                cin >> prevNamaProduk;
                cout << "Masukkan nama produk baru: ";
                cin >> namaProduk;
                cout << "Masukkan harga: ";
                cin >> harga;
                list.insertAfter(prevNamaProduk, namaProduk, harga);
                break;
            }
            case 5: {
                // Kode untuk menghapus data di urutan tertentu
                break;
            }
            case 6: {
                list.deleteAll();
                break;
            }
            case 7: {
                cout << "Data Produk:" << endl;
                list.display();
                break;
            }
            case 8: {
                return 0;
            }
            default: {
                cout << "Pilihan tidak valid" << endl;
                break;
            }
        }
    }
    return 0;
}

```
#### Output:

![Screenshot 2024-03-26 113809](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/3425db6f-2c92-431f-8fd4-534e7a300e8c)

Kode di atas mengimplementasikan struktur data Doubly Linked List untuk menyimpan informasi tentang produk skincare, termasuk nama produk dan harga, dengan memungkinkan operasi seperti menambahkan data ke awal list, menghapus data berdasarkan nama produk, memperbarui nama dan harga produk, menambahkan data di tengah list berdasarkan nama produk yang ada sebelumnya, dan menampilkan semua data dalam list. Program ini menyediakan menu interaktif di `main()` yang memungkinkan pengguna untuk memilih operasi yang ingin dilakukan, seperti menambahkan data baru, menghapus data, memperbarui data, menambahkan data di tengah list, menghapus semua data, dan menampilkan data. Fungsi `push` digunakan untuk menambahkan produk baru ke awal list, `pop` untuk menghapus produk dari awal list, `update` untuk memperbarui nama dan harga produk, `deleteAll` untuk menghapus semua produk dalam list, dan `display` untuk menampilkan semua produk dalam list. Fungsi `insertAfter` memungkinkan penambahan produk di tengah list berdasarkan nama produk yang ada sebelumnya, dan `deleteNode` digunakan untuk menghapus produk berdasarkan nama produk. Program ini menunjukkan bagaimana mengelola dan memanipulasi data dalam Doubly Linked List dengan berbagai operasi yang diminta, termasuk penambahan, penghapusan, dan penampilan data, serta bagaimana menambahkan data ke posisi tertentu dalam list. Selain itu, program ini juga menunjukkan bagaimana menangani kasus khusus seperti memperbarui nama produk dan harga, serta menampilkan data produk dalam format yang mudah dibaca.
#### Full code Screenshot:

![Screenshot 2024-03-26 113901](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/65560130-60b5-418e-8371-6bc666c13876)


## Kesimpulan
Kesimpulannya, kode-kode tersebut menunjukkan penggunaan array dalam berbagai konteks dan dimensi. Array digunakan sebagai wadah untuk menyimpan data dengan tipe yang sama, dan setiap elemen diakses menggunakan indeks. Array satu dimensi digunakan untuk menyimpan data dalam satu baris, sedangkan array dua dimensi digunakan untuk menyusun data dalam baris dan kolom. Selain itu, ada juga array multidimensi yang digunakan untuk menyimpan data dengan dimensi lebih dari dua. Program-program tersebut memanfaatkan array untuk berbagai tujuan, seperti menyimpan dan mengolah data, mencari nilai maksimum, minimum, dan rata-rata, serta memisahkan data genap dan ganjil. Dengan menggunakan array, program-program tersebut dapat melakukan operasi secara efisien dan terstruktur sesuai dengan kebutuhan pengguna.
## Referensi
[1]Dharma, Abdi. "Aplikasi Pembelajaran Linked List Berbasis Mobile Learning." Riau Journal Of Computer Science 4.1 (2018): 1-11.

[2]Siregar, Anugrah Ananda Nauli. "Pengertian Linked Object." (2019).


