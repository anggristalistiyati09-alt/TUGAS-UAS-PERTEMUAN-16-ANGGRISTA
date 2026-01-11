# TUGAS-UAS-PERTEMUAN-16-ANGGRISTA

    class Data:
        def __init__(self):
            self.value = None

    class View:
        def display_welcome(self):
            print("Selamat datang di Program Sederhana")
            print("-" * 30)

        def display_result_table(self, value):
            print("\nHasil:")
            print("+" + "-"*12 + "+" + "-"*15 + "+")
            print("| {:<10} | {:<13} |".format("Deskripsi", "Nilai"))
            print("+" + "-"*12 + "+" + "-"*15 + "+")
            print("| {:<10} | {:<13} |".format("Input", value))
            print("+" + "-"*12 + "+" + "-"*15 + "+")

        def display_error(self, message):
            print(f"Error: {message}")

    class Process:
        def __init__(self, data, view):
            self.data = data
            self.view = view

        def get_user_input(self):
            while True:
                try:
                    user_input = input("Masukkan sebuah angka bulat: ")
                    # Validasi input menggunakan eksepsi
                    number = int(user_input)
                    self.data.value = number
                    break
                except ValueError:
                    self.view.display_error("Input tidak valid. Harap masukkan angka bulat.")

        def run(self):
            self.view.display_welcome()
            self.get_user_input()
            self.view.display_result_table(self.data.value)



Penjelasan Persyaratan Program
Berikut adalah penjelasan langkah demi langkah mengenai persyaratan untuk membuat program sederhana tersebut: 
1. Konsep Modular dan OOP
Answer: Program harus dirancang menggunakan konsep modularitas dan Object-Oriented Programming (OOP).
Penjelasan: 
Modular: Kode program harus dipecah menjadi bagian-bagian yang lebih kecil dan terkelola (modul atau kelas).
OOP: Program harus memanfaatkan fitur-fitur OOP seperti enkapsulasi, dengan memisahkan logika menjadi tiga kelas utama: class data (untuk menangani data atau model), class view (untuk menangani tampilan atau interaksi pengguna), dan class process (untuk menangani logika bisnis atau pemrosesan data).
2. Input Pengguna
Answer: Program harus dapat menerima masukan atau data dari pengguna saat runtime.
Penjelasan:
Fungsionalitas ini memastikan interaktivitas, di mana pengguna dapat memasukkan informasi yang diperlukan agar program dapat memproses dan menghasilkan output yang relevan.
3. Validasi Input dan Eksepsi
Answer: Program harus menyertakan mekanisme untuk memvalidasi input pengguna dan menangani kesalahan menggunakan konsep eksepsi (exceptions).
Penjelasan:
Validasi Input: Memeriksa apakah data yang dimasukkan pengguna sesuai dengan format atau batasan yang diharapkan (misalnya, memastikan input angka adalah bilangan bulat positif).
Eksepsi: Menggunakan penanganan eksepsi (seperti try-catch di banyak bahasa pemrograman) untuk mengelola kesalahan yang mungkin terjadi selama input atau pemrosesan, sehingga program tidak crash dan dapat memberikan umpan balik yang bermakna kepada pengguna.
4. Tampilan Hasil (Table View)
Answer: Program harus menampilkan hasil eksekusi dalam format yang terstruktur, idealnya sebagai tampilan tabel (table view).
Penjelasan:
Menampilkan data dalam format tabel memudahkan pengguna untuk membaca dan memahami output, terutama jika hasilnya melibatkan banyak record atau data terstruktur. Penggunaan tampilan tabel meningkatkan keterbacaan dan pengalaman pengguna.

# CLASS DATA

    def __init__(self):
        self.value = None

    Penjelasan:
Digunakan untuk menyimpan data angka yang dimasukkan pengguna.
self.value awalnya bernilai None karena belum ada input.

# CLASS VIEW
a. display_welcome()

    print("Selamat datang di Program Sederhana")
    print("-" * 30)

Class ini bertugas menampilkan output ke layar.


b. display_result_table(self, value)

    print("\nHasil:")
    print("+------------+---------------+")
    print("| Deskripsi  | Nilai         |")
    print("+------------+---------------+")
    print("| Input      | value         |")
    print("+------------+---------------+")


Fungsi ini:
Menampilkan hasil input dalam bentuk tabel
Kolom Deskripsi dan Nilai
value adalah angka yang dimasukkan pengguna

# class process
Class ini adalah pengatur alur program (logika utama).

a. __init__(self, data, view)

    self.data = data
    self.view = view

b. get_user_input(self)

    while True:
        try:
            user_input = input("Masukkan sebuah angka bulat: ")
            number = int(user_input)
            self.data.value = number
            break
        except ValueError:
            self.view.display_error("Input tidak valid. Harap masukkan angka bulat.")

Penjelasan langkah demi langkah:
Program meminta input angka
int(user_input) → validasi input
Jika valid:
Disimpan ke self.data.value
Perulangan berhenti
Jika tidak valid:
Muncul pesan error
Program meminta input ulang

c. run(self)

    self.view.display_welcome()
    self.get_user_input()
    self.view.display_result_table(self.data.value)

Urutan eksekusi program:
Menampilkan pesan sambutan
Meminta dan memvalidasi input pengguna
Menampilkan hasil dalam tabel

# Alur Program Secara Singkat
Program dimulai
Menampilkan pesan selamat datang
Pengguna memasukkan angka
Input divalidasi:
Salah → tampil error
Benar → lanjut
Hasil ditampilkan dalam tabel
Program selesai

# Kesimpulan
✔ Program menerapkan OOP dengan pemisahan tugas yang jelas
✔ Menggunakan validasi input dengan try-except
✔ Output disajikan rapi dalam bentuk tabel
✔ Cocok sebagai contoh program Python dasar yang terstruktur
