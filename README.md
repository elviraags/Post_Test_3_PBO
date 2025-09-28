# Post_Test_3_PBO
## Sistem Manjemen Pasien Klinik Gigi

Sistem Manajemen Pasien Klinik Gigi adalah aplikasi sederhana berbasis Java yang menggunakan konsep CRUD untuk menambah, melihat, mengubah, dan menghapus data pasien. Program ini menerapkan struktur MVC dengan pemisahan class dalam packages model, service, dan main, serta dilengkapi constructor, access modifier, dan fitur pencarian pasien berdasarkan nama. Dengan demikian, pengelolaan data pasien menjadi lebih mudah, terstruktur, dan fleksibel.

Fitur utama adalah:

Tambah Pasien : digunakan untuk menambah daftar pasien baru
Lihat Pasien : digunakan untuk melihat seluruh data pasien yang terdaftar
Ubah data pasien : digunakan untuk mengubah data pasien yang sudah terdaftar, seperti merubah nama, usia, dan layanan
Hapus Pasien : digunakan untuk menghapus data pasien yang sudah terdaftar
Cari pasien : digunakan untuk mencari pasien yang sudah terdaftar dengan menginput nama pasien

Packages  dan Class awal

<img width="609" height="226" alt="image" src="https://github.com/user-attachments/assets/33fb7db9-0fd2-4756-9c23-c9d48b2d1f06" />

## SuperClass dan SubClass

kemudian saya menambahkan SuperClass dan Subclass baru pada packages model

<img width="598" height="270" alt="image" src="https://github.com/user-attachments/assets/fdb71864-6bad-46a9-b467-1664c2d4d841" />

Superclass berfungsi sebagai class induk yang menyimpan atribut dan method yang bersifat umum agar dapat digunakan kembali oleh class turunannya. disini saya menggunakan class pasien sebagai induk yaitu SuperClass

<img width="1919" height="821" alt="image" src="https://github.com/user-attachments/assets/b12d5477-b1ac-41e1-a9f2-c0801b6fc1b3" />

Kemudain saya membuat 2 Subclass baru sebagai turunan dari Superclass yang berfungsi sebagai class turunan yang mewarisi sifat-sifat dari superclass, lalu menambahkan atribut atau perilaku yang lebih khusus sesuai kebutuhan. saya membuat dua Subclass yaitu PasienDewasa da PasienAnak

<img width="1919" height="725" alt="image" src="https://github.com/user-attachments/assets/996606a3-49a9-4700-bbc2-cb15364ce8a8" />

Pada PasienDewasa, memiliki atribut utama turunan dari Superclass yaitu nama, umur, dan layanan, lalu saya menambahkan atribut baru yang khusus untuk pasien dewasa, yaitu pekerjaan. Dengan cara ini, kita bisa membedakan pasien dewasa dari pasien anak-anak

<img width="1919" height="823" alt="image" src="https://github.com/user-attachments/assets/7aea735f-6551-40f9-b854-81797f337c72" />

Pada PasienAnak, memiliki atribut utama turunan dari Superclass yaitu nama, umur, dan layanan, lalu saya menambahkan atribut khusus untuk pasien anak yaitu namaOrangTua. Atribut ini penting karena data anak biasanya terkait dengan orang tua yang bertanggung jawab.

## Penerapam Getter dan Setter
Getter dan setter adalah method khusus dalam pemrograman berorientasi objek yang digunakan untuk mengakses dan mengubah nilai atribut pada sebuah class.

<img width="1919" height="810" alt="image" src="https://github.com/user-attachments/assets/969725ba-ea47-4794-83d7-a9392de48959" />

Getter dan setter ditempatkan di superclass (Pasien) karena superclass menyimpan atribut dasar yang umum dimiliki oleh semua subclass, yaitu nama, umur, dan layanan. Dengan adanya getter dan setter di superclass, jadi subclass seperti PasienDewasa dan PasienAnak bisa memanfaatkan method ini secara langsung tanpa harus menuliskannya ulang.


<img width="1919" height="878" alt="image" src="https://github.com/user-attachments/assets/fc52fbff-02bc-4068-b8e2-52fafe358820" />

Bagian dari menu "Tambah Pasien", jika saya memilih opsi ini, program akan menampilkan pilihan kategori pasien, yaitu Pasien Dewasa atau Pasien Anak. Setelah kategori dipilih, program meminta saya untuk memasukkan data umum pasien berupa nama, umur, dan jenis layanan yang akan digunakan. Kemudian, berdasarkan kategori yang dipilih, program membuat objek pasien sesuai subclass-nya. Jika saya memilih kategori Pasien Dewasa, maka program juga meminta data tambahan berupa pekerjaan, dan objek yang dibuat adalah PasienDewasa. Sedangkan jika saya memilih kategori Pasien Anak, maka program akan meminta nama orang tua, lalu membuat objek PasienAnak

## Override

<img width="1556" height="280" alt="image" src="https://github.com/user-attachments/assets/b42cde78-5aec-42c5-9fc2-e35d9b171e96" />

Pada PasienAnak, penggunaan override dengan menambahkan informasi nama orang tua pasien. Sama seperti pada PasienDewasa, method ini memanggil method dari superclass terlebih dahulu, lalu menambahkan informasi tambahan yang relevan.

<img width="1531" height="277" alt="image" src="https://github.com/user-attachments/assets/dbf65ecb-c47d-4967-999d-c27995d13804" />

Pada PasienDewasa, penggunaan override dengan menambahkan informasi pekerjaan pasien. jadi method di subclass tetap memanggil super.tampilkanInfo() untuk menampilkan data umum dari superclass, kemudian menambahkan baris output tambahan khusus untuk pekerjaan.



## Polymorphism (Overloading) Abstract pada claas pasien 

<img width="1378" height="676" alt="image" src="https://github.com/user-attachments/assets/0846a7f3-d265-4740-b459-e966d8d03504" />

Pasien adalah kelas induk (superclass) yang bersifat abstrak. Karena mendefinisikan umum pasien (punya nama, umur, layanan) tetapi cara menampilkan informasi (tampilkanInfo) bisa berbeda tergantung jenis pasien (anak / dewasa).


## Extends Subclass PasienAnak

<img width="1423" height="607" alt="image" src="https://github.com/user-attachments/assets/7cf229df-4006-4327-951b-290d8130d072" />

Bisa lebih dari satu versi method tampilkanInfo, misalnya:

public abstract void tampilkanInfo();         
public void tampilkanInfo(boolean detail); 

Jadi saat dipanggil, bisa pilih tampilkanInfo() atau tampilkanInfo(true). Saat tampilkanInfo() dipanggil dari variabel bertipe Pasien, maka otomatis menjalankan implementasi yang sesuai dengan objek PasienAnak atau PasienDewasa.

## Extends Subclass PasienDewasa

<img width="1357" height="552" alt="image" src="https://github.com/user-attachments/assets/0e88b164-908e-42a9-9a65-41d7f799ed98" />

PasienAnak adalah turunan (extends) dari Pasien dengan Tambahan atribut khusus yaitu namaOrangTua. Override method tampilkanInfo() supaya selain nama, umur, layanan juga tampil nama orang tua. Overriding PasienAnak menimpa cara tampilkanInfo() dari Pasien.


## Interface Class Registrasi 

<img width="1285" height="423" alt="image" src="https://github.com/user-attachments/assets/1029fdcf-6f2c-4f4a-89f1-9479cefafae7" />

PasienDewasa juga turunan dari Pasien. Override method tampilkanInfo() supaya selain info dasar juga menampilkan pekerjaan. Sama seperti PasienAnak. Walau sama-sama Pasien, output informasi berbeda tergantung apakah pasien itu anak atau dewasa.


## Implements Interface Class PasienServic

<img width="1381" height="700" alt="image" src="https://github.com/user-attachments/assets/6991daa3-1124-437d-bfd8-b310fa2c7c0c" />

Registrasi adalah interface (kontrak), dengan mendefinisikan satu method wajib yaitu void daftarPasien(Pasien pasien);
Semua class yang implements Registrasi wajib menyediakan implementasi dari method ini.


## Alur Program

<img width="470" height="342" alt="image" src="https://github.com/user-attachments/assets/f707678e-1835-4dfa-8dd1-b37ae9447edc" />

disini saya memilih menu no 1 untuk Tambah Pasien, karna sebelumnya saya menambahkan Superclass dan Subclass, maka disini diminta untuk memilih pasien dewasa atau pasien anak, dan saya memilih untuk menginput pasien dewasa dengan masukkan nama, umur, dan layanan. karena saya memilih pasien dewasa, maka otomatis program meminta untuk masukkan pekerjaan sesuai dengan subclass pasien dewasa.

<img width="278" height="142" alt="image" src="https://github.com/user-attachments/assets/89366965-8b4f-46dc-aaa4-f620b29ea0ff" />

berikut adalah output pasien dewasa

<img width="506" height="567" alt="image" src="https://github.com/user-attachments/assets/f791a79e-e6ff-4c72-b641-c4fc01cfc37c" />

Sama seperti sebelumnya, saya menambahkan pasien dengan memilih pasien anak, dan saya memilih untuk menginput pasien anak dengan masukkan nama, umur, dan layanan. karena saya memilih pasien anak, maka otomatis program meminta untuk masukkan nama orang tua sesuai dengan subclass pasien anak. 

<img width="275" height="147" alt="image" src="https://github.com/user-attachments/assets/3bff8efd-3c3d-426b-ba8a-23684058a4e4" />


berikut adalah output pasien Anak

jadi itulah fungsi dari Superclass dan Subclass, untuk opsi menu lainnya sama seperti sebelumnya, hanya beda pada menu "Tambah Pasien" dengan turuan dari Pasien yaitu PasienDewasa dan PasienAnak
