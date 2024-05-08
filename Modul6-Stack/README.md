# <h1 align="center">Laporan Praktikum Modul Stack</h1>
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
#### c. Implementasikan fungsi untuk menambahkan data baru, menghapus data,mencari data berdasarkan NIM, dan mencari data berdasarkan rentang nilai (80 – 90).
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
![Screenshot 2024-04-09 162833](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/b4a2e634-a6be-46cb-92a7-aab8e7924ec0)
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
A. Hash table adalah struktur data yang digunakan untuk menyimpan dan mengakses data dengan cepat melalui fungsi hash. Dengan menggunakan fungsi hash yang efisien, hash table dapat memberikan akses yang cepat dan efisien terhadap data.

B. Operasi dasar hash table seperti insertion, deletion, dan searching menjadi penting dalam pengelolaan data. Dalam implementasi hash table, teknik chaining adalah metode umum yang digunakan untuk menangani kolisi, di mana dua kunci memiliki nilai hash yang sama. Dengan teknik chaining, item data dengan nilai indeks yang sama disimpan dalam linked list, memungkinkan pengelolaan data yang efisien.

C. Implementasi hash table dalam kode program C++ memberikan contoh konkret dari cara menggunakan teknik chaining untuk mengelola data. Dalam program tersebut, pengguna dapat menambahkan, menghapus, dan mencari data mahasiswa berdasarkan NIM atau rentang nilai tertentu. Dengan adanya menu pilihan, program memberikan fleksibilitas bagi pengguna dalam melakukan operasi-operasi tersebut, menunjukkan aplikasi praktis dari konsep hash table dalam pemrograman komputer.
## Referensi
[1] Asisten Praktikum, “Modul 6 Stack", Googgle Classroom, 2024.

[2] "A Survey of Stack-Based Machine Learning" oleh D. Wang et al. (2019) 

[3] "Stack-Based Memory Allocation for Deep Learning" oleh Y. Wu et al. (2019) 



