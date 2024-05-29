![Screenshot 2024-05-29 090113](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/0b42dc21-232a-4ef1-8e1a-d617e3e2b87a)![Screenshot 2024-05-29 085946](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/03794d12-8d70-406f-9f8e-dfd61f9120f7)![image](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/d0f3d6e1-ac7c-41f2-a3a1-1dd55bde30aa)<p align="center">Wahyu Hidayat</p>
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
![Screenshot 2024-05-29 092033](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/5a2894b8-60ed-4271-9bf6-5efdb3419910)



Kode ini merupakan implementasi dari struktur data pohon biner yang menyediakan berbagai operasi untuk manipulasi pohon biner. Pada awalnya, pohon diinisialisasi dengan pointer global `root` yang menunjuk ke `NULL`. Program ini mencakup fungsi-fungsi untuk mengecek apakah pohon kosong (`isEmpty`), membuat node baru (`newPohon`), menambahkan node ke pohon sebagai root (`buatNode`), dan menambahkan node sebagai anak kiri (`insertLeft`) atau anak kanan (`insertRight`). Selain itu, terdapat fungsi untuk mengubah data pada node (`update`), mengambil data dari node (`retrieve`), dan menemukan serta menampilkan informasi tentang node tertentu (`find`).

Penelusuran pohon dapat dilakukan dengan tiga cara: pre-order (`preOrder`), in-order (`inOrder`), dan post-order (`postOrder`). Program ini juga menyediakan fungsi untuk menghapus node dari pohon (`deleteTree`), menghapus subtree dari node tertentu (`deleteSub`), serta menghapus seluruh pohon (`clear`). Selain itu, terdapat fungsi untuk menghitung ukuran (`size`) dan tinggi (`height`) pohon, serta menampilkan karakteristik pohon seperti ukuran, tinggi, dan rata-rata node per level (`characteristic`).

Dalam fungsi `main`, pohon diinisialisasi dan beberapa node ditambahkan untuk membentuk struktur pohon biner. Beberapa operasi dilakukan termasuk pengubahan data pada node, penelusuran pohon, serta penghapusan subtree, yang diikuti dengan menampilkan kembali penelusuran pohon dan karakteristik pohon setelah perubahan. Program ini menampilkan hasil dari setiap operasi pada pohon biner untuk membantu pengguna memahami perubahan yang terjadi pada struktur pohon.

#### Full code Screenshot:
![Screenshot 2024-05-29 091955](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/267a3dce-73c7-42cf-a845-0f5242a47234)



## Unguided 

#### 1. Buatlah sebuah program untuk mencari sebuah huruf pada sebuah kalimat yangsudah di input dengan menggunakan Binary Search!

```C++
#include <iostream>
#include <string>
#include <algorithm>
using namespace std;

// Fungsi untuk mengurutkan array karakter menggunakan selection sort
void selection_sort(char arr[], int n) {
    int min;
    char temp;
    for (int i = 0; i < n - 1; i++) {
        min = i;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[min]) {
                min = j;
            }
        }
        // Tukar elemen
        temp = arr[i];
        arr[i] = arr[min];
        arr[min] = temp;
    }
}

// Fungsi untuk melakukan pencarian biner pada array karakter yang sudah diurutkan
void binary_search(char arr[], int n, char target) {
    int awal = 0, akhir = n - 1, tengah;
    bool found = false;
    
    while (awal <= akhir) {
        tengah = (awal + akhir) / 2;
        if (arr[tengah] == target) {
            found = true;
            break;
        } else if (arr[tengah] < target) {
            awal = tengah + 1;
        } else {
            akhir = tengah - 1;
        }
    }

    if (found) {
        cout << "Huruf '" << target << "' ditemukan pada indeks ke-" << tengah << endl;
    } else {
        cout << "Huruf '" << target << "' tidak ditemukan dalam kalimat." << endl;
    }
}

int main() {
    string kalimat;
    char cari;

    // Meminta pengguna untuk memasukkan sebuah kalimat
    cout << "Masukkan sebuah kalimat: ";
    getline(cin, kalimat);

    // Meminta pengguna untuk memasukkan huruf yang ingin dicari
    cout << "Masukkan huruf yang ingin Anda cari: ";
    cin >> cari;

    // Mengonversi string menjadi array karakter
    int panjang = kalimat.length();
    char arr[panjang];
    for (int i = 0; i < panjang; i++) {
        arr[i] = kalimat[i];
    }

    // Mengurutkan array karakter
    selection_sort(arr, panjang);

    // Menampilkan kalimat setelah diurutkan
    cout << "Kalimat setelah diurutkan: ";
    for (int i = 0; i < panjang; i++) {
        cout << arr[i];
    }
    cout << endl;

    // Melakukan binary search
    binary_search(arr, panjang, cari);

    return 0;
}



```
#### Output:
![Screenshot 2024-05-22 145134](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/adfa9e1d-c5e1-45a8-ad69-3a215f12d142)


- Kode diatas menggunakan algoritma pengurutan Selection Sort untuk mengurutkan karakter-karakter dalam kalimat dan algoritma pencarian Binary Search untuk mencari huruf yang diinginkan.

- Fungsi selection_sort digunakan untuk mengurutkan array karakter menggunakan algoritma Selection Sort. Dalam algoritma ini, setiap iterasi, elemen terkecil dari sisa array dipilih dan ditukar dengan elemen saat ini. Ini dilakukan hingga seluruh array terurut.

- Setelah pengurutan, fungsi binary_search dipanggil untuk melakukan pencarian biner pada array karakter yang sudah diurutkan. Dalam pencarian biner, array dibagi menjadi dua bagian setiap iterasi dan pencarian dilanjutkan pada bagian yang relevan tergantung pada relasi antara elemen tengah dan target. Jika elemen ditemukan, pesan yang sesuai ditampilkan; jika tidak, pesan bahwa huruf tidak ditemukan dicetak.

- Di dalam main, pengguna diminta untuk memasukkan sebuah kalimat dan huruf yang ingin dicari. Kalimat yang dimasukkan dikonversi menjadi array karakter, kemudian diurutkan menggunakan selection_sort. Setelah pengurutan, kalimat yang sudah diurutkan ditampilkan, dan fungsi binary_search dipanggil untuk mencari huruf yang diinginkan dalam kalimat yang sudah diurutkan. 
  
#### Full code Screenshot:
![Screenshot 2024-05-22 145149](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/47f18ccc-30e4-42e1-9f4e-7961232e2654)



#### 2. Buatlah sebuah program yang dapat menghitung banyaknya huruf vocal dalam sebuah kalimat!

```C++
#include <iostream>
#include <string>
#include <cctype> // Untuk menggunakan fungsi isalpha dan tolower
#include <vector>

using namespace std;

// Fungsi untuk menghitung jumlah huruf vokal dalam sebuah kalimat
int hitungVokal(const string& kalimat, vector<int>& indeks) {
    int jumlahVokal = 0;
    // Membuat string yang berisi huruf vokal
    string vokal = "aeiouAEIOU";
    
    // Iterasi melalui setiap karakter dalam kalimat
    for (int i = 0; i < kalimat.length(); ++i) {
        char karakter = kalimat[i];
        // Jika karakter adalah huruf dan huruf tersebut adalah huruf vokal
        if (isalpha(karakter) && vokal.find(karakter) != string::npos) {
            jumlahVokal++;
            indeks.push_back(i);
        }
    }
    return jumlahVokal;
}

int main() {
    string kalimat;
    vector<int> indeksHurufVokal;

    // Meminta pengguna untuk memasukkan kalimat
    cout << "Masukkan sebuah kalimat: ";
    getline(cin, kalimat);

    // Menghitung jumlah huruf vokal dalam kalimat
    int jumlahVokal = hitungVokal(kalimat, indeksHurufVokal);

    // Menampilkan jumlah huruf vokal
    cout << "Jumlah huruf vokal dalam kalimat adalah: " << jumlahVokal << endl;

    // Menampilkan indeks huruf vokal
    cout << "Indeks huruf vokal dalam kalimat adalah: ";
    for (int i = 0; i < indeksHurufVokal.size(); ++i) {
        cout << indeksHurufVokal[i];
        if (i < indeksHurufVokal.size() - 1) {
            cout << ", ";
        }
    }
    cout << endl;

    return 0;
}



```
#### Output:
![Screenshot 2024-05-22 150137](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/0ac9bef0-b33f-4245-bcb0-afabb82fa959)

- Kode diatas menggunakan fungsi getline(cin, kalimat). Kalimat ini akan disimpan dalam variabel kalimat yang merupakan objek dari tipe data string.

- Selanjutnya, program memanggil fungsi hitungVokal untuk menghitung jumlah huruf vokal dalam kalimat tersebut. Fungsi ini menerima dua parameter, yaitu kalimat yang ingin dihitung dan vektor indeksHurufVokal untuk menyimpan indeks di mana huruf vokal ditemukan.

- Dalam fungsi hitungVokal, program melakukan iterasi melalui setiap karakter dalam kalimat menggunakan loop for. Pada setiap iterasi, program memeriksa apakah karakter tersebut adalah huruf dan apakah karakter tersebut termasuk dalam daftar huruf vokal (aeiouAEIOU). Jika ya, maka jumlah huruf vokal akan bertambah satu dan indeks karakter tersebut akan dimasukkan ke dalam vektor indeksHurufVokal.

- Setelah selesai melakukan iterasi, program akan mengembalikan jumlah huruf vokal yang telah dihitung.

- Setelah itu, program akan menampilkan jumlah huruf vokal yang telah dihitung dan juga indeks dari huruf vokal tersebut dalam kalimat. Program menggunakan loop for untuk mencetak setiap indeks yang disimpan dalam vektor indeksHurufVokal, dan menyertakan tanda koma untuk memisahkan antara indeks.

#### Full code Screenshot:
![Screenshot 2024-05-22 150151](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/9b4a6258-89ef-4d8e-afe1-c4681e0d89fe)

#### 3. Diketahui data = 9, 4, 1, 4, 7, 10, 5, 4, 12, 4. Hitunglah berapa banyak angka 4 dengan menggunakan algoritma Sequential Search!
```C++
#include <iostream>
#include <vector>

using namespace std;

// Fungsi untuk melakukan Sequential Search
int sequentialSearch(const vector<int>& data, int target) {
    int count = 0;
    // Iterasi melalui setiap elemen dalam data
    for (int num : data) {
        // Jika elemen sama dengan target, tambahkan 1 ke count
        if (num == target) {
            count++;
        }
    }
    return count;
}

int main() {
    vector<int> data = {9, 4, 1, 4, 7, 10, 5, 4, 12, 4};
    int target = 4;
    
    // Menghitung jumlah angka 4 dalam data menggunakan Sequential Search
    int jumlah_angka_4 = sequentialSearch(data, target);

    // Menampilkan hasil
    cout << "Jumlah angka 4 dalam data adalah: " << jumlah_angka_4 << endl;

    return 0;
}



```
#### Output:
![Screenshot 2024-05-22 150921](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/ecb83c0b-07c8-4605-823c-83f6fd81b1e8)

- Kode diatas menggunakan algoritma Sequential Search untuk menghitung berapa banyak angka 4 dalam data yang diberikan. Pertama-tama, fungsi sequentialSearch didefinisikan untuk menerima dua parameter: data, yang merupakan vektor dari integer, dan target, yang merupakan angka yang ingin dicari. Di dalam fungsi ini, variabel count diinisialisasi dengan nilai 0 yang akan digunakan untuk menghitung berapa banyak angka target yang ditemukan dalam data. Selanjutnya, dilakukan iterasi melalui setiap elemen dalam data menggunakan loop for. Pada setiap iterasi, dilakukan pengecekan apakah elemen tersebut sama dengan target. Jika ya, maka 1 ditambahkan ke count. Setelah selesai melakukan iterasi, nilai count yang merupakan jumlah kemunculan angka target dalam data dikembalikan.

- Di dalam fungsi main, data yang merupakan vektor dari angka yang diberikan dan target yang merupakan angka yang ingin dicari, didefinisikan. Selanjutnya, fungsi sequentialSearch dipanggil dengan data dan target sebagai argumennya, dan hasilnya disimpan dalam variabel jumlah_angka_4. Terakhir, jumlah angka 4 yang ditemukan dalam data dicetak. Dengan menggunakan algoritma Sequential Search ini, program ini memberikan cara sederhana untuk menghitung berapa banyak angka 4 dalam data yang diberikan.
  
#### Full code Screenshot:
![Screenshot 2024-05-22 150938](https://github.com/Wahyu101101/Struktur-Data-Assigment/assets/161663486/4a2b2a96-5633-4f00-a984-f3b07aecd7c3)


## Kesimpulan
- A. Algoritma pencarian adalah serangkaian langkah sistematis yang digunakan untuk menemukan elemen tertentu dalam sekumpulan data atau struktur data.
- B. Tujuan utama dari algoritma pencarian adalah untuk menemukan lokasi atau indeks dari elemen yang dicari dalam waktu yang efisien.
- C. Algoritma pencarian sangat penting dalam berbagai bidang, seperti pengolahan data, struktur data, dan pemrograman komputer.
- D. Terdapat beberapa algoritma pencarian yang umum digunakan, antara lain Sequential Search, Binary Search, Linear Search, dan Hash Table.
- Sequential Search adalah algoritma pencarian sederhana yang digunakan untuk data yang belum terurut.
- Binary Search adalah algoritma pencarian efisien yang digunakan pada kumpulan data yang telah diurutkan.
- Linear Search adalah algoritma pencarian yang paling sederhana, di mana elemen-elemen dalam kumpulan data diperiksa satu per satu secara berurutan.
- Hash Table adalah struktur data yang menggunakan fungsi hash untuk memetakan kunci ke nilai yang sesuai.
- E. DFS (Depth-First Search) dan BFS (Breadth-First Search) adalah algoritma pencarian yang digunakan dalam struktur data seperti pohon dan graf.
- F. Program C++ dapat mengimplementasikan berbagai algoritma pencarian, seperti Sequential Search, Binary Search, dan sebagainya, untuk menemukan elemen tertentu dalam sebuah array.
- G. Algoritma Sequential Search dan Binary Search dapat digunakan untuk mencari elemen tertentu dalam array dengan kompleksitas waktu yang berbeda.
- H. Implementasi algoritma pencarian dan pengurutan dalam program C++ memungkinkan penyelesaian tugas-tugas komputasi yang melibatkan manipulasi data dengan efisien.
  
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
