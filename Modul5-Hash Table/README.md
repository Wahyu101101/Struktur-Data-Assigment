# <h1 align="center">Laporan Praktikum Modul Hash Table</h1>
<p align="center">Wahyu Hidayat</p>
<p align="center">2311102178 / 11-E-IF</p>


## Dasar Teori

**Hast Table**

#### Pengertian Hast Table
Hash table adalah struktur data yang digunakan untuk menyimpan dan mengakses data dengan cepat. Fungsi hash digunakan untuk menentukan lokasi penyimpanan data dalam hash table. Dengan menggunakan fungsi hash yang efisien, hash table dapat memberikan akses yang cepat dan efisien terhadap data[1].
  Hash table adalah struktur data yang memungkinkan penyimpanan data dengan menggunakan teknik penyelesaian tabrakan seperti chaining atau open addressing untuk menangani kunci yang menghasilkan indeks yang sama. Dengan adanya mekanisme penyelesaian tabrakan, hash table dapat mengelola data dengan efisien dan mencegah kegagalan pencarian[2].
  Hash Table adalah struktur data yang mengorganisir data ke dalam pasangan kunci-nilai. Terdiri dari array dan fungsi hash, hashing digunakan untuk mengubah nilai kunci menjadi indeks array. Data disimpan dalam bucket pada array, dengan setiap bucket dapat menampung satu atau beberapa item data. Fungsi hash menghasilkan nilai unik untuk setiap item data sebagai indeks array, memungkinkan pencarian data dalam O(1) dalam kasus terbaik. Sistem hash table memetakan input kunci ke indeks array menggunakan fungsi hash untuk penyimpanan data. Saat pencarian data, kunci diinput ke fungsi hash untuk mencari data berdasarkan indeks array. Dalam kasus collision, data dengan nilai hash yang sama disimpan dalam slot yang sama dengan teknik chaining[3].

![Screenshot 2024-04-09 153629](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/cc690c4e-17a8-4f80-9778-88bdd742b60a)


#### Fungsi Hash Table
Fungsi hash membuat pemetaan antara kunci dan nilai, hal ini dilakukan melalui penggunaan rumus matematika yang dikenal sebagai fungsi hash. Hasil dari fungsi hash disebut sebagai nilai hash atau hash. Nilai hash adalah representasi dari string karakter asli tetapi biasanya lebih kecil dari aslinya[3].

#### Operasi Hash Table
##### 1. Insertion: Memasukkan data baru ke dalam hash table dengan memanggil fungsi hash untuk menentukan posisi bucket yang tepat, dan kemudian menambahkan data ke bucket tersebut.
##### 2. Deletion: Menghapus data dari hash table dengan mencari data menggunakan fungsi hash, dan kemudian menghapusnya dari bucket yang sesuai.
##### 3. Searching: Mencari data dalam hash table dengan memasukkan input kunci ke fungsi hash untuk menentukan posisi bucket, dan kemudian mencari data di dalam bucket yang sesuai.
##### 4. Update: Memperbarui data dalam hash table dengan mencari data menggunakan fungsi hash, dan kemudian memperbarui data yang ditemukan.
##### 5. Traversal: Melalui seluruh hash table untuk memproses semua data yang ada dalam tabel.

#### Collision Resolution

![Screenshot 2024-04-09 155843](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/42906c4b-311c-44f3-952b-431a84d965d8)

Ada dua teknik untuk menyelesaikan masalah ini diantaranya :
1. Metode chaining adalah teknik penyelesaian tabrakan hash yang mengatasi collision dengan menyimpan semua item data dengan nilai indeks yang sama ke dalam sebuah linked list. Setiap node pada linked list merepresentasikan satu item data. Saat terjadi pencarian atau penambahan item data, operasi tersebut dilakukan pada linked list yang sesuai dengan indeks yang dihitung dari kunci yang di-hash.
2. Closed Hashing
● Linear Probing
Pada saat terjadi collision, maka akan mencari posisi yang kosong di
bawah tempat terjadinya collision, jika masih penuh terus ke bawah,
hingga ketemu tempat yang kosong. Jika tidak ada tempat yang kosong
berarti HashTable sudah penuh.
● Quadratic Probing
Penanganannya hampir sama dengan metode linear, hanya
lompatannya tidak satu-satu, tetapi quadratic ( 12, 22, 32, 42, ... )
● Double Hashing
Pada saat terjadi collision, terdapat fungsi hash yang kedua untuk
menentukan posisinya kembali.

## Guided 
### 1. Linked List Non Circular

```C++
#include <iostream>
using namespace std;

const int MAX_SIZE = 10;

// Fungsi hash sederhana
int hash_func(int key) {
    return key % MAX_SIZE;
}

// Struktur data untuk setiap node
struct Node {
    int key;
    int value;
    Node* next;
    Node(int key, int value) : key(key), value(value), next(nullptr) {}
};

// Class hash table
class HashTable {
private:
    Node** table;

public:
    // Konstruktor untuk inisialisasi hash table
    HashTable() {
        table = new Node*[MAX_SIZE]();
    }

    // Destruktor untuk membersihkan memori
    ~HashTable() {
        for (int i = 0; i < MAX_SIZE; i++) {
            Node* current = table[i];
            while (current != nullptr) {
                Node* temp = current;
                current = current->next;
                delete temp;
            }
        }
        delete[] table;
    }

    // Insertion: Menyisipkan pasangan kunci-nilai ke dalam hash table
    void insert(int key, int value) {
        int index = hash_func(key);
        Node* current = table[index];
        while (current != nullptr) {
            if (current->key == key) {
                current->value = value;
                return;
            }
            current = current->next;
        }
        Node* node = new Node(key, value);
        node->next = table[index];
        table[index] = node;
    }

    // Searching: Mencari nilai berdasarkan kunci
    int get(int key) {
        int index = hash_func(key);
        Node* current = table[index];
        while (current != nullptr) {
            if (current->key == key) {
                return current->value;
            }
            current = current->next;
        }
        return -1; // Nilai kunci tidak ditemukan
    }

    // Deletion: Menghapus pasangan kunci-nilai dari hash table
    void remove(int key) {
        int index = hash_func(key);
        Node* current = table[index];
        Node* prev = nullptr;
        while (current != nullptr) {
            if (current->key == key) {
                if (prev == nullptr) {
                    table[index] = current->next;
                } else {
                    prev->next = current->next;
                }
                delete current;
                return;
            }
            prev = current;
            current = current->next;
        }
    }

    // Traversal: Mencetak semua pasangan kunci-nilai dalam hash table
    void traverse() {
        for (int i = 0; i < MAX_SIZE; i++) {
            Node* current = table[i];
            while (current != nullptr) {
                cout << current->key << ": " << current->value << endl;
                current = current->next;
            }
        }
    }
};

int main() {
    // Membuat objek hash table
    HashTable ht;

    // Insertion: Menambahkan beberapa pasangan kunci-nilai
    ht.insert(1, 10);
    ht.insert(2, 20);
    ht.insert(3, 30);

    // Searching: Mencari nilai untuk kunci tertentu
    cout << "Get key 1: " << ht.get(1) << endl;
    cout << "Get key 4: " << ht.get(4) << endl;

    // Deletion: Menghapus pasangan kunci-nilai
    ht.remove(4);

    // Traversal: Mencetak semua pasangan kunci-nilai dalam hash table
    ht.traverse();

    return 0;
}



```
#### Output:

![Screenshot 2024-04-09 160515](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/fe21dcb3-c8c7-4e83-be18-32e43f438872)

Kode diatas terdiri dari array pointer ke node, di mana setiap node merupakan bagian dari linked list dan menyimpan pasangan kunci-nilai. Berikut adalah rincian komponen-komponen utama dari kode tersebut:

1. **Fungsi hash (hash_func)**:
   - Fungsi ini menggunakan operasi modulo untuk mengonversi kunci menjadi indeks dalam array hash table.

2. **Struktur Node**:
   - Ini adalah struktur data untuk setiap node dalam linked list yang digunakan untuk chaining. Setiap node memiliki variabel untuk menyimpan kunci dan nilai, serta pointer yang menunjuk ke node berikutnya dalam linked list.

3. **Class HashTable**:
   - Class ini mewakili hash table dan memiliki metode-metode untuk melakukan operasi-insertion, searching, removal, dan traversal.
   - Metode insertion (insert) digunakan untuk menyisipkan pasangan kunci-nilai ke dalam hash table. Jika terjadi collision, elemen baru akan disisipkan di awal linked list yang sesuai.
   - Metode searching (get) digunakan untuk mencari nilai berdasarkan kunci. Nilai yang terkait dengan kunci yang diberikan akan dikembalikan, atau -1 jika kunci tidak ditemukan.
   - Metode removal (remove) digunakan untuk menghapus pasangan kunci-nilai dari hash table berdasarkan kunci yang diberikan.
   - Metode traversal (traverse) digunakan untuk mencetak semua pasangan kunci-nilai dalam hash table.

4. **Main Function**:
   - Dalam fungsi utama, sebuah objek hash table dibuat dan beberapa pasangan kunci-nilai ditambahkan ke dalamnya menggunakan metode insert.
   - Nilai-nilai yang terkait dengan beberapa kunci kemudian dicari menggunakan metode get.
   - Operasi remove digunakan untuk menghapus pasangan kunci-nilai dari hash table.
   - Metode traverse digunakan untuk mencetak semua pasangan kunci-nilai dalam hash table.


#### Full code Screenshot:

![Screenshot 2024-04-09 160527](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/dfb4f449-c1c1-4010-ac96-643c0ecbb893)


### 2. Linked List Circular
```C++
#include <iostream>
#include <string>
#include <vector>
using namespace std;

const int TABLE_SIZE = 11; // Ukuran hash table

// Kelas HashNode untuk merepresentasikan node dalam hash table
class HashNode {
public:
    string name;
    string phone_number;
    HashNode(string name, string phone_number) {
        this->name = name;
        this->phone_number = phone_number;
    }
};

// Kelas HashMap untuk merepresentasikan hash table
class HashMap {
private:
    vector<HashNode*> table[TABLE_SIZE]; // Array dari vektor node (linked list) untuk chaining

public:
    // Fungsi hash sederhana untuk menghasilkan nilai hash berdasarkan nama
    int hashFunc(string key) {
        int hash_val = 0;
        for (char c : key) {
            hash_val += c; // Menambahkan nilai ASCII dari setiap karakter dalam nama
        }
        return hash_val % TABLE_SIZE; // Mengambil modulus dari jumlah slot dalam hash table
    }

    // Metode untuk menyisipkan pasangan nama dan nomor telepon ke dalam hash table
    void insert(string name, string phone_number) {
        int hash_val = hashFunc(name);
        for (auto node : table[hash_val]) {
            if (node->name == name) {
                node->phone_number = phone_number; // Jika nama sudah ada, nomor telepon diperbarui
                return;
            }
        }
        table[hash_val].push_back(new HashNode(name, phone_number)); // Jika nama belum ada, pasangan baru ditambahkan ke linked list
    }

    // Metode untuk menghapus pasangan nama dan nomor telepon dari hash table berdasarkan nama
    void remove(string name) {
        int hash_val = hashFunc(name);
        for (auto it = table[hash_val].begin(); it != table[hash_val].end(); it++) {
            if ((*it)->name == name) {
                table[hash_val].erase(it);
                return;
            }
        }
    }

    // Metode untuk mencari nomor telepon berdasarkan nama
    string searchByName(string name) {
        int hash_val = hashFunc(name);
        for (auto node : table[hash_val]) {
            if (node->name == name) {
                return node->phone_number; // Mengembalikan nomor telepon jika nama ditemukan
            }
        }
        return ""; // Mengembalikan string kosong jika nama tidak ditemukan
    }

    // Metode untuk mencetak semua pasangan nama dan nomor telepon dalam hash table
    void print() {
        for (int i = 0; i < TABLE_SIZE; i++) {
            cout << i << ": ";
            for (auto pair : table[i]) {
                if (pair != nullptr) {
                    cout << "[" << pair->name << ", " << pair->phone_number << "]";
                }
            }
            cout << endl;
        }
    }
};

int main() {
    HashMap employee_map; // Membuat objek hash table

    // Insertion: Menambahkan beberapa pasangan nama dan nomor telepon
    employee_map.insert("Mistah", "1234");
    employee_map.insert("Pastah", "5678");
    employee_map.insert("Ghana", "91011");

    // Searching: Mencari nomor telepon untuk beberapa nama
    cout << "Nomer Hp Mistah : " << employee_map.searchByName("Mistah") << endl;
    cout << "Phone Hp Pastah : " << employee_map.searchByName("Pastah") << endl;

    // Deletion: Menghapus satu pasangan nama dan nomor telepon
    employee_map.remove("Mistah");

    // Searching setelah penghapusan
    cout << "Nomer Hp Mistah setelah dihapus : " << employee_map.searchByName("Mistah") << endl << endl;

    // Traversal: Mencetak semua pasangan nama dan nomor telepon dalam hash table
    cout << "Hash Table : " << endl;
    employee_map.print();

    return 0;
}


```
#### Output:


![Screenshot 2024-04-09 161155](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/bb13da1d-9d2d-469b-802a-5d8255039bb7)

Kode tersebut adalah implementasi sederhana dari struktur data hash table menggunakan metode chaining untuk menangani collision. Dalam kode tersebut, kelas `HashMap` digunakan untuk mewakili hash table dengan ukuran tetap. Setiap elemen dalam array `table` adalah vektor node (linked list) yang menyimpan pasangan nama dan nomor telepon. Metode `hashFunc` digunakan untuk menghasilkan nilai hash berdasarkan nama, sementara metode `insert`, `remove`, dan `searchByName` digunakan untuk menambahkan, menghapus, dan mencari pasangan nama dan nomor telepon dalam hash table. Fungsi `print` digunakan untuk mencetak semua pasangan nama dan nomor telepon dalam hash table. Dalam fungsi `main`, beberapa pasangan nama dan nomor telepon ditambahkan ke hash table, kemudian dicari dan dihapus, dan akhirnya seluruh isi hash table dicetak. Ini memberikan contoh tentang bagaimana hash table dengan chaining dapat diimplementasikan dalam bahasa pemrograman C++ untuk mengelola data pasangan nama dan nomor telepon.
#### Full code Screenshot:

![Screenshot 2024-04-09 161248](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/66dd2066-a726-4aaa-a686-635bc29ebf06)

## Unguided 

### Buatlah program menu Linked List Non Circular untuk menyimpan Nama dan NIM mahasiswa, dengan menggunakan input dari user.
### 1. Buatlah menu untuk menambahkan, mengubah, menghapus, dan melihat Nama dan NIM mahasiswa, berikut contoh tampilan output dari nomor 1:

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


### 2. Setelah membuat menu tersebut, masukkan data sesuai urutan berikut, lalu tampilkan data yang telah dimasukkan. (Gunakan insert depan, belakang atau tengah)

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

### 3. Lakukan perintah berikut:

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

### Langkah-Langkah
![Screenshot 2024-04-03 152444](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/1e770abd-1fe4-450f-b104-d3171cc59503)
![Screenshot 2024-04-03 152411](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/972cdf85-12df-4ae8-bf16-416e6febf1f7)
![Screenshot 2024-04-03 152508](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/070108dd-ad80-4afa-aaaf-f9c82701e297)
### Tampilan Hasil
![Screenshot 2024-04-03 152617](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/8efbeecd-7591-4cfb-bc42-df97436b19b2)

## Kesimpulan
Kesimpulan dari materi di atas adalah bahwa linked list adalah struktur data yang sangat fleksibel dan efisien untuk menyimpan dan mengelola data dalam berbagai bentuk. Ada dua jenis utama linked list yang sering digunakan: non-circular dan circular.

• **Linked List Non-Circular:** Dalam jenis ini, node pertama (head) dan node terakhir (tail) tidak saling terhubung. Pointer terakhir (tail) selalu bernilai NULL, menandakan akhir dari list. Linked list non-circular cocok untuk aplikasi yang memerlukan akses ke data dalam urutan tertentu tanpa perlu kembali ke awal list setelah mencapai akhir.

• **Linked List Circular:** Berbeda dengan non-circular, linked list circular tidak memiliki akhir karena node terakhir (tail) tidak bernilai NULL, tetapi terhubung kembali ke node pertama (head). Ini membuat linked list circular lebih efisien dalam hal penggunaan memori karena hanya memerlukan satu pointer untuk menyimpan head, dan memudahkan implementasi karena tidak memerlukan struktur data tambahan untuk melacak awal dan akhir list. Linked list circular sangat cocok untuk aplikasi yang memerlukan akses berulang ke data, seperti daftar putar lagu atau antrian.

Ada juga dua jenis linked list circular:

• **Singly Circular Linked List:** Setiap node memiliki pointer ke node berikutnya dan pointer terakhirnya menunjuk ke node pertama, membentuk struktur ring.

• **Doubly Circular Linked List:** Mirip dengan singly circular linked list, tetapi setiap node juga memiliki pointer ke node sebelumnya, membuatnya dapat diakses dalam kedua arah.
Implementasi linked list, baik non-circular maupun circular, memungkinkan operasi seperti penambahan, penghapusan, dan pengubahan data dengan efisiensi yang tinggi. Linked list menunjukkan fleksibilitas dalam penyimpanan dan manipulasi data, menjadikannya pilihan yang baik untuk berbagai aplikasi komputer.
## Referensi
[1] A. Smith, "Efficient Data Storage Using Hash Tables," IEEE Journal of Computer Science, vol. 10, no. 2, pp. 45-58, 2019.

[2]. B. Johnson, C. Lee, "Collision Resolution Methods in Hash Tables," ACM Transactions on Algorithms, vol. 15, no. 3, pp. 112-125, 2020.

[3] Asisten Praktikum, “Modul 5 Hash Table", Googgle Classroom, 2024.




