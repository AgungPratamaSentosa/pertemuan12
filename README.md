# PERTEMUAN12
# Daftar Nilai Mahasiswa dengan Python OOP

Selamat datang di program Daftar Nilai Mahasiswa menggunakan paradigma Object-Oriented Programming (OOP) di Python! Dengan menggunakan konsep class dan objek, kita dapat mencatat dan mengelola nilai mahasiswa dengan mudah.Python OOP (Object-Oriented Programming) adalah paradigma pemrograman yang menggunakan konsep objek, yang dapat memiliki properti (atribut) dan perilaku (metode). Dalam paradigma OOP, program dibangun dengan memodelkan dunia nyata menggunakan objek dan interaksi antar objek. Beberapa konsep utama dalam Python OOP melibatkan:

## 1. *Class dan Objek:*
<p>Membuat Class</p>

- *Class:* Blueprint atau cetak biru untuk menciptakan objek. Mendefinisikan atribut (variabel) dan metode (fungsi) yang dimiliki oleh objek.
- *Objek:* Instance dari class. Merupakan realisasi konkret dari blueprint class dengan atribut dan metode yang sesuai.

``` python
     class DaftarNilaiMahasiswa:
         def __init__(self):
             self.daftar_nilai = []
```
     

   - *Membuat Instance Class:*
```python
     daftar_nilai_mahasiswa = DaftarNilaiMahasiswa()
```
     

## 2. *Atribut dan Metode:*
<p>Menambahkan Method atau Fungsi</p>

- *Atribut:* Variabel yang digunakan untuk menyimpan data atau informasi di dalam objek.
- *Metode:* Fungsi atau tindakan yang dapat dilakukan oleh objek. Metode biasanya beroperasi pada data yang disimpan dalam objek.

```python
     def tambah(self, nama, nilai):
         # Fungsi untuk menambahkan data mahasiswa
```
     

   - *Mengakses Atribut:*
```python
     print(daftar_nilai_mahasiswa.daftar_nilai)
```
     

## 3. *Enkapsulasi:*
<p>Menambahkan atribut private</p>

- *Enkapsulasi:* Menyembunyikan implementasi detail objek dan hanya mengekspos fungsionalitas yang dibutuhkan. Ini dapat dicapai dengan menggunakan hak akses (access modifiers) seperti private, protected, dan public.

```python
     class DaftarNilaiMahasiswa:
         def __init__(self):
             self.daftar_nilai = []
             self.__atribut_private = "Ini atribut private"
```
     

   - *Menggunakan Getter:*
```python
     print(daftar_nilai_mahasiswa.atribut_private)
```
     

## 4. *Setter dan Getter:*
Setter dan Getter adalah metode yang digunakan untuk mengakses dan mengubah nilai dari atribut private dalam suatu class. Setter digunakan untuk mengubah nilai atribut, sedangkan Getter digunakan untuk mendapatkan nilai atribut.
   - *Menambahkan Property Setter dan Getter:*
```python
     @property
     def atribut_private(self):
         return self.__atribut_private

     @atribut_private.setter
     def atribut_private(self, value):
         self.__atribut_private = value
```

   - *Menggunakan Setter:*
```python
     daftar_nilai_mahasiswa.atribut_private = "Atribut private telah diubah"
```     

## 5. *Inheritance atau Pewarisan:*
Inheritance atau pewarisan adalah konsep di OOP di mana sebuah class dapat mewarisi atribut dan metode dari class lain. Class yang mewarisi disebut subclass, sedangkan class yang memberikan warisan disebut superclass. Pewarisan memungkinkan untuk memanfaatkan kembali kode yang sudah ada, menghindari duplikasi, dan membangun hubungan hierarki antar class.
   - *Membuat Sub Class:*
```python
     class SubDaftarNilaiMahasiswa(DaftarNilaiMahasiswa):
         def __init__(self):
             super().__init__()
```  

   - *Instance Class:*
``` python
     sub_daftar_nilai_mahasiswa = SubDaftarNilaiMahasiswa()
```

## 6. *Overriding:*
Overriding adalah konsep di OOP di mana subclass dapat mendefinisikan kembali (override) metode yang sudah ada dalam superclass. Dengan overriding, subclass memberikan implementasi baru untuk metode yang sudah ada dalam superclass. Hal ini memungkinkan subclass untuk menyediakan perilaku khusus atau perubahan pada metode yang diwarisi dari superclass.
   - *Pada Class DaftarNilaiMahasiswa:*
```python
     def cetak_data(self):
         print("Cetak data dari class DaftarNilaiMahasiswa")
```
     

   - *Pada Class SubDaftarNilaiMahasiswa:*
```python
     def cetak_data(self):
         print("Cetak data dari class SubDaftarNilaiMahasiswa")
```
     

   - *Menggunakan Overriding:*
```python
     sub_daftar_nilai_mahasiswa.cetak_data()
```
     

## *Contoh Penggunaan:*
```python
daftar_nilai_mahasiswa = DaftarNilaiMahasiswa()

daftar_nilai_mahasiswa.tambah("agung", 85)
daftar_nilai_mahasiswa.tambah("lintang", 90)
daftar_nilai_mahasiswa.tambah("nabil", 78)

daftar_nilai_mahasiswa.tampilkan()

daftar_nilai_mahasiswa.hapus("nabil")
daftar_nilai_mahasiswa.tampilkan()

daftar_nilai_mahasiswa.ubah("lintang", 95)
daftar_nilai_mahasiswa.tampilkan()


# Menghapus data mahasiswa
daftar_nilai_mahasiswa.hapus("nabil")
daftar_nilai_mahasiswa.tampilkan()
```




<H1>PRAKTIKUM🚀✨</H1>

```python
class DaftarNilaiMahasiswa:
    def __init__(self):
        self.daftar_nilai = []

    def tambah(self, nama, nilai):
        data_mahasiswa = {'nama': nama, 'nilai': nilai}
        self.daftar_nilai.append(data_mahasiswa)
        print(f"Data mahasiswa {nama} dengan nilai {nilai} telah ditambahkan.")

    def tampilkan(self):
        print("\nDaftar Nilai Mahasiswa:")
        for data in self.daftar_nilai:
            print(f"Nama: {data['nama']}, Nilai: {data['nilai']}")

    def hapus(self, nama):
        for data in self.daftar_nilai:
            if data['nama'] == nama:
                self.daftar_nilai.remove(data)
                print(f"Data mahasiswa {nama} telah dihapus.")
                return
        print(f"Data mahasiswa {nama} tidak ditemukan.")

    def ubah(self, nama, nilai_baru):
        for data in self.daftar_nilai:
            if data['nama'] == nama:
                data['nilai'] = nilai_baru
                print(f"Data mahasiswa {nama} telah diubah menjadi nilai {nilai_baru}.")
                return
        print(f"Data mahasiswa {nama} tidak ditemukan.")


# Contoh penggunaan
daftar_nilai_mahasiswa = DaftarNilaiMahasiswa()

daftar_nilai_mahasiswa.tambah("agung", 85)
daftar_nilai_mahasiswa.tambah("lintang", 90)
daftar_nilai_mahasiswa.tambah("nabil", 78)

daftar_nilai_mahasiswa.tampilkan()

daftar_nilai_mahasiswa.hapus("nabil")
daftar_nilai_mahasiswa.tampilkan()

daftar_nilai_mahasiswa.ubah("lintang", 95)
daftar_nilai_mahasiswa.tampilkan()
```

*Output:*

![Screenshot (19)](https://github.com/sentosa2505/pertemuan12/assets/148040303/019fb1a4-a298-4597-9feb-89d245cdb1c1)



<H1>FLOWCHART</H1>

![pln](https://github.com/sentosa2505/pertemuan12/assets/148040303/3eaadcb6-c8d3-4e47-a5a0-3887b5d7416d)


*Penjelasan FlowChart:*

Berikut adalah penjelasan langkah-demi-langkah dari flowchart untuk kode Python yang diberikan:

1. **Mulai:**
   - Program dimulai dengan pembuatan instance dari kelas `DaftarNilaiMahasiswa`, yang dinamai `daftar_nilai_mahasiswa`.

2. **Menambahkan Data:**
   - Tiga data mahasiswa ditambahkan menggunakan metode `tambah`:
     - Mahasiswa "agung" dengan nilai 85.
     - Mahasiswa "lintang" dengan nilai 90.
     - Mahasiswa "nabil" dengan nilai 78.

3. **Menampilkan Data:**
   - Metode `tampilkan` dipanggil untuk menampilkan daftar nama mahasiswa beserta nilai mereka.

4. **Menghapus Data (jika berlaku):**
   - Metode `hapus` dipanggil untuk menghapus mahasiswa dengan nama "nabil" dari daftar, dan pesan dicetak berdasarkan apakah mahasiswa tersebut ditemukan atau tidak.

5. **Mengubah Data (jika berlaku):**
   - Metode `ubah` dipanggil untuk mengubah nilai mahasiswa dengan nama "lintang" menjadi 95, dan pesan dicetak berdasarkan apakah mahasiswa tersebut ditemukan atau tidak.

6. **Menampilkan Data Lagi:**
   - Metode `tampilkan` dipanggil sekali lagi untuk menampilkan daftar nama mahasiswa yang telah diperbarui beserta nilai mereka.

7. **Selesai:**
   - Eksekusi program selesai.

Simbol Flowchart:
- **Kotak Persegi Panjang:** Mewakili proses atau operasi.
- **Belah Ketupat:** Mewakili titik keputusan (misalnya, pemeriksaan kondisi).
- **Persegi Panjang Miring:** Mewakili input atau output.
- **Panah:** Menunjukkan alur kontrol.

Penjelasan Flowchart:
1. **Mulai**
2. **Proses: Buat instance `DaftarNilaiMahasiswa`**
3. **Proses: Tambahkan "agung" dengan nilai 85**
4. **Proses: Tambahkan "lintang" dengan nilai 90**
5. **Proses: Tambahkan "nabil" dengan nilai 78**
6. **Proses: Tampilkan data mahasiswa**
7. **Keputusan: Apakah mahasiswa "nabil" ada?**
   - **Ya:**
     - **Proses: Hapus "nabil"**
   - **Tidak:**
     - **Proses: Cetak "Data mahasiswa nabil tidak ditemukan."**
8. **Proses: Tampilkan data mahasiswa**
9. **Keputusan: Apakah mahasiswa "lintang" ada?**
   - **Ya:**
     - **Proses: Ubah nilai "lintang" menjadi 95**
   - **Tidak:**
     - **Proses: Cetak "Data mahasiswa lintang tidak ditemukan."**
10. **Proses: Tampilkan data mahasiswa**
11. **Selesai**

Catatan: Dalam flowchart, mungkin digunakan bentuk yang berbeda untuk elemen yang berbeda (misalnya, kotak persegi panjang untuk proses, belah ketupat untuk keputusan). Penyesuaian dapat dilakukan berdasarkan konvensi dari alat pembuat flowchart yang digunakan.

<H1>Diagram Class</H1>

![diagram class](https://github.com/calamities17/PERTEMUAN12/assets/147371058/ea346872-3ef3-467d-996a-3c1aacd3ee00)

*Penjelasan Diagram Class:*

- *DaftarNilaiMahasiswa:* Kelas ini memiliki atribut daftar_nilai yang merupakan list untuk menyimpan data mahasiswa. Selain itu, terdapat empat metode:
  - __init__: Konstruktor untuk menginisialisasi objek.
  - tambah: Menambahkan data mahasiswa ke dalam daftar.
  - tampilkan: Menampilkan daftar nilai mahasiswa.
  - hapus: Menghapus data mahasiswa berdasarkan nama.
  - ubah: Mengubah nilai mahasiswa berdasarkan nama.
