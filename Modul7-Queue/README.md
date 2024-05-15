<p align="center">Wahyu Hidayat</p>
<p align="center">2311102178 / 11-E-IF</p>


## Dasar Teori

## **Stack**

#### Pengertian Stack
**Queue** adalah struktur data yang digunakan untuk menyimpan data dengan metode FIFO (First-In First-Out). Data yang pertama dimasukkan ke dalam queue akan menjadi data yang pertama pula untuk dikeluarkan dari queue. Queue mirip dengan konsep antrian pada kehidupan sehari-hari, dimana konsumen yang datang lebih dulu akan dilayani terlebih dahulu[1]. 
**Queue** adalah struktur data linear yang mengikuti prinsip First-In-First-Out (FIFO), di mana elemen yang pertama kali masuk akan menjadi elemen yang pertama kali keluar. Antrian terdiri dari dua ujung, yaitu front (depan) dan rear (belakang).

#### Operasi Dasar Antrian
- Enqueue: Operasi untuk memasukkan elemen baru ke dalam antrian. Elemen baru akan ditempatkan di akhir (rear) antrian. Ilustrasi operasi enqueue pada antrian dengan linked list ditunjukkan pada Gambar 1.
![Linked-List-Enqueue-1024x320](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/0cc108a4-8c64-4e23-9aae-495b590225e3)


- Dequeue: Operasi untuk mengeluarkan elemen dari antrian. Elemen yang dikeluarkan adalah elemen yang paling awal masuk ke dalam antrian (front). Ilustrasi operasi dequeue pada antrian dengan linked list ditunjukkan pada Gambar 2.
![Linked-List-Dequeue-1024x320](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/1db10261-38f3-4288-9f28-26ca899e0bfa)



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

string arrayBuku[5]; // Array untuk menyimpan data dalam stack
int maksimal = 5, top = 0; // Variabel untuk mengontrol ukuran stack dan posisi top

// Fungsi untuk memeriksa apakah stack penuh
bool isFull() {
    return (top == maksimal);
}

// Fungsi untuk memeriksa apakah stack kosong
bool isEmpety() {
    return (top == 0);
}

// Fungsi untuk menambahkan data ke dalam stack
void pushArrayBuku(string data) {
    if (isFull()) { // Jika stack penuh
        cout <<"Data telah penuh" <<endl; // Tampilkan pesan
    } else {
        arrayBuku[top] = data; // Masukkan data ke dalam stack pada posisi top
        top++; // Pindahkan posisi top ke atas
    }
}

// Fungsi untuk menghapus data teratas dari stack
void popArrayBuku() {
    if (isEmpety()) { // Jika stack kosong
        cout <<"Tidak ada data yang dihapus" <<endl; // Tampilkan pesan
    } else {
        arrayBuku[top - 1] = ""; // Hapus data teratas dengan mengosongkan nilainya
        top--; // Turunkan posisi top
    }
}

// Fungsi untuk melihat data pada posisi tertentu dalam stack
void peekArrayBuku(int posisi) {
    if (isEmpety()) { // Jika stack kosong
        cout <<"Tidak ada data yang bisa dilihat"<<endl; // Tampilkan pesan
    } else {
        int index = top;
        for(int i = 1; i <= posisi; i++) {
            index--;
        }
        cout << "Posisi ke " << posisi << " adalah " << arrayBuku[index] <<endl; // Tampilkan data pada posisi tertentu
    }
}

// Fungsi untuk menghitung jumlah data dalam stack
int countStack() {
    return top;
}

// Fungsi untuk mengubah data pada posisi tertentu dalam stack
void changeArrayBuku(int posisi, string data) {
    if (posisi > top) { // Jika posisi melebihi jumlah data dalam stack
        cout << "Posisi melebihi data yang ada" <<endl; // Tampilkan pesan
    } else {
        int index = top;
        for (int i = 1; i <= posisi; i++) {
            index--;
        }
        arrayBuku[index] = data; // Ubah data pada posisi tertentu
    }
}

// Fungsi untuk menghapus semua data dalam stack
void destroyArraybuku() {
    for (int i = top; i >= 0; i--) {
        arrayBuku[i] = ""; // Mengosongkan semua data dalam array
    }
    top = 0; // Mengatur kembali posisi top ke 0
}

// Fungsi untuk mencetak semua data dalam stack
void cetakArrayBuku() {
    if (isEmpety()) { // Jika stack kosong
        cout << "Tidak ada data yang dicetak" <<endl; // Tampilkan pesan
    } else {
        for (int i = top -1; i >= 0; i--) { // Iterasi dari top ke bawah hingga indeks ke-0
            cout << arrayBuku[i] <<endl; // Tampilkan data pada setiap indeks
        }
    }
}

int main() {
    // Menambahkan beberapa data ke dalam stack
    pushArrayBuku("Kalkulus");
    pushArrayBuku("Struktur Data");
    pushArrayBuku("Matematika Diskrit");
    pushArrayBuku("Dasar Multimedia");
    pushArrayBuku("Inggris");

    // Mencetak semua data dalam stack
    cetakArrayBuku();
    cout << "\n";

    // Memeriksa apakah stack penuh atau kosong
    cout << "Apakah data stack penuh? " << isFull() <<endl;
    cout << "Apakah data stack kosong? " << isEmpety() <<endl;

    // Melihat data pada posisi tertentu dalam stack dan menghapus data teratas
    peekArrayBuku(2);
    popArrayBuku();
    cout << "Banyaknya data = " << countStack() <<endl;

    // Mengubah data pada posisi tertentu dalam stack
    changeArrayBuku(2, "Bahasa Jerman");
    cetakArrayBuku();

    cout <<"\n";
    // Menghapus semua data dalam stack dan mencetak jumlah data
    destroyArraybuku();
    cout << "Jumlah data setelah dihapus: " << top <<endl;

    // Mencetak semua data dalam stack setelah dihapus
    cetakArrayBuku();

    return 0; // Keluar dari program
}




```
#### Output:
![Screenshot 2024-05-08 144242](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/220b33c1-f24e-47ea-a3ff-a4e9632411e2)


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
![Screenshot 2024-05-08 144258](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/f90caef3-f069-446d-b180-b7d1dda95d17)






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
[1] Asisten Praktikum, “Modul 6 Stack", Googgle Classroom, 2024.

[2] "A Survey of Stack-Based Machine Learning" oleh D. Wang et al. (2019) 

[3] "Stack-Based Memory Allocation for Deep Learning" oleh Y. Wu et al. (2019) 



