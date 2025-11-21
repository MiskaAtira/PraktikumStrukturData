#  Penjelasan

## Linked List
Linked List itu adalah struktur data yang menyimpan data dalam bentuk rangkaian node yang saling terhubung. Setiap node berisi dua hal: data dan pointer/referensi yang menunjuk ke node berikutnya. Jadi, bentuknya seperti rantai yang tersusun dari banyak mata rantai.

## 1. Class Node
Fungsi ini dipakai untuk membuat satu elemen dalam linked list. Di dalam node ada dua bagian: data yang ingin disimpan dan penunjuk (next) yang mengarah ke node berikutnya. Jadi Node itu seperti “kotak” yang menyimpan data dan arah kemana harus lanjut.
```python
class Node:
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer
```

* Node adalah elemen tunggal dalam Linked List.
* `data` menyimpan isi data (misalnya: “apel”).
* `next` adalah pointer yang menunjuk ke node berikutnya.

Contoh bentuk node:
`[ data | next → ]`

## 2. Class LinkedList
Fungsi ini menambahkan data baru di bagian paling depan. Data baru akan menjadi head yang baru, sedangkan data yang sebelumnya di depan akan bergeser ke belakang. Caranya cukup mengubah arah pointer saja.
```python
class LinkedList:
    def __init__(self):
        self.head = None
```
* `head` adalah node pertama dalam linked list.
* Awalnya kosong (`None`).

## 3. insert_at_first(self, data) — Insert di awal 
Fungsi `insert_at_first` digunakan untuk menambahkan elemen baru pada posisi paling awal dari linked list. Proses ini dilakukan dengan membuat node baru yang next-nya langsung menunjuk ke head lama. Setelah itu, head dipindah ke node yang baru dibuat.
* Membuat node baru.
* `next`-nya diarahkan ke head lama.
* Head pindah ke node yang baru → data masuk paling depan.

```python
def insert_at_first(self, data):
    node = Node(data, self.head)
    self.head = node
```

## 4. insert_at_last(self, data) — Insert di akhir
Fungsi `insert_at_last` digunakan untuk menambahkan elemen di bagian akhir linked list. Jika linked list masih kosong, node baru langsung dijadikan head.
* Kalau list kosong → data jadi head.
* Kalau ada isinya → berjalan dari head sampai node terakhir.
* Node terakhir disambungkan dengan node baru.
```python
def insert_at_last(self, data):
    if self.head is None:
        self.head = Node(data)
    else:
        node_sekarang = self.head
        while node_sekarang.next:
            node_sekarang = node_sekarang.next
        node = Node(data)
        node_sekarang.next = node
```

## 5. insert_at(self, index, data)— Insert di posisi tertentu
Fungsi insert_at digunakan untuk menambahkan data pada posisi tertentu dalam linked list berdasarkan indeks.
* Kalau index di luar batas → invalid.
* Kalau index 0 → masuk di depan.
* Kalau index lain:

  * Traverse sampai node sebelum posisi yang diinginkan.
  * Selipkan node baru di sana.

```python
def insert_at(self, index, data):
    if index < 0 or index > self.length() - 1:
        print("index tidak valid")
    elif index == 0:
        self.insert_at_first(data)
    else:
        urutan = 0
        node_sekarang = self.head
        while urutan < index - 1:
            urutan += 1
            node_sekarang = node_sekarang.next
        node = Node(data, node_sekarang.next)
        node_sekarang.next = node
```

## 6. remove_first(self) — Hapus elemen pertama
Fungsi remove_first digunakan untuk menghapus node pertama dalam linked list. Jika list kosong, fungsi akan menampilkan pesan bahwa tidak ada data yang bisa dihapus. Jika list berisi elemen, head akan dipindahkan ke node berikutnya, sehingga node pertama secara otomatis tidak lagi terhubung dengan list dan dianggap terhapus
* Kalau kosong → tidak ada yang dihapus.
* Kalau ada → head pindah ke node berikutnya.
* Node lama otomatis terlepas.
```python
def remove_first(self):
    if self.head is None:
        print("tidak ada data yang bisa dihapus")
    else:
        self.head = self.head.next
```

## 7. remove_last(self) — Hapus elemen paling akhir
Fungsi ini menghapus data paling belakang. Kalau list kosong atau hanya ada satu data, itu ditangani langsung. Kalau datanya banyak, fungsi ini berjalan dari awal sampai node terakhir.
```python
def remove_last(self):
    if self.head is None:
        print("tidak ada data yang bisa dihapus")
    elif self.head.next is None:
        self.head = None
    else:
        node_sebelumnya = None
        node_sekarang = self.head
        while node_sekarang.next:
            node_sebelumnya = node_sekarang
            node_sekarang = node_sekarang.next
        node_sebelumnya.next = None
```
* Kasus 1: List kosong → tidak bisa hapus.
* Kasus 2: Isi cuma satu node → habis jadi kosong.
* Kasus 3: Isi banyak → jalan sampai node terakhir.

## 8. remove_at(self, index) — Hapus di posisi tertentu
Fungsi ini menghapus data pada posisi tertentu sesuai index. Jika index 0, maka data pertama dihapus. Untuk index lain, fungsi mencari node sebelum posisi yang ingin dihapus lalu memutuskan sambungan agar node target terlepas dari list.
```python
def remove_at(self, index):
    if index < 0 or index >= self.length():
        print("index invalid")
    elif index == 0:
        self.remove_first()
    else:
        urutan = 0
        node_sekarang = self.head
        while urutan < index - 1:
            node_sekarang = node_sekarang.next
            urutan += 1
        node_sekarang.next = node_sekarang.next.next
```

* Validasi index.
* Kalau index 0 → hapus depan.

## 9. print(self) — Menampilkan semua data
Fungsi ini menampilkan seluruh isi linked list dari depan sampai belakang. Jika list kosong, ditampilkan pesan “data kosong”. Kalau ada isi, data ditampilkan satu per satu dengan tanda panah “→”.
```python
def print(self):
    if self.head is None:
        print("data kosong")
    else:
        text_print = ''
        node_sekarang = self.head
        while node_sekarang:
            text_print += str(node_sekarang.data) + " → "
            node_sekarang = node_sekarang.next
        print(text_print)
```

* Kalau list kosong → tampilkan pesan.
* Kalau ada isi →

  * Ambil data per node dari head ke akhir.
  * Digabung jadi satu string.
  * Tampilkan seperti:
    `mangga → jeruk → apel →`

---

## 10. length(self) — Menghitung jumlah node
Fungsi ini menghitung jumlah data dalam linked list. Caranya dengan berjalan dari head sampai node terakhir sambil menghitung jumlah langkahnya.
* Mulai dari head.
* Hitung satu per satu node hingga `None`.
* Return total jumlah node.
```python
def length(self):
    urutan = 0
    data_sekarang = self.head
    while data_sekarang:
        data_sekarang = data_sekarang.next
        urutan += 1
    return urutan
```

## 11. Bagian penggunaan
Bagian penggunaan ini menunjukkan seluruh proses kerja Linked List:
mulai dari list kosong, menambah data di awal, menambah data di akhir, menyisipkan data di tengah, menghapus beberapa data, mengecek jumlah data dan menampilkan hasil akhirnya.
Akhirnya hanya tersisa satu elemen, yaitu “mangga”.

```python
LL = LinkedList()

LL.insert_at_first("jeruk")
LL.insert_at_first("mangga")
LL.insert_at_first("manggis")
LL.insert_at_last("apel")
LL.insert_at(2, "anggur")

LL.remove_first()
LL.remove_last()
LL.remove_at(1)
LL.remove_at(1)

LL.print()
print(LL.length())
```

Ini bagian yang menjalankan semua fungsi di atas.

## 12. Hasil Run

```python
mangga →
1
```



