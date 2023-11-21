<H1>PRAKTIKUM10</H1>
<H2>TABLE PRAKTIKUM</H2>
<H1>PROGRAM</H1>

``` python
#STEP1

from prettytable import PrettyTable

def hitung_nilai_akhir(tugas, uts, uas):
    nilai_akhir = 0.3 * tugas + 0.35 * uts + 0.35 * uas
    return nilai_akhir

def tambah_data(data_mahasiswa):
    nama = input("Masukkan nama mahasiswa: ")
    nim = input("Masukkan NIM mahasiswa: ")
    tugas = float(input("Masukkan nilai tugas: "))
    uts = float(input("Masukkan nilai UTS: "))
    uas = float(input("Masukkan nilai UAS: "))
    nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
    data_mahasiswa[nama] = {"NIM": nim, "Tugas": tugas, "UTS": uts, "UAS": uas, "Nilai Akhir": nilai_akhir}
    print("Data mahasiswa berhasil ditambahkan.")

def ubah_data(data_mahasiswa):
    nama = input("Masukkan nama mahasiswa yang akan diubah datanya: ")
    if nama in data_mahasiswa:
        tugas = float(input("Masukkan nilai tugas baru: "))
        uts = float(input("Masukkan nilai UTS baru: "))
        uas = float(input("Masukkan nilai UAS baru: "))
        nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
        data_mahasiswa[nama] = {"Tugas": tugas, "UTS": uts, "UAS": uas, "Nilai Akhir": nilai_akhir}
        print("Data mahasiswa berhasil diubah.")
    else:
        print("Nama mahasiswa tidak ditemukan.")

def hapus_data(data_mahasiswa):
    nama = input("Masukkan nama mahasiswa yang akan dihapus datanya: ")
    if nama in data_mahasiswa:
        del data_mahasiswa[nama]
        print("Data mahasiswa berhasil dihapus.")
    else:
        print("Nama mahasiswa tidak ditemukan.")

def tampilkan_data(data_mahasiswa):
    tabel = PrettyTable()
    tabel.field_names = ["Nama", "NIM", "Tugas", "UTS", "UAS", "Nilai Akhir"]

    for nama, nilai in data_mahasiswa.items():
        tabel.add_row([nama, nilai["NIM"], nilai["Tugas"], nilai["UTS"], nilai["UAS"], nilai["Nilai Akhir"]])

    print("\nDaftar Nilai Mahasiswa:")
    print(tabel)
1

def cari_data(data_mahasiswa):
    nama = input("Masukkan nama mahasiswa yang akan dicari: ")
    if nama in data_mahasiswa:
        tabel = PrettyTable()
        tabel.field_names = ["Nama", "Tugas", "UTS", "UAS", "Nilai Akhir"]
        nilai = data_mahasiswa[nama]
        tabel.add_row([nama, nilai["Tugas"], nilai["UTS"], nilai["UAS"], nilai["Nilai Akhir"]])
        print("\nData mahasiswa ditemukan:")
        print(tabel)
    else:
        print("Nama mahasiswa tidak ditemukan.")

#Program utama
data_mahasiswa = {}

while True:
    print("\nMenu Pilihan:")
    print("1. Tambah Data")
    print("2. Ubah Data")
    print("3. Hapus Data")
    print("4. Tampilkan Data")
    print("5. Cari Data")
    print("6. Keluar")

    pilihan = input("Masukkan pilihan (1-6): ")

    if pilihan == "1":
        tambah_data(data_mahasiswa)
    elif pilihan == "2":
        ubah_data(data_mahasiswa)
    elif pilihan == "3":
        hapus_data(data_mahasiswa)
    elif pilihan == "4":
        tampilkan_data(data_mahasiswa)
    elif pilihan == "5":
        cari_data(data_mahasiswa)
    elif pilihan == "6":
        print("Program selesai.")
        break
    else:
        print("Pilihan tidak valid. Masukkan angka 1-6.")
```



# KONTAK 

``` python
#PROGRAM

from prettytable import PrettyTable

#Buat dictionary daftar kontak
daftar_kontak = {
    'Ari': '081234567',
    'Dina': '087654321',
}

#Tampilkan kontaknya Ari
print(f"Kontak Ari: {daftar_kontak.get('Ari', 'Kontak tidak ditemukan')}")

#Tambah kontak baru dengan nama Riko, nomor 087654544
daftar_kontak['Riko'] = '087654544'
print("Kontak Riko ditambahkan.")

#Ubah kontak Dina dengan nomor baru 088999776
if 'Dina' in daftar_kontak:
    daftar_kontak['Dina'] = '088999776'
    print("Nomor kontak Dina diubah.")
else:
    print("Kontak Dina tidak ditemukan.")

#Tampilkan semua Nama
print("Semua Nama:")
for nama in daftar_kontak.keys():
    print(nama)

#Tampilkan semua Nomor
print("\nSemua Nomor:")
for nomor in daftar_kontak.values():
    print(nomor)

#Tampilkan daftar Nama dan nomornya menggunakan pretty table
tabel_kontak = PrettyTable()
tabel_kontak.field_names = ["Nama", "Nomor"]
for nama, nomor in daftar_kontak.items():
    tabel_kontak.add_row([nama, nomor])

print("\nDaftar Nama dan Nomor:")
print(tabel_kontak)

#Hapus kontak Dina
if 'Dina' in daftar_kontak:
    del daftar_kontak['Dina']
    print("\nKontak Dina dihapus.")
else:
    print("\nKontak Dina tidak ditemukan.")
```


# TABLE LIST
<p>OUTPUT</p>

![Screenshot (19)](https://github.com/calamities17/PERTEMUAN10/assets/147371058/8a5989f6-8bc2-40ff-9e7c-c422f4fb145f)

# KONTAK
<p>OUTPUT</p>

![Screenshot (20)](https://github.com/calamities17/PERTEMUAN10/assets/147371058/8d2b6501-b62d-4a24-b40e-320216bcc5d4)

# FLOWCHART TABLE LIST

![grg003mp](https://github.com/calamities17/PERTEMUAN10/assets/147371058/e4617bbf-b063-45e6-8ddd-aad97468a387)



<P>PENJELASAN FLOWCHART TABLE LIST</P>

1. **Inisialisasi:**
   - Proses dimulai dengan menginisialisasi kamus kosong bernama `data_mahasiswa`.
   - Opsi menu ditampilkan kepada pengguna.
   - Pilihan pengguna dibaca dan disimpan dalam variabel `choice`.

2. **Struktur Keputusan:**
   - Flowchart masuk ke dalam struktur keputusan berdasarkan pilihan pengguna.
   - Jika pilihan adalah "Tambah Data", flowchart akan masuk ke cabang yang sesuai.
   - Jika pilihan adalah "Ubah Data", maka akan masuk ke cabang tersebut.
   - Jika pilihan adalah "Hapus Data", maka akan masuk ke cabang tersebut.
   - Jika pilihan adalah "Tampilkan Data", maka akan masuk ke cabang tersebut.
   - Jika pilihan adalah "Cari Data", maka akan masuk ke cabang tersebut.
   - Jika tidak ada opsi yang dipilih di atas, akan mencetak pesan kesalahan.

3. **Cabang "Tambah Data":**
   - Jika pengguna memilih untuk menambahkan data, flowchart akan melalui langkah-langkah berikut:
     - Membaca input untuk nama (nama), NIM (nim), dan nilai (tugas, uts, uas).
     - Menghitung nilai akhir berdasarkan bobot tertentu.
     - Menambahkan data ke kamus `data_mahasiswa`.
     - Mencetak pesan keberhasilan yang menunjukkan bahwa data mahasiswa telah ditambahkan.

4. **Cabang "Ubah Data":**
   - Jika pengguna memilih untuk mengubah data, flowchart akan melalui langkah-langkah berikut:
     - Membaca input untuk nama (nama) dan nilai baru (tugas, uts, uas).
     - Memeriksa apakah nama tersebut ada dalam kamus `data_mahasiswa`.
       - Jika ada, menghitung ulang nilai akhir dan memperbarui data.
       - Jika tidak ada, mencetak pesan kesalahan.

5. **Cabang "Hapus Data":**
   - Jika pengguna memilih untuk menghapus data, flowchart akan melalui langkah-langkah berikut:
     - Membaca input untuk nama (nama).
     - Memeriksa apakah nama tersebut ada dalam kamus `data_mahasiswa`.
       - Jika ada, menghapus data tersebut.
       - Jika tidak ada, mencetak pesan kesalahan.

6. **Cabang "Tampilkan Data":**
   - Jika pengguna memilih untuk menampilkan data, flowchart akan melalui langkah-langkah berikut:
     - Membuat tabel cantik bernama `tabel`.
     - Menambahkan nama bidang ke dalam tabel.
     - Melakukan iterasi pada kamus `data_mahasiswa` dan menambahkan baris ke dalam tabel.
     - Mencetak tabel yang berisi daftar data mahasiswa.

7. **Cabang "Cari Data":**
   - Jika pengguna memilih untuk mencari data, flowchart akan melalui langkah-langkah berikut:
     - Membaca input untuk nama (nama).
     - Memeriksa apakah nama tersebut ada dalam kamus `data_mahasiswa`.
       - Jika ada, membuat tabel cantik bernama `tabel` dan menampilkan data.
       - Jika tidak ada, mencetak pesan kesalahan.

8. **Akhir:**
   - Program berakhir setelah menyelesaikan operasi yang dipilih atau mencetak pesan kesalahan.

Flowchart ini memberikan representasi visual dari logika dan proses pengambilan keputusan dalam program yang dijelaskan.

