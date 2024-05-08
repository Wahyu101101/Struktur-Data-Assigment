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

![Screenshot 2024-05-08 133627](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/d725d770-8e2b-4d33-9a27-acb2f59fe9e8)

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



