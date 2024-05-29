<p align="center">Wahyu Hidayat</p>
<p align="center">2311102178 / 11-E-IF</p>

## Dasar Teori

## **Graph dan Tree**

#### Pengertian Graph/graf
**Graf**(graph) adalah struktur data yang terdiri dari kumpulan node (vertex) dan sisi (edge) yang menghubungkan node-node tersebut. Graf dapat digunakan untuk merepresentasikan hubungan antara objek-objek tertentu dalam berbagai bidang seperti jaringan sosial, jaringan komputer, kimia, dan banyak lagi [1][2][3].
- **Graf atau graph** adalah struktur data yang digunakan untuk merepresentasikan hubungan antara objek dalam bentuk node atau vertex dan sambungan antara node tersebut dalam bentuk sisi atau edge[6]. Graf terdiri dari simpul dan busur yang secara matematis dinyatakan sebagai :
- G = (V, E)
- Dimana G adalah Graph, V adalah simpul atau vertex dan E sebagai sisi atau edge. Dapat digambarkan:


  <img src="https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/53a68266-1656-4534-ac51-233d1c6caed3" alt="Screenshot 2024-05-26 061254" width="250"/>

- #### Elemen-elemen dalam Graf:

   <img src="https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/2dcc3d0a-1513-420b-9694-11e1add40f2e" alt="Screenshot 2024-05-26 062321" width="250"/>

- Node (Vertex): Node merupakan objek yang terhubung dalam graf. Setiap node dapat memiliki nilai atau data tertentu. Node dapat mewakili berbagai entitas seperti orang, lokasi, atau objek lainnya. Dalam beberapa kasus, node juga dapat memiliki atribut tambahan seperti label atau warna. [3][4]

  ![images](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/a6a388cb-1c0d-4436-9daa-d0553c76db91)
  
- Sisi (Edge): Sisi adalah garis yang menghubungkan sepasang node dalam graf. Sisi dapat memiliki bobot (weight) atau tidak memiliki bobot. Bobot sisi dapat merepresentasikan jarak, biaya, atau kekuatan hubungan antara node. Sisi juga dapat memiliki atribut tambahan seperti label atau warna. [3][4]

  ![images](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/a180f22c-537d-4fc0-94ca-36b9e972810f)

- Adjacency: Dua node dikatakan adjacent (bertetangga) jika terhubung langsung oleh sisi. Sebuah node dapat memiliki beberapa node tetangga yang terhubung dengannya. Dalam graf berarah, sebuah node dapat memiliki node tetangga masuk (in-neighbors) dan node tetangga keluar (out-neighbors). [3][4]

  ![images](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/7571876b-3056-4112-9b23-8a2038261858)

- Derajat (Degree): Derajat suatu node adalah jumlah sisi yang terhubung dengan node tersebut. Dalam graf berarah, terdapat derajat masuk (in-degree) dan derajat keluar (out-degree). Dalam graf tidak berarah, derajat sebuah node adalah jumlah sisi yang terhubung dengannya. [1][4]

  ![images](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/0bbd5f3b-394c-475c-924d-f3fbc39c8bdf)

- Lintasan (Path): Lintasan adalah urutan node-node yang terhubung oleh sisi dalam graf. Panjang lintasan adalah jumlah sisi yang ada dalam lintasan tersebut. [1][4]

  ![images](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/50f4f598-463d-4058-8447-b29137069d6c)

- Siklus (Cycle): Siklus adalah lintasan di mana node awal dan node akhir adalah sama. Siklus tidak diperbolehkan dalam struktur data pohon (tree). [1][4]

- #### Jenis-jenis Graf:



  ![Screenshot 2024-05-26 065750](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/93e55e3c-be4f-4c93-95be-a43401990deb)
- a. Graph berarah (directed graph): Urutan simpul mempunyai arti. Misal busur AB adalah e1 sedangkan busur BA adalah e8.
- b. Graph tak berarah (undirected graph): Urutan simpul dalam sebuah busur tidak diperhatikan. Misal busur e1 dapat disebut busur AB atau BA.
- c. Weight Graph : Graph yang mempunyai nilai pada tiap edgenya.


  ![images](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/b0cf1934-90f7-43b2-83b5-3d7ba131f863)
  
- Graf Berarah (Directed Graph): Graf di mana setiap sisi memiliki arah dari satu node ke node lainnya. Sisi diwakili dengan panah yang menunjukkan arah. Dalam graf berarah, derajat masuk dan derajat keluar node dapat berbeda. [1][3][4]

  ![images](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/765409a2-9bbd-4979-ba10-1df54a602fec)

- Graf Tidak Berarah (Undirected Graph): Graf di mana sisi tidak memiliki arah, sehingga hubungan antara node adalah dua arah. Dalam graf tidak berarah, derajat masuk dan derajat keluar node selalu sama. [1][3][4]

  ![images](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/92a73f28-74ae-4cbb-b3c2-0b67cc83a5c2)

- Graf Berbobot (Weighted Graph): Graf di mana setiap sisi memiliki bobot atau nilai tertentu yang mewakili jarak, biaya, atau kekuatan hubungan. Bobot sisi dapat bernilai positif atau negatif. [1][3][4]

  ![images](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/bdb4fda3-2adc-4262-a9e4-a9926f22eac6)

- Graf Tidak Berbobot (Unweighted Graph): Graf di mana sisi tidak memiliki bobot. Semua sisi dianggap memiliki bobot yang sama, biasanya bernilai 1. [1][3][4]

  ![images](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/953bf460-c7d7-49a4-98b6-3c7409c32985)

- Graf Terhubung (Connected Graph): Graf di mana setiap pasangan node terhubung melalui setidaknya satu jalur sisi. Jika tidak, graf disebut tidak terhubung. Dalam graf tidak terhubung, terdapat beberapa komponen terhubung. [1][4]

  ![images](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/5ec3c072-77bb-4916-8bda-a9bb3f7497b1)

- Graf Lengkap (Complete Graph): Graf tidak berarah di mana setiap pasangan node terhubung langsung oleh sisi. Dalam graf lengkap dengan n node, terdapat (n(n-1))/2 sisi. [1][4]

  ![images](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/0eb326fc-6559-4826-8b77-6c12410534af)

- Graf Planar: Graf yang dapat digambarkan pada bidang datar tanpa ada sisi yang bersilangan. Graf planar memiliki banyak aplikasi dalam bidang visualisasi data dan desain sirkuit. [4][5]

  ![images](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/4fbf5867-58de-435a-a5b1-d8db90039dc8)

- Graf Bipartit: Graf di mana himpunan node dapat dipartisi menjadi dua himpunan terpisah sedemikian rupa sehingga setiap sisi menghubungkan sepasang node dari dua himpunan yang berbeda. Graf bipartit banyak digunakan dalam masalah pencocokan dan pewarnaan graf. [4][5]

Graf memiliki banyak aplikasi dalam berbagai bidang, seperti analisis jaringan sosial, pencarian rute terpendek, deteksi komunitas, analisis data, visualisasi data, dan banyak lagi. Pemahaman dasar tentang graf sangat penting dalam pengembangan algoritma dan pemecahan masalah kompleks. [2][3][4]

- #### Representasi Graph Representasi dengan Matriks
  
  <img src="https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/ed6a415d-39c3-4245-9c10-1c90ef28adbc" alt="Screenshot 2024-05-26 070047" width="300"/>

- #### Representasi dengan Linked List

<img src="https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/3511e579-54b0-46c7-a6ed-211534b7ee6b" alt="Screenshot 2024-05-26 070328" width="300"/>


Memahami perbedaan antara simpul vertex dan simpul edge sangat penting saat membuat representasi graf dalam bentuk linked list.

- Simpul Vertex: Mewakili titik atau simpul dalam graf.
- Simpul Edge: Mewakili hubungan antara simpul-simpul tersebut.
Struktur simpul vertex dan simpul edge bisa sama atau berbeda tergantung pada kebutuhan, namun biasanya seragam. Perbedaan utama terletak pada bagaimana kita memperlakukan dan menggunakan keduanya dalam representasi graf.

<img src="https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/55832310-0878-434e-bcf6-620fa4c977b5" alt="Screenshot 2024-05-26 070759" width="300"/>




#### 1. Definisi Tree (Pohon)
- Sebuah tree (pohon) adalah struktur data non-linear yang terdiri dari simpul-simpul (nodes) yang terhubung secara hierarkis. Setiap simpul memiliki satu induk (parent) kecuali simpul akar (root), dan dapat memiliki beberapa anak (children) [7].

- Dalam ilmu komputer, pohon/tree adalah struktur data yang sangat umum dan kuat yang menyerupai nyata pohon. Ini terdiri dari satu set node tertaut yang terurut dalam grafik yang terhubung, dimana setiap node memiliki paling banyak satu simpul induk, dan nol atau lebih simpul anak dengan urutan tertentu. Struktur data tree digunakan untuk menyimpan data-data hirarki seperti pohon keluarga, skema pertandingan, struktur organisasi[6]. Istilah dalam struktur data tree dapat dirangkum sebagai berikut : 

![Screenshot 2024-05-29 084449](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/9380f769-c252-4713-956e-e931a740da5c)


- Binary tree atau pohon biner merupakan struktur data pohon akan tetapi setiap simpul dalam pohon diprasyaratkan memiliki simpul satu level di bawahnya (child)tidak lebih dari 2 simpul, artinya jumlah child yang diperbolehkan yakni 0, 1, dan 2. Gambar 1, menunjukkan contoh dari struktur data binary tree.

![Screenshot 2024-05-29 084725](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/e6512917-3ef9-4b7f-ab9d-e4bb78baf251)

- Membuat struktur data binary tree dalam suatu program (berbahasa C++) dapat menggunakan struct yang memiliki 2 buah pointer, seperti halnya double linked list.

![Screenshot 2024-05-29 085001](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/ca78b395-9340-4e3b-a2f4-ea06762684d0)

#### 2. Operasi pada Tree
- a. Create: digunakan untuk membentuk binary tree baru yang masih kosong.
- b. Clear: digunakan untuk mengosongkan binary tree yang sudah ada atau menghapus semua node pada binary tree.
- c. isEmpty: digunakan untuk memeriksa apakah binary tree masih kosong atau tidak.
- d. Insert: digunakan untuk memasukkan sebuah node kedalam tree.
- e. Find: digunakan untuk mencari root, parent, left child, atau right child dari suatu node dengan syarat tree tidak boleh kosong.
- f. Update: digunakan untuk mengubah isi dari node yang ditunjuk oleh pointer current dengan syarat tree tidak boleh kosong.
- g. Retrive: digunakan untuk mengetahui isi dari node yang ditunjuk pointer current dengan syarat tree tidak boleh kosong.
- h. Delete Sub: digunakan untuk menghapus sebuah subtree (node beserta seluruh descendant-nya) yang ditunjuk pointer current dengan syarat tree tidak boleh kosong.
- i. Characteristic: digunakan untuk mengetahui karakteristik dari suatu tree. Yakni size, height, serta average lenght-nya.
- j. Traverse: digunakan untuk mengunjungi seluruh node-node pada tree dengan cara traversal. Terdapat 3 metode traversal yang dibahas dalam modul ini yakni Pre-Order, In-Order, dan Post-Order.
- 1. Pre-Order Penelusuran secara pre-order memiliki alur:
  - a. Cetak data pada simpul root
  - b. Secara rekursif mencetak seluruh data pada subpohon kiri
  - c. Secara rekursif mencetak seluruh data pada subpohon kanan Dapat kita turunkan rumus penelusuran menjadi:

![Screenshot 2024-05-29 085316](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/1ca71941-7fe2-4c3d-856e-2ef213d6ec14)

![Screenshot 2024-05-29 085340](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/42d12956-5b75-48d3-b2b1-98fbab377399)

- 2. In-Order Penelusuran secara in-order memiliki alur:
  - a. Secara rekursif mencetak seluruh data pada subpohon kiri
  - b. Cetak data pada root
  - c. Secara rekursif mencetak seluruh data pada subpohon kanan Dapat kita turunkan rumus penelusuran menjadi:

![Screenshot 2024-05-29 085946](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/f46b335e-c307-4246-81b8-3462b430d996)

- 3. Post Order Penelusuran secara in-order memiliki alur:
  - a. Secara rekursif mencetak seluruh data pada subpohon kiri
  - b. Secara rekursif mencetak seluruh data pada subpohon kanan
  - c. Cetak data pada root
Dapat kita turunkan rumus penelusuran menjadi:

![Screenshot 2024-05-29 090113](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/fbe46d96-eba0-4640-b3d8-23de074121b7)

#### 3. Terminologi dalam Tree


- Root (Akar): Simpul tertinggi dalam pohon yang tidak memiliki induk.
- Parent (Induk): Simpul yang memiliki satu atau lebih anak.
- Child (Anak): Simpul yang memiliki induk.
- Sibling (Saudara): Simpul-simpul yang memiliki induk yang sama.
- Leaf (Daun): Simpul yang tidak memiliki anak.
- Internal Node (Simpul Internal): Simpul yang memiliki setidaknya satu anak.
- Depth (Kedalaman): Panjang jalur dari akar ke simpul tertentu.
- Height (Tinggi): Panjang jalur terpanjang dari akar ke daun.


#### 4. Jenis-jenis Tree


- Binary Tree: Setiap simpul memiliki maksimum dua anak.
- Binary Search Tree (BST): Jenis khusus dari binary tree, di mana setiap simpul pada sisi kiri memiliki nilai yang lebih kecil dari induknya, dan setiap simpul pada sisi kanan memiliki nilai yang lebih besar dari induknya.
- Balanced Binary Tree: Binary tree di mana kedalaman untuk setiap cabang kiri dan kanan tidak berbeda lebih dari satu.
- N-ary Tree: Setiap simpul dapat memiliki lebih dari dua anak.
- Trie (Prefiks Tree): Tree yang digunakan untuk menyimpan dan mencari string [8].


#### 5. Operasi pada Tree


- Traversal (Pelacakan): Kunjungan ke setiap simpul dalam tree, seperti preorder, inorder, dan postorder traversal.
- Insertion (Penyisipan): Menambahkan simpul baru ke dalam tree.
- Deletion (Penghapusan): Menghapus simpul dari tree.
- Searching (Pencarian): Menemukan simpul tertentu dalam tree.


#### 6. Aplikasi Tree
- Tree digunakan dalam berbagai bidang komputasi, seperti pengindeksan file sistem, kompresi data, pengambilan keputusan, dan banyak lagi. Penggunaan tree yang umum meliputi struktur direktori dalam sistem operasi, sintaks parsing, dan pemrosesan ekspresi matematika [9].


## Guided 
### Guided 1
#### Program Graph
```C++
#include <iostream> // Mengimpor pustaka input-output standar
#include <iomanip>  // Mengimpor pustaka manipulasi IO
using namespace std; // Menggunakan namespace std

// Array simpul yang menyimpan nama-nama kota
string simpul[7] = {
    "Ciamis",
    "Bandung",
    "Bekasi",
    "Tasikmalaya",
    "Cianjur",
    "Purwokerto",
    "Yogyakarta"
};

// Matriks busur yang menyimpan bobot/biaya antara dua simpul (kota)
int busur[7][7] = {
    {0, 7, 8, 0, 0, 0, 0},    // Ciamis ke Bandung (7), Bekasi (8)
    {0, 0, 5, 0, 0, 15, 0},   // Bandung ke Bekasi (5), Purwokerto (15)
    {0, 6, 0, 0, 5, 0, 0},    // Bekasi ke Bandung (6), Cianjur (5)
    {0, 5, 0, 0, 2, 4, 0},    // Tasikmalaya ke Bandung (5), Cianjur (2), Purwokerto (4)
    {23, 0, 0, 10, 0, 0, 8},  // Cianjur ke Ciamis (23), Tasikmalaya (10), Yogyakarta (8)
    {0, 0, 0, 0, 7, 0, 3},    // Purwokerto ke Cianjur (7), Yogyakarta (3)
    {0, 0, 0, 0, 9, 4, 0}     // Yogyakarta ke Cianjur (9), Purwokerto (4)
};

// Fungsi untuk menampilkan graf
void tampilGraph(){
    for (int baris = 0; baris < 7; baris++) { // Loop untuk setiap baris (simpul)
        // Menampilkan nama simpul dengan lebar tetap 15 karakter
        cout << " " << setiosflags(ios::left) << setw(15) << simpul[baris] << " : ";
        
        for (int kolom = 0; kolom < 7; kolom++) { // Loop untuk setiap kolom (simpul tujuan)
            if (busur[baris][kolom] != 0) { // Jika ada busur (bobot tidak nol)
                // Menampilkan nama simpul tujuan dan bobot busur
                cout << " " << simpul[kolom] << "(" << busur[baris][kolom] << ")";
            }
        }
        cout << endl; // Baris baru setelah setiap baris simpul selesai diproses
    }
}

int main(){
    tampilGraph(); // Memanggil fungsi untuk menampilkan graf
    return 0; // Mengembalikan nilai 0 menandakan program selesai dengan sukses
}





```
#### Output:
![Screenshot 2024-05-29 091138](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/ac774058-a40b-4b93-a9cd-2d9f8855e876)


Kode diatas bertujuan untuk menampilkan graf yang merepresentasikan koneksi antar simpul (kota) beserta bobotnya (misalnya jarak atau biaya). Dalam program ini, terdapat array simpul yang menyimpan nama-nama kota dan matriks busur yang menyimpan bobot koneksi antar kota. Fungsi tampilGraph digunakan untuk menampilkan graf. Fungsi ini bekerja dengan melakukan iterasi melalui setiap simpul (baris dalam matriks busur). Untuk setiap simpul, ia menampilkan nama simpul tersebut dengan lebar tetap 15 karakter. Kemudian, ia memeriksa setiap koneksi dari simpul tersebut ke simpul lain (kolom dalam matriks busur). Jika terdapat koneksi (bobot tidak nol), ia akan menampilkan nama simpul tujuan dan bobot koneksinya dalam format yang jelas. Akhirnya, main memanggil fungsi tampilGraph untuk menampilkan seluruh graf. Output dari program ini adalah daftar simpul beserta koneksi mereka dan bobot masing-masing, dalam format yang mudah dibaca.

#### Full code Screenshot:
![Screenshot 2024-05-29 091051](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/684504c6-589a-43b9-b6f2-feb213e94b88)


### Guided 2
#### Program Tree

```C++
#include <iostream>
using namespace std;

// PROGRAM BINARY TREE
// Deklarasi Pohon
struct Pohon {
    char data;
    Pohon *left, *right, *parent; // pointer untuk left child, right child, dan parent
};

// pointer global
Pohon *root;

// Inisialisasi
void init() {
    root = NULL; // inisialisasi root menjadi NULL
}

// Fungsi untuk mengecek apakah tree kosong
bool isEmpty() {
    return root == NULL; // mengembalikan true jika root NULL
}

// Fungsi untuk membuat node baru
Pohon *newPohon(char data) {
    Pohon *node = new Pohon(); // alokasi memori untuk node baru
    node->data = data; // mengisi data pada node
    node->left = NULL; // inisialisasi left child ke NULL
    node->right = NULL; // inisialisasi right child ke NULL
    node->parent = NULL; // inisialisasi parent ke NULL
    return node;
}

// Fungsi untuk membuat root node
void buatNode(char data) {
    if (isEmpty()) {
        root = newPohon(data); // membuat root node jika tree kosong
        cout << "\nNode " << data << " berhasil dibuat menjadi root." << endl;
    } else {
        cout << "\nPohon sudah dibuat" << endl; // jika root sudah ada
    }
}

// Fungsi untuk menambahkan node ke left child
Pohon *insertLeft(char data, Pohon *node) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
        return NULL;
    } else {
        if (node->left != NULL) {
            cout << "\nNode " << node->data << " sudah ada child kiri!" << endl; // pesan jika left child sudah ada
            return NULL;
        } else {
            Pohon *baru = newPohon(data); // membuat node baru
            baru->parent = node; // mengatur parent node baru
            node->left = baru; // mengatur left child pada node
            cout << "\nNode " << data << " berhasil ditambahkan ke child kiri " << node->data << endl;
            return baru;
        }
    }
}

// Fungsi untuk menambahkan node ke right child
Pohon *insertRight(char data, Pohon *node) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
        return NULL;
    } else {
        if (node->right != NULL) {
            cout << "\nNode " << node->data << " sudah ada child kanan!" << endl; // pesan jika right child sudah ada
            return NULL;
        } else {
            Pohon *baru = newPohon(data); // membuat node baru
            baru->parent = node; // mengatur parent node baru
            node->right = baru; // mengatur right child pada node
            cout << "\nNode " << data << " berhasil ditambahkan ke child kanan " << node->data << endl;
            return baru;
        }
    }
}

// Fungsi untuk mengupdate data pada node
void update(char data, Pohon *node) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
    } else {
        if (!node)
            cout << "\nNode yang ingin diganti tidak ada!!" << endl; // pesan jika node tidak ditemukan
        else {
            char temp = node->data; // menyimpan data lama
            node->data = data; // mengganti data dengan yang baru
            cout << "\nNode " << temp << " berhasil diubah menjadi " << data << endl;
        }
    }
}

// Fungsi untuk mengambil data dari node
void retrieve(Pohon *node) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
    } else {
        if (!node)
            cout << "\nNode yang ditunjuk tidak ada!" << endl; // pesan jika node tidak ditemukan
        else {
            cout << "\nData node : " << node->data << endl; // menampilkan data node
        }
    }
}

// Fungsi untuk menemukan data pada node dan menampilkan informasi terkait
void find(Pohon *node) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
    } else {
        if (!node)
            cout << "\nNode yang ditunjuk tidak ada!" << endl; // pesan jika node tidak ditemukan
        else {
            cout << "\nData Node : " << node->data << endl;
            cout << "Root : " << root->data << endl; // menampilkan data root
            if (!node->parent)
                cout << "Parent : (tidak punya parent)" << endl; // pesan jika tidak punya parent
            else
                cout << "Parent : " << node->parent->data << endl; // menampilkan data parent
            if (node->parent != NULL && node->parent->left != node && node->parent->right == node)
                cout << "Sibling : " << node->parent->left->data << endl; // menampilkan data sibling kiri
            else if (node->parent != NULL && node->parent->right != node && node->parent->left == node)
                cout << "Sibling : " << node->parent->right->data << endl; // menampilkan data sibling kanan
            else
                cout << "Sibling : (tidak punya sibling)" << endl; // pesan jika tidak punya sibling
            if (!node->left)
                cout << "Child Kiri : (tidak punya Child kiri)" << endl; // pesan jika tidak punya child kiri
            else
                cout << "Child Kiri : " << node->left->data << endl; // menampilkan data child kiri
            if (!node->right)
                cout << "Child Kanan : (tidak punya Child kanan)" << endl; // pesan jika tidak punya child kanan
            else
                cout << "Child Kanan : " << node->right->data << endl; // menampilkan data child kanan
        }
    }
}

// Fungsi penelusuran (Traversal)
// preOrder
void preOrder(Pohon *node) {
    if (isEmpty())
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
    else {
        if (node != NULL) {
            cout << " " << node->data << ", "; // menampilkan data node
            preOrder(node->left); // rekursif ke left child
            preOrder(node->right); // rekursif ke right child
        }
    }
}

// inOrder
void inOrder(Pohon *node) {
    if (isEmpty())
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
    else {
        if (node != NULL) {
            inOrder(node->left); // rekursif ke left child
            cout << " " << node->data << ", "; // menampilkan data node
            inOrder(node->right); // rekursif ke right child
        }
    }
}

// postOrder
void postOrder(Pohon *node) {
    if (isEmpty())
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
    else {
        if (node != NULL) {
            postOrder(node->left); // rekursif ke left child
            postOrder(node->right); // rekursif ke right child
            cout << " " << node->data << ", "; // menampilkan data node
        }
    }
}

// Fungsi untuk menghapus node tree
void deleteTree(Pohon *node) {
    if (isEmpty())
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
    else {
        if (node != NULL) {
            if (node != root) {
                if (node->parent->left == node)
                    node->parent->left = NULL; // menghapus link ke left child
                else if (node->parent->right == node)
                    node->parent->right = NULL; // menghapus link ke right child
            }
            deleteTree(node->left); // rekursif ke left child
            deleteTree(node->right); // rekursif ke right child
            if (node == root) {
                delete root; // menghapus root
                root = NULL;
            } else {
                delete node; // menghapus node
            }
        }
    }
}

// Fungsi untuk menghapus subtree
void deleteSub(Pohon *node) {
    if (isEmpty())
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
    else {
        deleteTree(node->left); // menghapus subtree left child
        deleteTree(node->right); // menghapus subtree right child
        cout << "\nNode subtree " << node->data << " berhasil dihapus." << endl;
    }
}

// Fungsi untuk menghapus seluruh tree
void clear() {
    if (isEmpty())
        cout << "\nBuat tree terlebih dahulu!!" << endl; // pesan jika tree belum dibuat
    else {
        deleteTree(root); // menghapus seluruh tree
        cout << "\nPohon berhasil dihapus." << endl;
    }
}

// Fungsi untuk cek ukuran tree
int size(Pohon *node) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!!" << endl; // pesan jika tree belum dibuat
        return 0;
    } else {
        if (!node) {
            return 0; // jika node NULL, return 0
        } else {
            return 1 + size(node->left) + size(node->right); // menghitung ukuran tree
        }
    }
}

// Fungsi untuk cek tinggi (height) tree
int height(Pohon *node) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
        return 0;
    } else {
        if (!node) {
            return 0; // jika node NULL, return 0
        } else {
            int heightKiri = height(node->left); // menghitung tinggi left child
            int heightKanan = height(node->right); // menghitung tinggi right child
            if (heightKiri >= heightKanan) {
                return heightKiri + 1; // mengembalikan tinggi maksimum
            } else {
                return heightKanan + 1; // mengembalikan tinggi maksimum
            }
        }
    }
}

// Fungsi untuk menampilkan karakteristik tree
void characteristic() {
    int s = size(root); // menghitung ukuran tree
    int h = height(root); // menghitung tinggi tree
    cout << "\nSize Tree : " << s << endl;
    cout << "Height Tree : " << h << endl;
    if (h != 0)
        cout << "Average Node of Tree : " << s / h << endl; // menghitung rata-rata node per level
    else
        cout << "Average Node of Tree : 0" << endl;
}

int main() {
    init(); // inisialisasi tree
    buatNode('A'); // membuat root node 'A'
    
    // Menambahkan node ke tree
    Pohon *nodeB, *nodeC, *nodeD, *nodeE, *nodeF, *nodeG, *nodeH, *nodeI, *nodeJ;
    nodeB = insertLeft('B', root);
    nodeC = insertRight('C', root);
    nodeD = insertLeft('D', nodeB);
    nodeE = insertRight('E', nodeB);
    nodeF = insertLeft('F', nodeC);
    nodeG = insertLeft('G', nodeE);
    nodeH = insertRight('H', nodeE);
    nodeI = insertLeft('I', nodeG);
    nodeJ = insertRight('J', nodeG);
    
    update('Z', nodeC); // mengubah data node 'C' menjadi 'Z'
    update('C', nodeC); // mengubah data node 'Z' kembali menjadi 'C'
    
    retrieve(nodeC); // mengambil data dari node 'C'
    find(nodeC); // menemukan data pada node 'C' dan menampilkan informasi terkait
    
    // Menampilkan traversal tree
    cout << "\nPreOrder :" << endl;
    preOrder(root);
    cout << "\n" << endl;
    
    cout << "InOrder :" << endl;
    inOrder(root);
    cout << "\n" << endl;
    
    cout << "PostOrder :" << endl;
    postOrder(root);
    cout << "\n" << endl;
    
    characteristic(); // menampilkan karakteristik tree
    
    deleteSub(nodeE); // menghapus subtree dari node 'E'
    
    cout << "\nPreOrder :" << endl;
    preOrder(root);
    cout << "\n" << endl;
    
    characteristic(); // menampilkan karakteristik tree setelah penghapusan subtree
    
    return 0;
}


```
#### Output:

![Screenshot 2024-05-29 092033](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/347b16b6-237d-44de-abf7-f617099518e6)


Kode ini merupakan implementasi dari struktur data pohon biner yang menyediakan berbagai operasi untuk manipulasi pohon biner. Pada awalnya, pohon diinisialisasi dengan pointer global `root` yang menunjuk ke `NULL`. Program ini mencakup fungsi-fungsi untuk mengecek apakah pohon kosong (`isEmpty`), membuat node baru (`newPohon`), menambahkan node ke pohon sebagai root (`buatNode`), dan menambahkan node sebagai anak kiri (`insertLeft`) atau anak kanan (`insertRight`). Selain itu, terdapat fungsi untuk mengubah data pada node (`update`), mengambil data dari node (`retrieve`), dan menemukan serta menampilkan informasi tentang node tertentu (`find`).

Penelusuran pohon dapat dilakukan dengan tiga cara: pre-order (`preOrder`), in-order (`inOrder`), dan post-order (`postOrder`). Program ini juga menyediakan fungsi untuk menghapus node dari pohon (`deleteTree`), menghapus subtree dari node tertentu (`deleteSub`), serta menghapus seluruh pohon (`clear`). Selain itu, terdapat fungsi untuk menghitung ukuran (`size`) dan tinggi (`height`) pohon, serta menampilkan karakteristik pohon seperti ukuran, tinggi, dan rata-rata node per level (`characteristic`).

Dalam fungsi `main`, pohon diinisialisasi dan beberapa node ditambahkan untuk membentuk struktur pohon biner. Beberapa operasi dilakukan termasuk pengubahan data pada node, penelusuran pohon, serta penghapusan subtree, yang diikuti dengan menampilkan kembali penelusuran pohon dan karakteristik pohon setelah perubahan. Program ini menampilkan hasil dari setiap operasi pada pohon biner untuk membantu pengguna memahami perubahan yang terjadi pada struktur pohon.

#### Full code Screenshot:




## Unguided 

#### 1. Buatlah program graph dengan menggunakan inputan user untuk menghitung jarak dari sebuah kota ke kota lainnya.

```C++
#include <iostream>
#include <iomanip>
#include <string>
using namespace std;

// Struktur untuk merepresentasikan edge antar simpul
struct Edge {
    int wahyu_2311102178, destination, weight;
};

class Graph {
    int V; // Jumlah simpul
    Edge edges[100]; // Array untuk menyimpan edge, diasumsikan maksimal 100 edges
    int edgeCount; // Jumlah edge yang ada

public:
    // Konstruktor
    Graph(int vertices) {
        V = vertices; // Inisialisasi jumlah simpul
        edgeCount = 0; // Inisialisasi jumlah edge
    }

    // Menambahkan edge ke graf
    void addEdge(int wahyu_2311102178, int destination, int weight) {
        edges[edgeCount++] = {wahyu_2311102178, destination, weight}; // Menambahkan edge ke dalam array edges
    }

    string nodeNames[10]; // Array untuk menyimpan nama simpul, diasumsikan maksimal 10 simpul

    // Mencetak matriks adjacency
    void printAdjacencyMatrix() {
        int matrix[10][10] = {}; // Membuat matriks 10x10 dan mengisinya dengan 0

        // Mengisi matriks dengan bobot edge
        for (int i = 0; i < edgeCount; ++i) {
            matrix[edges[i].wahyu_2311102178][edges[i].destination] = edges[i].weight;
        }

        // Mencetak nama simpul di bagian atas kolom
        cout << setw(11) << " "; // Spasi untuk penjajaran
        for (int i = 0; i < V; ++i) {
            cout << setw(11) << nodeNames[i] << " "; // Mencetak nama simpul
        }
        cout << endl;

        // Mencetak matriks adjacency
        for (int i = 0; i < V; ++i) {
            cout << setw(10) << nodeNames[i] << " "; // Mencetak nama simpul di awal setiap baris
            for (int j = 0; j < V; ++j) {
                cout << setw(10) << matrix[i][j] << "  "; // Mencetak bobot antar simpul
            }
            cout << endl;
        }
    }
};

int main() {
    int jumlahSimpul; // Variabel untuk menyimpan jumlah simpul
    cout << "Silakan masukan jumlah simpul : ";
    cin >> jumlahSimpul; // Input jumlah simpul dari pengguna

    Graph graph(jumlahSimpul); // Membuat graf dengan jumlah simpul yang diberikan

    // Input nama simpul
    cout << "Silakan masukan nama simpul" << endl;
    for (int i = 0; i < jumlahSimpul; ++i) {
        cout << "Simpul " << i + 1 << " : ";
        cin >> graph.nodeNames[i]; // Input nama simpul dari pengguna
    }

    // Input bobot antar simpul
    cout << "Silakan masukkan bobot antar simpul" << endl;
    for (int i = 0; i < jumlahSimpul; ++i) {
        for (int j = 0; j < jumlahSimpul; ++j) {
            int weight;
            cout << graph.nodeNames[i] << "-->" << graph.nodeNames[j] << " = ";
            cin >> weight; // Input bobot dari pengguna
            graph.addEdge(i, j, weight); // Menambahkan edge ke graf
        }
    }

    // Mencetak matriks adjacency
    graph.printAdjacencyMatrix(); // Memanggil fungsi untuk mencetak matriks adjacency

    return 0;
}



```
#### Output:
![Screenshot 2024-05-29 113159](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/f988c9a2-5cbf-4b1d-9d43-77203ebcd97f)


- kode ini dimulai dengan menyertakan pustaka standar iostream dan iomanip untuk melakukan operasi input/output dan format output. Struktur Edge digunakan untuk merepresentasikan sebuah busur dalam graf, yang terdiri dari simpul sumber (source), simpul tujuan (destination), dan bobot (weight).

- Kelas Graph dirancang untuk menyimpan dan memanipulasi graf. Kelas ini memiliki variabel anggota V untuk menyimpan jumlah simpul, edges berupa array untuk menyimpan busur graf, dan edgeCount untuk menghitung jumlah busur yang ada. Kelas ini juga memiliki metode addEdge untuk menambahkan busur ke dalam array edges, serta metode printAdjacencyMatrix untuk mencetak matriks adjacency graf.

- Di dalam printAdjacencyMatrix, sebuah matriks 10x10 diinisialisasi dengan nilai nol, lalu diisi dengan bobot dari setiap busur yang ada di dalam array edges. Nama-nama simpul dicetak sebagai header kolom dan baris untuk matriks tersebut. Matriks adjacency kemudian dicetak, menampilkan bobot di antara setiap pasangan simpul.

- Fungsi main bertugas untuk membaca input dari pengguna. Pengguna diminta untuk memasukkan jumlah simpul yang akan digunakan. Setelah itu, nama setiap simpul dimasukkan dan disimpan dalam array nodeNames yang berada di dalam kelas Graph. Pengguna kemudian diminta untuk memasukkan bobot antara setiap pasangan simpul, dan informasi ini digunakan untuk menambahkan busur ke graf melalui metode addEdge.

- Setelah semua data dimasukkan, matriks adjacency dicetak menggunakan metode printAdjacencyMatrix, yang memberikan tampilan tabel bobot antara setiap simpul dengan format yang rapi.
  
#### Full code Screenshot:

![Screenshot 2024-05-29 113116](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/c3644b70-8cb9-4f2c-9340-3022e0d2517d)


#### 2. Buatlah sebuah program yang dapat menghitung banyaknya huruf vocal dalam sebuah kalimat!

```C++
#include <iostream>
using namespace std;

// PROGRAM BINARY TREE
// Deklarasi Pohon
struct Pohon {
    char data;
    Pohon *left, *right, *parent; // pointer untuk left child, right child, dan parent
};

// pointer global
Pohon *root;

// Inisialisasi
void init() {
    root = NULL; // inisialisasi root menjadi NULL
}

// Fungsi untuk mengecek apakah tree kosong
bool isEmpty() {
    return root == NULL; // mengembalikan true jika root NULL
}

// Fungsi untuk membuat node baru
Pohon *newPohon(char data) {
    Pohon *node = new Pohon(); // alokasi memori untuk node baru
    node->data = data; // mengisi data pada node
    node->left = NULL; // inisialisasi left child ke NULL
    node->right = NULL; // inisialisasi right child ke NULL
    node->parent = NULL; // inisialisasi parent ke NULL
    return node;
}

// Fungsi untuk membuat root node
void buatNode(char data) {
    if (isEmpty()) {
        root = newPohon(data); // membuat root node jika tree kosong
        cout << "\nNode " << data << " berhasil dibuat menjadi root." << endl;
    } else {
        cout << "\nPohon sudah dibuat" << endl; // jika root sudah ada
    }
}

// Fungsi untuk menambahkan node ke left child
Pohon *insertLeft(char data, Pohon *node) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
        return NULL;
    } else {
        if (node->left != NULL) {
            cout << "\nNode " << node->data << " sudah ada child kiri!" << endl; // pesan jika left child sudah ada
            return NULL;
        } else {
            Pohon *baru = newPohon(data); // membuat node baru
            baru->parent = node; // mengatur parent node baru
            node->left = baru; // mengatur left child pada node
            cout << "\nNode " << data << " berhasil ditambahkan ke child kiri " << node->data << endl;
            return baru;
        }
    }
}

// Fungsi untuk menambahkan node ke right child
Pohon *insertRight(char data, Pohon *node) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
        return NULL;
    } else {
        if (node->right != NULL) {
            cout << "\nNode " << node->data << " sudah ada child kanan!" << endl; // pesan jika right child sudah ada
            return NULL;
        } else {
            Pohon *baru = newPohon(data); // membuat node baru
            baru->parent = node; // mengatur parent node baru
            node->right = baru; // mengatur right child pada node
            cout << "\nNode " << data << " berhasil ditambahkan ke child kanan " << node->data << endl;
            return baru;
        }
    }
}

// Fungsi untuk mengupdate data pada node
void update(char data, Pohon *node) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
    } else {
        if (!node)
            cout << "\nNode yang ingin digantitidak ada!!" << endl; // pesan jika node tidak ditemukan
        else {
            char temp = node->data; // menyimpan data lama
            node->data = data; // mengganti data dengan yang baru
            cout << "\nNode " << temp << " berhasil diubah menjadi " << data << endl;
        }
    }
}

// Fungsi untuk mengambil data dari node
void retrieve(Pohon *node) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
    } else {
        if (!node)
            cout << "\nNode yang ditunjuk tidak ada!" << endl; // pesan jika node tidak ditemukan
        else {
            cout << "\nData node : " << node->data << endl; // menampilkan data node
        }
    }
}

// Fungsi untuk menemukan data pada node dan menampilkan informasi terkait
void find(Pohon *node) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
    } else {
        if (!node)
            cout << "\nNode yang ditunjuk tidak ada!" << endl; // pesan jika node tidak ditemukan
        else {
            cout << "\nData Node : " << node->data << endl;
            cout << "Root : " << (root ? to_string(root->data) : "NULL") << endl; // menampilkan data root
            if (!node->parent)
                cout << "Parent : (tidak punya parent)" << endl; // pesan jika tidak punya parent
            else
                cout << "Parent : " << node->parent->data << endl; // menampilkan data parent
            if (node->parent != NULL && node->parent->left != node && node->parent->right == node)
                cout << "Sibling : " << node->parent->left->data << endl; // menampilkan data sibling kiri
            else if (node->parent != NULL && node->parent->right != node && node->parent->left == node)
                cout << "Sibling : " << node->parent->right->data << endl; // menampilkan data sibling kanan
            else
                cout << "Sibling : (tidak punya sibling)" << endl; // pesan jika tidak punya sibling
            if (!node->left)
                cout << "Child Kiri : (tidak punya Child kiri)" << endl; // pesan jika tidak punya child kiri
            else
                cout << "Child Kiri : " << node->left->data << endl; // menampilkan data child kiri
            if (!node->right)
                cout << "Child Kanan : (tidak punya Child kanan)" << endl; // pesan jika tidak punya child kanan
            else
                cout << "Child Kanan : " << node->right->data << endl; // menampilkan data child kanan
        }
    }
}

// Fungsi penelusuran (Traversal)
// preOrder
void preOrder(Pohon *node) {
    if (isEmpty())
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
    else {
        if (node != NULL) {
            cout << " " << node->data << ", "; // menampilkan data node
            preOrder(node->left); // rekursif ke left child
            preOrder(node->right); // rekursif ke right child
        }
    }
}

// inOrder
void inOrder(Pohon *node) {
    if (isEmpty())
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
    else {
        if (node != NULL) {
            inOrder(node->left); // rekursif ke left child
            cout << " " << node->data << ", "; // menampilkan data node
            inOrder(node->right); // rekursif ke right child
        }
    }
}

//] postOrder
void postOrder(Pohon *node) {
    if (isEmpty())
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
    else {
        if (node != NULL) {
            postOrder(node->left); // rekursif ke left child
            postOrder(node->right); // rekursif ke right child
            cout << " " << node->data << ", "; // menampilkan data node
        }
    }
}

// Fungsi untuk menghapus node tree
void deleteTree(Pohon *node) {
    if (isEmpty())
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
    else {
        if (node != NULL) {
            if (node != root) {
                if (node->parent->left == node)
                    node->parent->left = NULL; // menghapus link ke left child
                else if (node->parent->right == node)
                    node->parent->right = NULL; // menghapus link ke right child
            }
            deleteTree(node->left); // rekursif ke left child
            deleteTree(node->right); // rekursif ke right child
            if (node == root) {
                delete root; // menghapus root
                root = NULL;
            } else {
                delete node; // menghapus node
            }
        }
    }
}

// Fungsi untuk menghapus subtree
void deleteSub(Pohon *node) {
    if (isEmpty())
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
    else {
        deleteTree(node->left); // menghapus subtree left child
        deleteTree(node->right); // menghapus subtree right child
        cout << "\nNode subtree " << node->data << " berhasil dihapus." << endl;
    }
}

// Fungsi untuk menghapus seluruh tree
void clear() {
    if (isEmpty())
        cout << "\nBuat tree terlebih dahulu!!" << endl; // pesan jika tree belum dibuat
    else {
        deleteTree(root); // menghapus seluruh tree
        cout << "\nPohon berhasil dihapus." << endl;
    }
}

// Fungsi untuk cek ukuran tree
int size(Pohon *node) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!!" << endl; // pesan jika tree belum dibuat
        return 0;
    } else {
        if (!node) {
            return 0; // jika node NULL, return 0
        } else {
            return 1 + size(node->left) + size(node->right); // menghitung ukuran tree
        }
    }
}

// Fungsi untuk cek tinggi (height) tree
int height(Pohon *node) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
        return 0;
    } else {
        if (!node) {
            return 0; // jika node NULL, return 0
        } else {
            int heightKiri = height(node->left); // menghitung tinggi left child
            int heightKanan = height(node->right); // menghitung tinggi right child
            if (heightKiri >= heightKanan) {
                return heightKiri + 1; // mengembalikan tinggi maksimum
            } else {
                return heightKanan + 1; // mengembalikan tinggi maksimum
            }
        }
    }
}

// Fungsi untuk cek jumlah leaf (node tanpa child)
int leafCount(Pohon *node) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
        return 0;
    } else {
        if (!node) {
            return 0; // jika node NULL, return 0
        } else {
            if (!node->left && !node->right) {
                return 1; // jika node tanpa child, return 1
            } else {
                return leafCount(node->left) + leafCount(node->right); // menghitung jumlah leaf pada tree
            }
        }
    }
}

// Fungsi untuk cek jumlah internal node (node dengan minimal 1 child)
int internalCount(Pohon *node) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
        return 0;
    } else {
        if (!node) {
            return 0; // jika node NULL, return 0
        } else {
            if (node->left || node->right) {
                return 1 + internalCount(node->left) + internalCount(node->right); // menghitung jumlah internal node pada tree
            } else {
                return 0; // jika node tanpa child, return 0
            }
        }
    }
}

// Fungsi untuk mengubah data pada node tree
void changeData(Pohon *node, int newData) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
    } else {
        node->data = newData; // mengubah data pada node tree
        cout << "\nData pada node " << node->data << " berhasil diubah menjadi " << newData << "." << endl;
    }
}

// Fungsi untuk menghitung jarak dari node root ke node lain
int distance(Pohon *node, int key) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
        return -1;
    } else {
        if (node == NULL) {
            return -1; // jika node tidak ditemukan, return -1
        } else {
            if (node->data == key) {
                return 0; // jika node ditemukan, return 0
            } else {
                int distLeft = distance(node->left, key); // menghitung jarak pada left child
                int distRight = distance(node->right, key); // menghitung jarak pada right child
                if (distLeft == -1 && distRight == -1) {
                    return -1; // jika node tidak ditemukan, return -1
                } else if (distLeft != -1) {
                    return 1 + distLeft; // mengembalikan jarak dari root ke node yang ditemukan pada left child
                } else {
                    return 1 + distRight; // mengembalikan jarak dari root ke node yang ditemukan pada right child
                }
            }
        }
    }
}

// Fungsi untuk mencari node berdasarkan key
Pohon *find(Pohon *node, int key) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!" << endl; // pesan jika tree belum dibuat
        return NULL;
    } else {
        if (node == NULL) {
            return NULL; // jika node tidak ditemukan, return NULL
        } else {
            if (node->data == key) {
                return node; // jika node ditemukan, return node tersebut
            } else {
                Pohon *leftChild = find(node->left, key); // mencari node pada left child
               Pohon *rightChild = find(node->right, key); // mencari node pada right child
                if (leftChild != NULL) {
                    return leftChild; // jika node ditemukan pada left child, return node tersebut
                } else {
                    return rightChild; // jika node ditemukan pada right child, return node tersebut
                }
            }
        }
    }
}

// Fungsi untuk menampilkan node child dari node yang diinputkan
void showChild(Pohon *node) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!" << endl;
    } else {
        if (!node) {
            cout << "\nNode yang ditunjuk tidak ada!" << endl;
        } else {
            cout << "\nNode " << node->data << " : ";
            if (node->left) {
                cout << "Child Kiri : " << node->left->data << " ";
            } else {
                cout << "Child Kiri : (tidak punya Child kiri) ";
            }
            if (node->right) {
                cout << "Child Kanan : " << node->right->data << " ";
            } else {
                cout << "Child Kanan : (tidak punya Child kanan) ";
            }
            cout << endl;
        }
    }
}

// Fungsi untuk menampilkan semua descendant dari node yang diinputkan
void showDescendants(Pohon *node) {
    if (isEmpty()) {
        cout << "\nBuat tree terlebih dahulu!" << endl;
    } else {
        if (!node) {
            cout << "\nNode yang ditunjuk tidak ada!" << endl;
        } else {
            cout << "\nDescendants of Node " << node->data << " : ";
            if (node->left) {
                showDescendants(node->left); // menampilkan descendant pada left child
            }
            if (node->right) {
                showDescendants(node->right); // menampilkan descendant pada right child
            }
            cout << node->data << " "; // menampilkan node yang sedang diproses
        }
    }
}

void menu() {
    int wahyu_2311102178;
    char data, parentData;
    Pohon *parentNode = NULL;

    do {
        cout << "\nMenu:\n";
        cout << "1. Buat Node Root\n";
        cout << "2. Tambahkan Node ke Child Kiri\n";
        cout << "3. Tambahkan Node ke Child Kanan\n";
        cout << "4. Update Data Node\n";
        cout << "5. Retrieve Data Node\n";
        cout << "6. Find Node\n";
        cout << "7. PreOrder Traversal\n";
        cout << "8. InOrder Traversal\n";
        cout << "9. PostOrder Traversal\n";
        cout << "10. Hapus Subtree\n";
        cout << "11. Hapus Tree\n";
        cout << "12. Tampilkan Karakteristik Tree\n";
        cout << "13. Tampilkan Node Child\n";
        cout << "14. Tampilkan Descendant\n";
        cout << "15. Keluar\n";
        cout << "Pilihan: ";
        cin >> wahyu_2311102178;

        switch (wahyu_2311102178) {
            case 1:
                cout << "Masukkan data root: ";
                cin >> data;
                buatNode(data);
                break;
            case 2:
                cout << "Masukkan data parent: ";
                cin >> parentData;
                cout << "Masukkan data node: ";
                cin >> data;
                parentNode = find(root, parentData);
                if (parentNode) {
                    insertLeft(data, parentNode);
                } else {
                    cout << "Parent node tidak ditemukan!" << endl;
              }
                break;
            case 3:
                cout << "Masukkan data parent: ";
                cin >> parentData;
                cout << "Masukkan data node: ";
                cin >> data;
                parentNode = find(root, parentData);
                if (parentNode) {
                    insertRight(data, parentNode);
                } else {
                    cout << "Parent node tidak ditemukan!" << endl;
                }
                break;
            case 4:
                cout << "Masukkan data node yang ingin diupdate: ";
                cin >> data;
                cout << "Masukkan data baru: ";
                cin >> parentData;
                parentNode = find(root, data);
                if (parentNode) {
                    update(parentData, parentNode);
                } else {
                    cout << "Node tidak ditemukan!" << endl;
                }
                break;
            case 5:
                cout << "Masukkan data node yang ingin di-retrieve: ";
                cin >> data;
                parentNode = find(root, data);
                retrieve(parentNode);
                break;
            case 6:
                cout << "Masukkan data node yang ingin ditemukan: ";
                cin >> data;
                parentNode = find(root, data);
                find(parentNode);
                break;
            case 7:
                cout << "PreOrder Traversal: ";
                preOrder(root);
                cout << "\n";
                break;
            case 8:
                cout << "InOrder Traversal: ";
                inOrder(root);
                cout << "\n";
                break;
            case 9:
                cout << "PostOrder Traversal: ";
                postOrder(root);
                cout << "\n";
                break;
            case 10:
                cout << "Masukkan data node yang ingin dihapus subtreenya: ";
                cin >> data;
                parentNode = find(root, data);
                deleteSub(parentNode);
                break;
            case 11:
                clear();
                break;
            case 12:
                cout << "Ukuran Tree: " << size(root) << endl;
                cout << "Tinggi Tree: " << height(root) << endl;
                cout << "Jumlah Leaf: " << leafCount(root) << endl;
                cout << "Jumlah Internal Node: " << internalCount(root) << endl;
                break;
            case 13:
                cout << "Masukkan data node yang ingin ditampilkan child-nya: ";
                cin >> data;
                parentNode = find(root, data);
                showChild(parentNode);
                break;
            case 14:
                cout << "Masukkan data node yang ingin ditampilkan descendant-nya: ";
                cin >> data;
                parentNode = find(root, data);
                showDescendants(parentNode);
                cout << endl;
                break;
            case 15:
                cout << "Keluar dari program.\n";
                break;
            default:
                cout << "Pilihan tidak valid.\n";
        }
    } while (wahyu_2311102178 != 15);
}

int main() {
    init(); // inisialisasi tree
    menu(); // menampilkan menu
    return 0;
}


```
#### Output:
![Screenshot 2024-05-29 115711](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/a5c6d729-8470-4ef6-9cda-6584ce59a72c)

- Dalam program Binary Tree, fungsi untuk menampilkan semua descendant dari node yang diinputkan dapat dilakukan dengan menggunakan traversal level order (BFS) pada subtree dari node yang diinputkan.

- Dalam versi awal dari program, menggunakan queue untuk melakukan traversal level order. Namun, dapat menggunakan rekursi untuk melakukan traversal level order tanpa menggunakan queue.

- Dalam rekursi, melakukan traversal level order dengan memanggil fungsi rekursif pada setiap node pada level yang sedang diproses. Setiap node pada level yang sedang diproses akan dipanggil fungsi rekursif untuk melakukan traversal level order pada subtree dari node tersebut.

- Dengan menggunakan rekursi, dapat menghapus queue dari program dan membuat program lebih efisien. Selain itu, dapat menghapus fungsi enqueue dan dequeue yang tidak diperlukan lagi.

- Dalam program yang diperbaiki, menggunakan rekursi untuk melakukan traversal level order pada subtree dari node yang diinputkan.
#### Full code Screenshot:
![Screenshot 2024-05-29 115735](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/ce0610be-03a0-4fb2-a008-7d0ce197945c)

## Kesimpulan
- #### A. Graf

- Graf adalah struktur data yang terdiri dari kumpulan node (vertex) dan sisi (edge) yang menghubungkan node-node tersebut.
- Graf dapat digunakan untuk merepresentasikan hubungan antara objek-objek tertentu dalam berbagai bidang.
- Elemen-elemen dalam graf: node (vertex), sisi (edge), adjacency, degree, path, cycle.
- Jenis-jenis graf: graph berarah (directed graph), graph tak berarah (undirected graph), graph berbobot (weighted graph), graph tidak berbobot (unweighted graph), graph terhubung (connected graph), graph lengkap (complete graph), graph planar, graph bipartit.

#### 1. Representasi Graf

- Representasi graf dengan matriks
- Representasi graf dengan linked list

- ####  B. Tree (Pohon)

- Definisi tree: struktur data non-linear yang terdiri dari simpul-simpul (nodes) yang terhubung secara hierarkis.
- Operasi pada tree: create, clear, isEmpty, insert, find, update, retrieve, delete sub, characteristic, traverse.
- Jenis-jenis tree: binary tree, binary search tree (BST), balanced binary tree, N-ary tree, trie (prefiks tree).
- Aplikasi tree: pengindeksan file sistem, kompresi data, pengambilan keputusan, dan banyak lagi.

#### 1. Operasi pada Tree

- Traversal (pelacakan): preorder, inorder, postorder
- Insertion (penyisipan): menambahkan simpul baru ke dalam tree
- Deletion (penghapusan): menghapus simpul dari tree
- Searching (pencarian): menemukan simpul tertentu dalam tree

- #### C. Kode Program

- Kode program untuk menampilkan graf yang merepresentasikan koneksi antar simpul (kota) beserta bobotnya (misalnya jarak atau biaya).
- Kode program untuk implementasi struktur data pohon biner yang menyediakan berbagai operasi untuk manipulasi pohon biner.
- Kode program untuk menampilkan matriks adjacency graf.
  
## Referensi
[1] Yadav, P., & Gupta, R. (2019). A Journey of Graph Algorithms: From Historical to Modern. International Journal of Computer Sciences and Engineering, 7(3), 1038-1047. 

[2] Chakraborty, D., Narayanam, R., & Kalyanaraman, S. (2020). Graph Analytics for Temporal Networks. Proceedings of the VLDB Endowment, 13(12), 3640-3643. 

[3] Hajebi, K., Abbasi-Yadkori, Y., Shahbazi, H., & Zhang, H. (2019). Fast Approximate Nearest-Neighbor Search with k-Nearest Neighbor Graph. Proceedings of the 28th International Joint Conference on Artificial Intelligence, 2184-2191. 

[4] Bondy, J. A., & Murty, U. S. R. (2008). Graph Theory with Applications. Macmillan.

[5] Skiena, S. (2008). The Algorithm Design Manual. Springer Science & Business Media.

[6] Asisten Praktikum, “Modul 9 Graph dan Tree", Googgle Classroom, 2024.

[7] Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2022). Introduction to algorithms. MIT press.

[8] Leis, V., Kemper, A., & Neumann, T. (2019). Trie-Scan: A hybrid trie-cuckoo algorithm for processing ad-hoc trie queries on modern CPUs. Information Systems, 82, 181-200.

[9] Sadecki, J., & Kozłowski, J. (2021). Parallel path finding on trees with GPU. Parallel Computing, 104, 102700.
