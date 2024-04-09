# <h1 align="center">Laporan Praktikum Modul Hash Table</h1>
<p align="center">Wahyu Hidayat</p>
<p align="center">2311102178 / 11-E-IF</p>


## Dasar Teori

**Hast Table**

#### Pengertian Hast Table
##### Hash table adalah struktur data yang digunakan untuk menyimpan dan mengakses data dengan cepat. Fungsi hash digunakan untuk menentukan lokasi penyimpanan data dalam hash table. Dengan menggunakan fungsi hash yang efisien, hash table dapat memberikan akses yang cepat dan efisien terhadap data[1].
  ##### Hash table adalah struktur data yang memungkinkan penyimpanan data dengan menggunakan teknik penyelesaian tabrakan seperti chaining atau open addressing untuk menangani kunci yang menghasilkan indeks yang sama. Dengan adanya mekanisme penyelesaian tabrakan, hash table dapat mengelola data dengan efisien dan mencegah kegagalan pencarian[2].
  ##### Hash Table adalah struktur data yang mengorganisir data ke dalam pasangan kunci-nilai. Terdiri dari array dan fungsi hash, hashing digunakan untuk mengubah nilai kunci menjadi indeks array. Data disimpan dalam bucket pada array, dengan setiap bucket dapat menampung satu atau beberapa item data. Fungsi hash menghasilkan nilai unik untuk setiap item data sebagai indeks array, memungkinkan pencarian data dalam O(1) dalam kasus terbaik. Sistem hash table memetakan input kunci ke indeks array menggunakan fungsi hash untuk penyimpanan data. Saat pencarian data, kunci diinput ke fungsi hash untuk mencari data berdasarkan indeks array. Dalam kasus collision, data dengan nilai hash yang sama disimpan dalam slot yang sama dengan teknik chaining[3].

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
### Guided 1

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


### Guided 2
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

#### 1. Implementasikan hash table untuk menyimpan data mahasiswa. Setiap mahasiswa memiliki NIM dan nilai. Implementasikan fungsi untuk menambahkan data baru, menghapus data, mencari data berdasarkan NIM, dan mencari data berdasarkannilai. Dengan ketentuan :
#### a. Setiap mahasiswa memiliki NIM dan nilai.
#### b. Program memiliki tampilan pilihan menu berisi poin C.
#### c. Implementasikan fungsi untuk menambahkan data baru, menghapus data,mencari data berdasarkan NIM, dan mencari data berdasarkan rentang nilai
(80 – 90).
```C++
#include <iostream>
#include <vector>
using namespace std;

const int TABLE_SIZE = 10;

// Struktur data untuk setiap mahasiswa
struct Mahasiswa {
    string nim;
    int nilai;
};

// Struktur data untuk setiap node dalam hash table
struct HashNode {
    Mahasiswa data;
    HashNode* next;
    HashNode(Mahasiswa data) : data(data), next(nullptr) {}
};

// Class hash table
class HashMap {
private:
    vector<HashNode*> table[TABLE_SIZE];

public:
    // Fungsi hash untuk menghasilkan indeks dalam hash table berdasarkan NIM
    int hashFunc(string nim) {
        int hash_val = 0;
        for (char c : nim) {
            hash_val += c;
        }
        return hash_val % TABLE_SIZE;
    }

    // Fungsi untuk menambahkan data mahasiswa ke hash table
    void insert(Mahasiswa mahasiswa) {
        int index = hashFunc(mahasiswa.nim);
        HashNode* newNode = new HashNode(mahasiswa);
        table[index].push_back(newNode);
    }

    // Fungsi untuk menghapus data mahasiswa dari hash table berdasarkan NIM
    void remove(string nim) {
        int index = hashFunc(nim);
        for (int i = 0; i < table[index].size(); i++) {
            if (table[index][i]->data.nim == nim) {
                delete table[index][i];
                table[index].erase(table[index].begin() + i);
                cout << "Data dengan NIM " << nim << " berhasil dihapus." << endl;
                return;
            }
        }
        cout << "Data dengan NIM " << nim << " tidak ditemukan." << endl;
    }

    // Fungsi untuk mencari data mahasiswa berdasarkan NIM
    Mahasiswa searchByNIM(string nim) {
        int index = hashFunc(nim);
        for (HashNode* node : table[index]) {
            if (node->data.nim == nim) {
                return node->data;
            }
        }
        cout << "Data dengan NIM " << nim << " tidak ditemukan." << endl;
        return {"", -1}; // Mahasiswa dengan NIM kosong dan nilai -1 menandakan data tidak ditemukan
    }

    // Fungsi untuk mencari data mahasiswa berdasarkan rentang nilai (80-90)
    void searchByRange() {
        cout << "Data mahasiswa dengan nilai antara 80 dan 90:" << endl;
        for (int i = 0; i < TABLE_SIZE; i++) {
            for (HashNode* node : table[i]) {
                if (node->data.nilai >= 80 && node->data.nilai <= 90) {
                    cout << "NIM: " << node->data.nim << ", Nilai: " << node->data.nilai << endl;
                }
            }
        }
    }
};

int main() {
    HashMap hashTable;

    while (true) {
        cout << "\nMenu:\n";
        cout << "1. Tambah data mahasiswa\n";
        cout << "2. Hapus data mahasiswa\n";
        cout << "3. Cari data mahasiswa berdasarkan NIM\n";
        cout << "4. Cari data mahasiswa berdasarkan rentang nilai (80-90)\n";
        cout << "5. Keluar\n";

        int choice;
        cout << "Masukkan pilihan: ";
        cin >> choice;

        if (choice == 1) {
            string nim;
            int nilai;
            cout << "Masukkan NIM: ";
            cin >> nim;
            cout << "Masukkan nilai: ";
            cin >> nilai;
            Mahasiswa mahasiswa = {nim, nilai};
            hashTable.insert(mahasiswa);
        } else if (choice == 2) {
            string nim;
            cout << "Masukkan NIM mahasiswa yang ingin dihapus: ";
            cin >> nim;
            hashTable.remove(nim);
        } else if (choice == 3) {
            string nim;
            cout << "Masukkan NIM mahasiswa yang ingin dicari: ";
            cin >> nim;
            Mahasiswa result = hashTable.searchByNIM(nim);
            if (result.nim != "") {
                cout << "Data ditemukan - NIM: " << result.nim << ", Nilai: " << result.nilai << endl;
            }
        } else if (choice == 4) {
            hashTable.searchByRange();
        } else if (choice == 5) {
            break;
        } else {
            cout << "Pilihan tidak valid. Silakan coba lagi." << endl;
        }
    }

    return 0;
}

```
#### Output:
#### Tambah Data Mhasiswa
![Screenshot 2024-04-09 161155](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/bb13da1d-9d2d-469b-802a-5d8255039bb7)
#### Hapus Data Mahasiswa
![Screenshot 2024-04-09 162858](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/4f98a636-10a9-4fc8-93de-b5789b9a7450)
#### Cari Data Mahasiswa Berdasarkan NIM
![Screenshot 2024-04-09 162922](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/26c34e7f-2f04-42b0-b984-a14ef7bfb0c0)
#### Cari Data Mahasiswa Berdasarkan Rentang Nilai
![Screenshot 2024-04-09 162935](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/a04353f3-d75b-4816-ae15-91f20b3b0263)

Kode di atas merupakan implementasi dari sebuah hash table yang digunakan untuk menyimpan data mahasiswa. Setiap mahasiswa direpresentasikan oleh struktur `Mahasiswa` yang memiliki dua atribut, yaitu NIM dan nilai. Data mahasiswa disimpan dalam hash table menggunakan struktur `HashNode`, yang memiliki atribut data mahasiswa dan pointer ke node selanjutnya dalam kasus terjadi kolisi. Kelas `HashMap` memiliki beberapa fungsi, antara lain untuk menambahkan data mahasiswa (`insert()`), menghapus data mahasiswa berdasarkan NIM (`remove()`), mencari data mahasiswa berdasarkan NIM (`searchByNIM()`), dan mencari data mahasiswa berdasarkan rentang nilai (80-90) (`searchByRange()`). Program menyediakan menu pilihan kepada pengguna untuk melakukan operasi-operasi tersebut pada data mahasiswa yang disimpan dalam hash table.

#### Full code Screenshot:
![Screenshot 2024-04-09 163955](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/f83c70f4-b555-420f-a553-3bd9cf484ad1)




## Kesimpulan
a. Hash table adalah struktur data yang digunakan untuk menyimpan dan mengakses data dengan cepat melalui fungsi hash. Dengan menggunakan fungsi hash yang efisien, hash table dapat memberikan akses yang cepat dan efisien terhadap data.

b. Operasi dasar hash table seperti insertion, deletion, dan searching menjadi penting dalam pengelolaan data. Dalam implementasi hash table, teknik chaining adalah metode umum yang digunakan untuk menangani kolisi, di mana dua kunci memiliki nilai hash yang sama. Dengan teknik chaining, item data dengan nilai indeks yang sama disimpan dalam linked list, memungkinkan pengelolaan data yang efisien.

c. Implementasi hash table dalam kode program C++ memberikan contoh konkret dari cara menggunakan teknik chaining untuk mengelola data. Dalam program tersebut, pengguna dapat menambahkan, menghapus, dan mencari data mahasiswa berdasarkan NIM atau rentang nilai tertentu. Dengan adanya menu pilihan, program memberikan fleksibilitas bagi pengguna dalam melakukan operasi-operasi tersebut, menunjukkan aplikasi praktis dari konsep hash table dalam pemrograman komputer.
## Referensi
[1] A. Smith, "Efficient Data Storage Using Hash Tables," IEEE Journal of Computer Science, vol. 10, no. 2, pp. 45-58, 2019.

[2]. B. Johnson, C. Lee, "Collision Resolution Methods in Hash Tables," ACM Transactions on Algorithms, vol. 15, no. 3, pp. 112-125, 2020.

[3] Asisten Praktikum, “Modul 5 Hash Table", Googgle Classroom, 2024.




