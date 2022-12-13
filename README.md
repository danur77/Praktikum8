# lab ke-8

Nama : Danang Nurcahyo

NIM : 312210004

Kelas : TI.22.A.1

## DAFTAR ISI <br>
| No | Description | Link |
|-----|------|-----|
|1|Tugas Praktikum 8|[Click Here](#Tugas-Praktikum-8)|
|2|Praktikum 8|[Click Here](#Praktikum-8)|
|3|Diagram Class Praktikum 8|[Click Here](#Diagram-Class-Praktikum-8)|
|4|Flowchart Praktikum 8|[Click Here](#flowchart-praktikum-8)|


## Tugas Praktikum 8
Buat program sederhana dengan mengaplikasikan penggunaan class. Buatlah class untuk menampilkan daftar nilai mahasiswa, dengan ketentuan:

- Method tambah() untuk menambah data
- Method tampilkan() untuk menampilkan data
- Method hapus(nama) untuk menghapus data berdasarkan nama
- Method ubah(nama) untuk mengubah data berdasarkan nama
- Buat diagram class, flowchart dan penjelasan programnya pada README.md.
- Commit dan push repository ke github.

## Praktikum 8

### Rumus :

class mahasiswa:
    def __init__(self, nama, nim, tugas, uts, uas):
        self.nama = nama
        self.nim= nim
        self.tugas = tugas
        self.uts = uts
        self.uas = uas
    def tambah(self,nama,nim,tugas,uts,uas):
        data.nama.append(nama)
        data.nim.append(nim)
        data.tugas.append(tugas)
        data.uts.append(uts)
        data.uas.append(uas)

    def lihat(self):
        for i in range(len(data.nama)):
            print("|", i+1, "  |", end="")
            print('{0:<25}'.format(self.nama[i]), end="")
            print("|", self.nim[i], end="")
            print(" |", self.tugas[i], end="")
            print("    |", self.uts[i], end="")
            print("  |", self.uas[i], " | ", end="")
            print(f'{((self.tugas[i]*30/100) + (self.uts[i]*35/100) + (self.uas[i]*35/100)) :.2f}', " |")

    def ubah(self,nama,nim,tugas,uts,uas):
        self.nama[no] = nama
        self.nim[no] = nim
        self.tugas[no] = tugas
        self.uts[no] = uts
        self.uas[no] = uas

    def hapus(self):
        del self.nama[no]
        del self.nim[no]
        del self.tugas[no]
        del self.uts[no]
        del self.uas[no]

data = mahasiswa([],[],[],[],[])

while True:
    menu = input("\n[(L)ihat, (T)ambah, (U)bah, (H)apus, (K)eluar]:")
    if menu == "t" or menu == "T":
       print("\nTambah Data")
       data.tambah(
           input("Masukkan Nama : "),
           input("Masukkan Nim : "),
           int(input("Nilai Tugas : ")),
           int(input("Nilai UTS : ")),
           int(input("Nilai UAS : "))
           )
       print("\nData berhasil ditambahkan")

    elif menu == "l" or menu == "L":
        print("\nDaftar Nilai")
        print("==========================================================================")
        print("| No  |          Nama           |    NIM    | TUGAS | UTS | UAS |  AKHIR |")
        print("==========================================================================")
        if len(data.nama) != 0:
            data.lihat()
        else:
            print("                         TIDAK ADA DATA                               ")
        print("==========================================================================")

    elif menu == "u" or menu == "U":
        print("\nUbah Data")
        ubah = input("Masukkan Nama : ")
        if ubah in data.nama:
           no = data.nama.index(ubah)
           print("Masukkan Data Yang Baru : ")
           data.ubah(
               input("Nama : "),
               input("Nim : "),
               int(input("Nilai Tugas : ")),
               int(input("Nilai UTS : ")),
               int(input("Nilai UAS : "))
               )
        else:
            print(ubah, "tidak ada di dalam data")

    elif menu == "h" or menu == "H":
        print("\nHapus Data")
        hapus = input("Masukkan Nama : ")
        if hapus in data.nama:
            no = data.nama.index(hapus)
            data.hapus()
            print("Data", hapus, "Berhasil dihapus")
        else:
            print(hapus, "tidak ada di dalam data")

    elif menu == "k" or menu == "K":
        print("\nTerimakasih\n")
        break

    else:
        print("\nPerintah yang dimasukkan salah!\n")
            
## Program :

![Screenshot 2022-12-13 183746](https://user-images.githubusercontent.com/115677839/207318429-0a5eb369-6009-4cff-b269-29b38bcdd267.png)

![Screenshot 2022-12-13 183828](https://user-images.githubusercontent.com/115677839/207318514-3b1e8558-1ecb-45c9-ab64-d5fc49b0e35c.png)

![Screenshot 2022-12-13 183902](https://user-images.githubusercontent.com/115677839/207318556-6b1dca6b-765b-4b28-96f7-ad0839e9335d.png)

![Screenshot 2022-12-13 183929](https://user-images.githubusercontent.com/115677839/207318606-94a9eb61-5f80-48a2-9dcf-95ae62b8dd8c.png)


## Hasil Run & Penjelasan Program :
- Pertama kita mendeklarasikan sebuah class mahasiswa yang didalamnya terdapat atribut NIM, Nama, nilai tugas, nilai UTS dan nilai UAS. Jangan lupa, untuk mendeklarasikan sebuah class didalam OOP kita harus menggunakan **def__init__ dan juga self.**

      class mahasiswa:
          def __init__(self, nama, nim, tugas, uts, uas):
              self.nama = nama
              self.nim = nim
              self.tugas = tugas
              self.uts = uts
              self.uas = uas

- Seperti biasa, deklarasikan satu dictionary kosong sebagai tempat menyimpan data-data yang sudah kita input. Ada 5 list kosong yang nantinya berisi NIM, Nama, nilai tugas, nilai UTS dan nilai UAS.

      data = mahasiswa([],[],[],[],[])  

- Kita akan buat beberapa method untuk menambahkan, menampilkan, menghapus, mengubah data mahasiswa. Pertama membuat method tambah(), method ini berfungsi untuk menambahkan data. Dalam method ini kita menggunakan append() supaya data yang terakhir ditambahkan ada di urutan list paling akhir.

      def tambah(self,nim,nama,tugas,uts,uas):
              data.nama.append(nama)
              data.nim.append(nim)
              data.tugas.append(tugas)
              data.uts.append(uts)
              data.uas.append(uas)

- Ini tampilan jika kita menginput method : `Tambah()`

![Screenshot 2022-12-13 185732](https://user-images.githubusercontent.com/115677839/207319417-7028f75b-c025-457f-8c29-42286d8310d1.png)


- Fungsi membuat method lihat() yaitu untuk menampilkan seluruh data yang sudah kita tambahkan tadi. Jika tidak ada data sama sekali, maka akan muncul tulisan **TIDAK ADA DATA.**

      def lihat(self):
              for i in range(len(data.nama)):
                  print("|", i+1, "  |", end="")
                  print('{0:<25}'.format(self.nama[i]), end="")
                  print("|", self.nim[i], end="")
                  print(" |", self.tugas[i], end="")
                  print("    |", self.uts[i], end="")
                  print("  |", self.uas[i], " | ", end="")
                  print(f'{((self.tugas[i]*30/100) + (self.uts[i]*35/100) + (self.uas[i]*35/100)) :.2f}', " |")
                  
- Ini tampilan jika kita menginput method : `Lihat()`

![Screenshot 2022-12-13 193814](https://user-images.githubusercontent.com/115677839/207320656-9e854410-572e-4495-8c38-78bfc842c688.png)


- Fungsi membuat method ubah() yaitu untuk mengubah data. jika method ini diinput, maka data Nama, NIM, nilai tugas, nilai UTS, nilai UAS index nomor - (no) akan diubah sesuai dengan inputan dari user. Index ke - (no) akan dicari secara otomatis sesuai dengan nama yang ingin diubah oleh user.

      def ubah(self,nim,nama,tugas,uts,uas):
              self.nama[no] = nama
              self.nim[no] = nim
              self.tugas[no] = tugas
              self.uts[no] = uts
              self.uas[no] = uas
              
- Ini tampilan jika kita menginput method : `Ubah()`
![Screenshot 2022-12-13 185839](https://user-images.githubusercontent.com/115677839/207320727-0e1a3823-61e7-4b3b-9ca3-8d6463c60216.png)


- Terakhir kita membuat method hapus(), yang berfungsi untuk menghapus data berdasarkan nama. Kita bisa menggunakan del untuk menghapus datanya. Seperti sebelumnya, nomor index list yang akan dihapus disesuaikan dengan inputan dari user. Yaitu index nomor ke - (no).

      def hapus(self):
              del self.nama[no]
              del self.nim[no]
              del self.tugas[no]
              del self.uts[no]
              del self.uas[no]
              
- Ini tampilan jika kita menginput method : `Hapus()`

![Screenshot 2022-12-13 190120](https://user-images.githubusercontent.com/115677839/207320771-8700d07f-2be6-49c7-b46a-6c9043501bdb.png)

## Diagram Class Praktikum 8

![Diagram Kelas](https://user-images.githubusercontent.com/115678171/207250890-b0888c56-9f40-48fb-a411-f873e2c2194c.jpg)

## Flowchart Praktikum 8

![Flowchart](https://user-images.githubusercontent.com/115678171/207250962-5e5694c8-4181-4fbb-b5b1-4e246d4f56e4.png)

## Sekian dari saya, Terima kasih
