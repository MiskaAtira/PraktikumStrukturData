# Implementasi Queue di Python

Queue adalah (antrian) atau struktur data berurutan yang bekerja dengan konsep FIFO (First In, First Out), yaitu elemen yang masuk pertama akan keluar lebih dulu. Pada kehidupan nyata, seperti orang yang antre di loket: yang datang duluan dilayani duluan.
Program ini menunjukkan contoh sederhana struktur data Queue (antrian) menggunakan list di Python.  

## Kode Program

```python
queue = []

# Enqueue
queue.append('A')
queue.append('B')
queue.append('C')
print("Queue: ", queue)

# Dequeue
element = queue.pop(0)
print("Dequeue: ", element)

# Peek
frontElement = queue[0]
print("Peek: ", frontElement)

# isEmpty
isEmpty = not bool(queue)
print("isEmpty: ", isEmpty)

# Size
print("Size: ", len(queue))
```

## Penjelasan Kode Program

1. Inisialisasi Queue berfungsi untuk Membuat sebuah list kosong yang akan berfungsi sebagai antrian, Pada tahap awal, queue belum memiliki elemen apa pun sehingga masih kosong:

   ```python
   queue = []
   ```

2. Enqueue (Menambah Data) berfungsi untuk Menambahkan elemen ke dalam antrian ke paling belakang menggunakan `append()` 
   ```python
   queue.append('A')
   queue.append('B')
   queue.append('C')
   ```

   Setelah bagian ini, isi antrian: `['A', 'B', 'C']`.

3. Dequeue (Menghapus Data Terdepan) berfungsi untuk Menghapus elemen pertama atau data terdepan dengan `pop(0)`

   ```python
   element = queue.pop(0)
   ```

   Elemen `'A'` keluar dari antrian.

4. Peek (Melihat Elemen Terdepan): 
   Melihat elemen yang paling depan tanpa menghapus elemen tersebut 

   ```python
   frontElement = queue[0]
   ```

5. isEmpty (Cek Kosong atau Tidak): 
   Mengecek apakah antrian kosong

   ```python
   isEmpty = not bool(queue)
   ```

6. Size (Jumlah Elemen):
   Menghitung banyaknya elemen yang ada didalamnya

   ```python
   len(queue)
   ```

## Hasil Output yang akan keluar

```
Queue:  ['A', 'B', 'C']
Dequeue:  A
Peek:  B
isEmpty:  False
Size:  2
```

## Kesimpulan

Queue memudahkan pengelolaan data yang harus diproses secara berurutan. Dengan aturan FIFO, struktur ini sangat cocok digunakan untuk sistem antrian, pengelolaan tugas, atau proses yang harus mengikuti urutan masuk data. Struktur ini biasanya digunakan untuk sistem antrian
* Operasi dasar:

  * `append()` → menambah data  (enqueue)
  * `pop(0)` → menghapus data paling depan (dequeue)
  * `queue[0]` → melihat data paling depan (peek)
  * `len` untuk menhitung jumlah elemen

--------------------------------------------------------------------------------------------------------------------------


# Implementasi Stack di Python

Contoh program berikut memperlihatkan cara menggunakan struktur data Stack (tumpukan) dengan memanfaatkan list di Python.
Stack (tumpukan) adalah struktur data yang menyimpan elemen secara bertumpuk dan bekerja dengan prinsip LIFO (Last In, First Out), yaitu elemen yang masuk terakhir akan menjadi elemen pertama yang keluar. Struktur ini mirip seperti tumpukan buku: buku yang ditaruh paling atas adalah yang paling mudah diambil terlebih dahulu.

## Kode Program

```python
stack = []

# Push
stack.append('A')
stack.append('B')
stack.append('C')
print("Stack: ", stack)

# Pop
element = stack.pop()
print("Pop: ", element)

# Peek 
topElement = stack[-1]
print("Peek: ", topElement)

# isEmpty
isEmpty = not bool(stack)
print("isEmpty: ", isEmpty)

# Size
print("Size :", len(stack))
```

## Penjelasan

1. Membuat Stack
   Bagian ini membuat list kosong yang akan digunakan sebagai struktur tumpukan:

   ```python
   stack = []
   ```

2. Push (Menambahkan Data)
   Elemen baru dimasukkan ke bagian paling atas tumpukan menggunakan `append()`:

   ```python
   stack.append('A')
   stack.append('B')
   stack.append('C')
   ```

   Setelah proses tersebut, isi stack menjadi: `['A', 'B', 'C']`.

3. Pop (Mengambil Data Teratas)
   Menghapus dan mengambil elemen paling atas dengan `pop()`:

   ```python
   element = stack.pop()
   ```

   Elemen `'C'` yang terakhir dimasukkan adalah yang pertama keluar.

4. Peek (Melihat Data Teratas)
   Mengecek elemen paling atas tanpa menghilangkannya:

   ```python
   topElement = stack[-1]
   ```

5. isEmpty (Memeriksa Kondisi Stack)
   Mengecek apakah tumpukan masih berisi elemen atau tidak:

   ```python
   isEmpty = not bool(stack)
   ```

6. Size (Menghitung Jumlah Elemen)
   Mengetahui berapa banyak elemen yang ada di dalam stack:

   ```python
   len(stack)
   ```

## Output Program

```
Stack:  ['A', 'B', 'C']
Pop:  C
Peek:  B
isEmpty:  False
Size : 2
```

## Kesimpulan

* Stack merupakan struktur data yang bekerja dengan aturan LIFO (Last In First Out), di mana elemen terakhir yang masuk adalah yang lebih dulu dikeluarkan. Stack mempermudah pengelolaan data yang harus diproses secara terbalik dari urutan masuknya. Dengan prinsip LIFO, struktur ini sangat berguna pada fitur seperti undo/redo, penanganan fungsi dalam pemrograman (call stack), dan penyimpanan data sementara yang membutuhkan akses cepat pada elemen paling atas.
* Operasi utama pada stack meliputi:

  * `append()` → menambah data (push)
  * `pop()` → menghapus data teratas (pop)
  * `stack[-1]` → melihat data paling atas (peek)




