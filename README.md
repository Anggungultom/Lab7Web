# PHP FRAMMEWORK(Codeigniter)
  Beberapa ekstensi PHP perlu diaktifkan untuk kebutuhan pengembangan Codeigniter 4.

 Berikut beberapa ekstensi yang perlu diaktifkan:      
• php-json ekstension untuk bekerja dengan JSON;    
• php-mysqlnd native driver untuk MySQL;                                          
• php-xml ekstension untuk bekerja dengan XML;                                  
• php-intl ekstensi untuk membuat aplikasi multibahasa;                             
• libcurl (opsional), jika ingin pakai Curl.

Untuk mengaktifkan ekstentsi tersebut, melalu XAMPP Control Panel, pada bagian Apache klik Config -> PHP.ini

![image](https://github.com/user-attachments/assets/a41f19d6-26bf-4963-9106-9cd3ac761db2)


![image](https://github.com/user-attachments/assets/475e548f-f4ed-4bed-b3fa-54bae4403090)


Pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan.
Kemudian simpan kembali filenya dan restart Apache web server.

Instalasi Codeigniter 4

Untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara manual
dan menggunakan composer. Pada praktikum ini kita menggunakan cara manual.

• Unduh Codeigniter dari website https://codeigniter.com/download

• Extrak file zip Codeigniter ke direktori htdocs/lab11_ci.

• Ubah nama direktory framework-4.x.xx menjadi ci4.

• Buka browser dengan alamat http://localhost/lab11_ci/ci4/public/

![image](https://github.com/user-attachments/assets/5c81eac4-f9cc-43b4-b052-af7a523e3a7b)

- Menjalankan CLI (Command Line Interface)

Codeigniter 4 menyediakan CLI untuk mempermudah proses development. Untuk mengakses
CLI buka terminal/command prompt.

![image](https://github.com/user-attachments/assets/63d89e18-8936-4cb9-b98c-b0100fb40034)

Arahkan lokasi direktori sesuai dengan direktori kerja project dibuat
(xampp/htdocs/lab11_ci/ci4/)

Perintah yang dapat dijalankan untuk memanggil CLI Codeigniter adalah:

![image](https://github.com/user-attachments/assets/4748b158-dbca-488e-87f6-d10eeafe7b30)


Mengaktifkan Mode Debugging

Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk mengetahui
pesan error apabila terjadi kesalahan dalam membuat kode program.

Secara default fitur ini belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan pesan
kesalahan ,namun jika tidak ada kesalahan akan tampil seperti berikut.

![image](https://github.com/user-attachments/assets/6fa57ef7-aaad-4d60-94b3-a72bfbd9b028)


Semua jenis error akan ditampilkan sama.Untuk memudahkan mengetahui jenis errornya,
maka perlu diaktifkan mode debugging dengan mengubah nilai konfigurasi pada environment
variable CI_ENVIRINMENT menjadi development.


![image](https://github.com/user-attachments/assets/7e50bdec-b42f-4cef-b90d-952dbeb0a14e)


Contoh error yang terjadi. Untuk mencoba error tersebut, ubah kode pada file
app/Controller/Home.php hilangkan titik koma pada akhir kode.

![image](https://github.com/user-attachments/assets/29c098eb-515d-49eb-96ef-7bb8c8ad4830)


Routing dan Controller

Pada Codeigniter, request yang diterima oleh file index.php akan diarahkan ke Router untuk
meudian oleh router tesebut diarahkan ke Controller.

![image](https://github.com/user-attachments/assets/23bd6f82-6e81-4cba-949a-905487e76748)

Kode tersebut akan mengarahkan rute untuk halaman home.
untuk menambahkan rute baru tambahkan kode berikut;

![image](https://github.com/user-attachments/assets/0db66dfe-47d9-446a-9758-db1672028fbf)

Untuk mengetahui route yang ditambahkan sudah benar, buka CLI dan jalankan perintah
berikut.
php spark routes

![image](https://github.com/user-attachments/assets/c1f68dfc-825a-4476-9f75-1af69b3b2f15)

Selanjutnya coba akses route yang telah dibuat dengan mengakses alamat url
http://localhost:8080/about

![image](https://github.com/user-attachments/assets/d93427c6-9434-4e1b-8423-69b3e5c6fc0c)

Ketika diakses akan mucul tampilan error 404 file not found, itu artinya file/page tersebut tidak
ada. Untuk dapat mengakses halaman tersebut, harus dibuat terlebih dahulu Contoller yang
sesuai dengan routing yang dibuat yaitu Contoller Page.

-Membuat Controller

Selanjutnya adalah membuat Controller Page. Buat file baru dengan nama page.php pada
direktori Controller kemudian isi kodenya seperti berikut.

![image](https://github.com/user-attachments/assets/d79d4a6c-bb07-4658-921e-034a76f09bc9)

Selanjutnya refresh Kembali browser, maka akan ditampilkan hasilnya yaotu halaman sudah
dapat diakses.

![image](https://github.com/user-attachments/assets/c5555067-c447-4147-a365-aa55761d66d7)

-Auto Routing

Secara default fitur autoroute pada Codeiginiter sudah aktif. Untuk mengubah status autoroute
dapat mengubah nilai variabelnya. Untuk menonaktifkan ubah nilai true menjadi false.

$routes->setAutoRoute(true);

Tambahkan method baru pada Controller Page seperti berikut.

public function tos()

{
echo "ini halaman Term of Services";

}

Method ini belum ada pada routing, sehingga cara mengaksesnya dengan menggunakan
alamat: http://localhost:8080/page/tos

![image](https://github.com/user-attachments/assets/f6d7cf73-7ad6-4fd9-9936-bf8fed2abca0)

-Membuat View

Selanjutnya adalam membuat view untuk tampilan web agar lebih menarik. Buat file baru
dengan nama about.php pada direktori view (app/view/about.php) kemudian isi kodenya
seperti berikut.


![image](https://github.com/user-attachments/assets/73fba42f-1f8a-4c36-96cc-31e0fe8e196a)

Kemudian lakukan refresh pada halaman tersebut.

![image](https://github.com/user-attachments/assets/598a3b8c-6866-4b7c-8112-a88cb350489d)

-Membuat Layout Web dengan CSS

Pada dasarnya layout web dengan css dapat diimplamentasikan dengan mudah pada
codeigniter. Yang perlu diketahui adalah, pada Codeigniter 4 file yang menyimpan asset css
dan javascript terletak pada direktori public.

Buat file css pada direktori public dengan nama style.css
Kemudian buat folder template pada direktori view kemudian buat file header.php dan
footer.php

File app/view/template/header.php

![image](https://github.com/user-attachments/assets/1be98603-baaf-4e4a-af84-79928ca2de07)

![image](https://github.com/user-attachments/assets/f523bd5a-0932-44e1-b753-0e4bbe5ff97c)


File app/view/template/footer.php

![image](https://github.com/user-attachments/assets/c45dc6c0-13d0-49ec-aceb-70a7d15ccd54)

Kemudian ubah file app/view/about.php seperti berikut.

![image](https://github.com/user-attachments/assets/9d94e769-4d0b-4e59-82db-4e6f54f70e75)

Selanjutnya refresh tampilan pada alamat http://localhost:8080/about

Dan Begini Lah Hasil Akhirnya untuk Praktikum 1:)


![image](https://github.com/user-attachments/assets/2d9e1134-1b55-4540-b9ea-7992263b796d)



# Praktikum 2: Framework Lanjutan(CRUD)

Repositori ini merupakan bagian dari praktikum Lab 7, yang membahas pembuatan aplikasi CRUD sederhana menggunakan **CodeIgniter 4** dan **MySQL**.



**Fitur Utama:**

    - view($slug)
    Menampilkan detail artikel berdasarkan slug URL. Digunakan untuk halaman publik.

    - admin_index()
    Menampilkan seluruh data artikel di halaman admin. Ini adalah dashboard utama admin.

    - add()
    Menyediakan form tambah artikel, validasi input, dan menyimpan data baru ke database.

    - edit($id)
    Menyediakan form edit artikel dan menangani proses update data ke database berdasarkan ID artikel.

    - delete($id)
    Menghapus data artikel dari database berdasarkan ID.



 **Struktur Terkait:**

    Model: app/Models/ArtikelModel.php
    Menghubungkan controller dengan database, serta mendefinisikan field yang boleh diisi (allowedFields).

    View:

        app/Views/artikel/admin_index.php – Daftar semua artikel

        app/Views/artikel/form_add.php – Form tambah artikel

        app/Views/artikel/form_edit.php – Form edit artikel

        app/Views/artikel/detail.php – Tampilan detail artikel

    Routing:
    Telah ditambahkan group routing untuk admin pada app/Config/Routes.php:

    #$routes->group('admin', function($routes) {
    $routes->get('artikel', 'Artikel::admin_index');
    $routes->add('artikel/add', 'Artikel::add');
    $routes->add('artikel/edit/(:any)', 'Artikel::edit/$1');
    $routes->get('artikel/delete/(:any)', 'Artikel::delete/$1');
    });





**Tabel Artikel**


![image](https://github.com/user-attachments/assets/99baaf4c-ad7e-443d-9b27-e42573af884f)


⚙️ **Konfigurasi Koneksi Database**
1. Buka file .env di folder project CI4
2. Cari bagian konfigurasi database
   
   ![image](https://github.com/user-attachments/assets/4a6c69f6-e615-4747-a2da-1b829d57dad7)

3. Ubah dan aktifkan konfigurasi
   - Hapus tanda # di depan baris-baris itu
   - Ganti nilainya menjadi:

     ![image](https://github.com/user-attachments/assets/3079be52-d8c6-4bee-b3dd-42e4bd692b8f)


  *Catatan Penting*
  
- username = root → default XAMPP

- password = (kosong) → jika kamu tidak mengatur password di XAMPP

- database.default.database = lab_ci4 → nama database yang sudah kamu buat

4. Simpan file .env


   

# Tampilan Aplikasi Portal Berita
**Halaman Daftar Artikel (User)**

   ![image](https://github.com/user-attachments/assets/a546b256-2d26-4114-95a3-656f108788c2)


*Penjelasan:*

- Menampilkan semua artikel yang telah dipublikasikan.

- Setiap judul artikel dapat diklik untuk melihat detailnya.



**Halaman About (User)**

   ![image](https://github.com/user-attachments/assets/0c9de625-9b9e-487b-98c1-bfaf5c877074)

 *Penjelasan:*

- Halaman statis yang menjelaskan informasi tentang portal berita.


**Halaman Edit Artikel (Admin)**

![image](https://github.com/user-attachments/assets/4410c928-d46d-4a6f-8852-175f20117751)


*Penjelasan:*

- Admin dapat memperbarui artikel yang sudah dibuat.

- Form terdiri dari input judul dan isi.


**Halaman Tambah Artikel (Admin)**

![image](https://github.com/user-attachments/assets/016ba045-ce2d-4fe7-81e2-bd6a6f069050)

*Penjelasan:*

- Admin dapat membuat artikel baru dengan input: judul, isi, upload gambar, dan memilih status (published/draft).



**Tambah Artikel**

Berikut tampilan halaman untuk menambah artikel baru:


![image](https://github.com/user-attachments/assets/cd4297e0-287a-472e-8d46-dd61e612e710)


Keterangan:

- Admin dapat mengisi judul, isi, upload gambar, dan memilih status.

- Gambar akan disimpan dan artikel masuk ke database saat tombol Simpan ditekan.





**Edit Artikel**

Gambar berikut menunjukkan tampilan halaman edit artikel pada portal admin:



![image](https://github.com/user-attachments/assets/6c6656a8-1725-45e2-bbd6-96bea3e15962)


Keterangan:

- Admin dapat mengubah judul dan isi artikel.

- Setelah klik tombol Kirim, data akan diperbarui di database.


**Cara Akses:**

    - Halaman admin: localhost:8080/admin/artikel

    - Tambah artikel: localhost:8080/admin/artikel/add

    - Edit artikel: localhost:8080/admin/artikel/edit/1

    - Detail publik: localhost:8080/artikel/artikel-pertama




# Penjelasan Praktikum 3: View Layout dan View Cell


**1. Tujuan Praktikum**

Praktikum ini bertujuan untuk:

- Menggunakan View Layout di CodeIgniter 4 untuk membuat kerangka halaman utama.

- Menerapkan View Cell untuk menampilkan komponen UI secara modular (seperti widget artikel terbaru di sidebar).


**2. Membuat Layout Utama**

*Langkah:*

- Buat folder layout di app/Views/

- Buat file main.php

![image](https://github.com/user-attachments/assets/e51e259f-888d-40f2-914b-e1abf9212052)


**3. Mengubah View Home agar Gunakan Layout**
*File*: app/Views/home.php

![image](https://github.com/user-attachments/assets/bc736af3-ebd1-4b95-9c3a-7f95924c7536)


**4. Membuat View Cell: ArtikelTerkini**

*Langkah:*

- Buat folder app/Cells/

- Buat file ArtikelTerkini.php

![image](https://github.com/user-attachments/assets/794dd012-b887-475e-9643-f50e697936e2)



**5. Buat View Cell Template**

*Folder*: app/Views/components/

*File*: artikel_terkini.php

![image](https://github.com/user-attachments/assets/7b2ffb18-37c8-4a51-ac4e-e0401e2a388d)


**Hasil Akhir Praktikum 3**
![image](https://github.com/user-attachments/assets/c162ede6-e2e0-42ca-9bfa-a6f13c902a89)


# Praktikum 4 - Modul Login dan Auth dengan CodeIgniter 4

 yang berfokus pada pembuatan sistem login sederhana dengan CodeIgniter 4 menggunakan fitur Auth, Filter, dan Session.


 **Tujuan Praktikum**
 
- Memahami konsep dasar authentication dan filter di CodeIgniter 4

- Menerapkan sistem login sederhana menggunakan session

- Membatasi akses admin menggunakan Auth Filter


***Langkah-langkah Praktikum***

**1. Membuat Tabel user**

![image](https://github.com/user-attachments/assets/1967f28a-f62f-4456-8107-391805ae26b6)


**2. Membuat Model UserModel.php**

*Lokasi*: app/Models/UserModel.php

![image](https://github.com/user-attachments/assets/5d48df21-e57c-409c-9937-0c99b58bc1ba)

**3. Membuat Controller User.php**

*Lokasi*: app/Controllers/User.php

![image](https://github.com/user-attachments/assets/94b9730e-6486-49c8-a16c-56ed33fd3c74)

![image](https://github.com/user-attachments/assets/c8d595ad-e380-45b9-a875-a7771f8aa561)


**4. Membuat View Login**

*Lokasi*: app/Views/user/login.php

![image](https://github.com/user-attachments/assets/745e45e8-a747-488f-9dff-a8c93165e075)


**5. Membuat Database Seeder**

- *Jalankan perintah:*

php spark make:seeder UserSeeder

- *Isi file app/Database/Seeds/UserSeeder.php:*

  ![image](https://github.com/user-attachments/assets/a6b0143e-0c94-4e5e-84de-a9c7b81eeba3)

- *Jalankan seedernya:*

php spark db:seed UserSeeder



![image](https://github.com/user-attachments/assets/c08e1e80-fcc4-4339-a060-28d874ebc068)


**6. Membuat Filter Auth**

*Lokasi*: app/Filters/Auth.php

![image](https://github.com/user-attachments/assets/051e3876-54d9-4c48-ac6b-7004b3ab7741)

**7. Daftarkan Filter di Config/Filters.php**

*Tambahkan:*

'auth' => App\Filters\Auth::class,


**8. Gunakan Filter di Routing**

Buka app/Config/Routes.php dan tambahkan:

![image](https://github.com/user-attachments/assets/c9adb165-fc87-4e51-89f7-da6be8171916)


**Sekarang Jalankan dan Uji**

- *Jalankan:*

php spark serve

-*Akses:*

http://localhost:8080/user/login


![image](https://github.com/user-attachments/assets/06fec595-ba58-4e7b-927c-490c62db4c4b)


# Praktikum 5 - Pagination dan Pencarian 

**Tujuan**

- Memahami konsep dasar Pagination.

- Memahami konsep dasar Pencarian data.

- Menerapkan fitur Pagination dan Pencarian pada aplikasi menggunakan Framework CodeIgniter 4.

**Langkah-Langkah Praktikum**

*1. Menambahkan Pagination di Controller Artikel*

![image](https://github.com/user-attachments/assets/cf981dde-c4d7-4bd8-b81f-85c9953288a4)

**2. Menampilkan Pagination Link di admin_index.php**

*Tambahkan kode berikut setelah tabel data:*

<?= $pager->links(); ?>

![image](https://github.com/user-attachments/assets/cec3d017-a52d-40d8-ab2a-1a6cc868e8ac)


![image](https://github.com/user-attachments/assets/aea019f6-9561-417f-b3ff-d1fbc20ccbc0)




**3. Menambahkan Fitur Pencarian**

Ubah kembali method admin_index seperti berikut:


Tambahkan form pencarian di admin_index.php:


Ubah kode pagination menjadi:

![image](https://github.com/user-attachments/assets/a5086ca3-2651-46c2-8b8d-68632a1654e1)


![image](https://github.com/user-attachments/assets/e2062ea6-f0e9-4847-bbc5-daf9fb1758b9)



# Praktikum 6 – Upload File Gambar


***Tujuan***

- Memahami konsep dasar file upload pada aplikasi web.

- Mampu mengimplementasikan upload gambar ke server menggunakan CodeIgniter 4.

- Melanjutkan fungsionalitas aplikasi artikel dari praktikum sebelumnya.


**Langkah-Langkah Implementasi**

*1. Update Method add() di Artikel.php*

Tambahkan proses upload gambar ke method add() di app/Controllers/Artikel.php:

![image](https://github.com/user-attachments/assets/c0e6ff53-9833-48a6-85ec-ac33bdaf0ebc)


*2. Tambahkan Input Gambar di Form*

Edit file app/Views/artikel/form_add.php. Tambahkan field berikut:

![image](https://github.com/user-attachments/assets/3ec520d0-9f02-4634-884d-20fcec728552)


Dan ubah tag form-nya agar mendukung upload file:

![image](https://github.com/user-attachments/assets/da301d1b-75e6-4177-a9d9-61592e98ac9c)


*3. Buat Folder Tujuan Upload*

Buat folder public/gambar/ jika belum ada, agar gambar bisa disimpan dengan benar:"mkdir public/gambar"

Pastikan folder gambar/ memiliki permission tulis (write) agar tidak error saat upload.


![image](https://github.com/user-attachments/assets/f4bd5258-cae8-4a1e-8422-364d3e533db5)


# Praktikum 7 - Relasi Tabel dan Query Builder


**Tujuan**

- Memahami konsep relasi antar tabel (One-to-Many).

- Mengimplementasikan foreign key dalam database.

- Melakukan join antar tabel menggunakan Query Builder di CodeIgniter 4.

- Menampilkan data yang saling terhubung dari tabel relasi di tampilan (View).

***Langkah-Langkah Implementasi***

*1. Membuat Tabel kategori*

![image](https://github.com/user-attachments/assets/64a07973-1c94-4cf6-b893-a56ed3e15b6f)

*2. Menambahkan Foreign Key di Tabel artikel*

![image](https://github.com/user-attachments/assets/08ee4a4f-6278-4406-80db-5edef49c15fc)

![image](https://github.com/user-attachments/assets/344be1f0-b188-4c07-9ff7-af517dac8fbb)



*3. Model KategoriModel*

![image](https://github.com/user-attachments/assets/df4e1b10-558e-42f9-898a-c266340c3884)


*4. Modifikasi ArtikelModel*

Menambahkan method untuk join dengan tabel kategori:

![image](https://github.com/user-attachments/assets/a7658d64-ebb1-4cde-83ce-38468941d59c)


*5. Update Artikel.php Controller*

- Menggunakan method getArtikelDenganKategori().

- Menambahkan filter pencarian dan filter kategori.

- Mengimplementasikan fitur tambah, edit, dan hapus artikel beserta kategorinya.

*6. Perubahan di View*

- index.php: Menampilkan artikel beserta nama kategori.

- admin_index.php: Filter berdasarkan kategori, pencarian, dan pagination.

- form_add.php & form_edit.php: Dropdown pilihan kategori saat tambah/edit artikel.


![image](https://github.com/user-attachments/assets/6d372d7d-ec2b-4404-8c1f-8ca1ef6b2e51)


# Praktikum 8 - AJAX (Asynchronous JavaScript and XML)

**Tujuan Praktikum:**

- Memahami konsep dasar AJAX dan cara kerjanya.

- Mengimplementasikan AJAX di CodeIgniter 4 untuk pengambilan dan penghapusan data.

- Melatih kemampuan debugging dan interaktivitas aplikasi web.



***Apa itu AJAX?***

  AJAX adalah teknik yang memungkinkan halaman web untuk mengambil atau mengirim data ke server tanpa melakukan reload halaman secara keseluruhan. Hal ini menjadikan web terasa lebih dinamis, cepat, dan interaktif.


**Cara Kerja AJAX:**

1. Event Trigger: Pengguna menekan tombol atau mengetik.

2. Request Dikirim: JavaScript (biasanya via jQuery) mengirimkan request (GET/POST) ke server.

3. Server Memproses: Server menjalankan proses (ambil data, delete, dll).

4. Respon Diterima: Server mengembalikan data (biasanya format JSON).

5. Update Tampilan: JavaScript mengupdate bagian halaman tanpa reload.


**Langkah Praktikum:**

*1. Menambahkan jQuery*

Unduh jQuery dan simpan di folder:

![image](https://github.com/user-attachments/assets/7315f5b3-d282-402b-9c6c-f19ac01409e6)


*2. Membuat Controller AjaxController*

![image](https://github.com/user-attachments/assets/36199014-0c9b-45c3-963a-faa4b358765d)


 *3. Membuat View ajax/index.php*
 
Berisi tampilan tabel + AJAX load:

![image](https://github.com/user-attachments/assets/4c529212-64a3-44cd-84a1-49ff47023d3e)

![image](https://github.com/user-attachments/assets/1d03e1e8-d0f3-4ad4-af4d-a836cee709dc)

![image](https://github.com/user-attachments/assets/91556b67-7eb8-4a3a-a4ab-c16c919b8591)


**Hasil Uji Coba**

- Data dimuat otomatis via AJAX
- Tombol hapus mengirim request DELETE tanpa reload halaman
- Tabel langsung terupdate setelah hapus data

![image](https://github.com/user-attachments/assets/eaded62b-e950-4603-a6b4-316a8f66f383)


#  Praktikum 9 – Implementasi AJAX Pagination dan Search 


**Tujuan**

- Memahami konsep dasar penggunaan AJAX untuk fitur pencarian dan paginasi.

- Mengimplementasikan AJAX agar tampilan halaman tidak melakukan reload penuh.

- Meningkatkan performa dan user experience (UX) aplikasi web.


 **Langkah Implementasi**
 
1. Modifikasi Controller: Artikel::admin_index()

    ![image](https://github.com/user-attachments/assets/fcac21bc-c144-445e-b538-d0cc46e8e68c)

    - Mengembalikan data dalam format JSON jika request berasal dari AJAX.

    - Jika bukan AJAX, tampilkan view seperti biasa.

2. Ubah View admin_index.php

    ![image](https://github.com/user-attachments/assets/c8bfac64-ccc2-4ab0-9f17-b8f5deb20cf0)

    Semua data tabel artikel dan navigasi pagination akan di-render melalui jQuery.


3. Tambahkan Script AJAX (jQuery)

    ![image](https://github.com/user-attachments/assets/c5cef2b8-c90a-458c-9881-4c91a1a2e279)

***Hasil Uji Coba***

![image](https://github.com/user-attachments/assets/84c873a0-3762-4933-b017-126473ee9df4)


# Praktikum 10: REST API

**Tujuan Praktikum**

  - Memahami konsep dasar API dan RESTful.

  - Mampu membuat REST API menggunakan CodeIgniter 4.

  - Mampu menghubungkan aplikasi dengan REST Client seperti Postman untuk pengujian


***Apa itu REST API?***

REST (Representational State Transfer) adalah arsitektur standar dalam pengembangan API (Application Programming Interface). API berfungsi sebagai jembatan antara dua aplikasi agar bisa saling bertukar data.


***Analogi REST API:***

REST API seperti daftar menu restoran. Client (pelanggan) hanya dapat memesan apa yang tersedia, meskipun server (koki) bisa memasak berbagai hal lainnya.

*REST API:*

  - Menggunakan HTTP request seperti GET, POST, PUT, dan DELETE.

  - Biasanya menggunakan format data JSON.

  - Memudahkan integrasi antar-platform (contoh: backend PHP ↔ frontend Vue.js).

**Tools yang Digunakan**

  1. Text Editor: Visual Studio Code (VSCode)

  2. Web Server: Apache (XAMPP/htdocs)

  3. REST Client: Postman

  4. Framework: CodeIgniter 4


**Langkah-langkah Praktikum**

1. Download postman : https://www.postman.com/downloads/
2.  Membuat REST Controller
   
   Buat file Post.php di app/Controllers/:

   ![image](https://github.com/user-attachments/assets/59ac081d-af93-4995-bf68-dde53e0c6480)
  ![image](https://github.com/user-attachments/assets/e8bdbfd1-2f3d-4ff4-8ceb-c367f08b112c)
  ![image](https://github.com/user-attachments/assets/54141fd6-4d05-456f-ad98-089958f042d0)

3.  Konfigurasi Routing
   
Edit file app/Config/Routes.php:

  ![image](https://github.com/user-attachments/assets/06f8db27-5af4-44a3-ab71-7a747edeac2b)

  Untuk mengecek route nya jalankan perintah berikut:
  
  *php spark routes*

  Selanjutnya akan muncul daftar route yang telah dibuat.

![image](https://github.com/user-attachments/assets/a020b124-ff74-4a0f-94f1-04e456d0c98b)

**Testing REST API CodeIgniter**
  Buka aplikasi postman dan pilih create new → HTTP Request
  
![image](https://github.com/user-attachments/assets/628fd9c0-10b6-4ea6-a6ba-f1df39f7af93)


**Menampilkan Semua Data**

Pilih method GET dan masukkan URL berikut:
http://localhost:8080/post

Lalu, klik Send. Jika hasil test menampilkan semua data artikel dari database, maka pengujian

![image](https://github.com/user-attachments/assets/23307201-ffb0-41c4-8fbe-e0e93f1988bf)

**Menampilkan Data Spesifik**

Masih menggunakan method GET, hanya perlu menambahkan ID artikel di belakang URL
seperti ini:

http://localhost:8080/post/5 (Bebas artikel mana yg mau di tampilkan)

Selanjutnya, klik Send. Request tersebut akan menampilkan data artikel yang memiliki ID
nomor 5 di database.

![image](https://github.com/user-attachments/assets/564a4f3d-1aad-4f78-81f5-cb7d3f586a8e)

**Mengubah Data**

Untuk mengubah data, silakan ganti method menjadi PUT. Kemudian, masukkan URL artikel
yang ingin diubah. Misalnya, ingin mengubah data artikel dengan ID nomor 5, maka masukkan
URL berikut:

http://localhost:8080/post/5

Selanjutnya, pilih tab Body. Kemudian, pilih x-www-form-uriencoded. Masukkan nama
atribut tabel pada kolom KEY dan nilai data yang baru pada kolom VALUE. Kalau sudah,
klik Send

![image](https://github.com/user-attachments/assets/71fa38ef-e9fb-4a2b-9328-350db32697fe)

**Menambahkan Data**

Anda perlu menggunakan method POST untuk menambahkan data baru ke database.
Kemudian, masukkan URL berikut:

http://localhost:8080/post

Pilih tab Body, lalu pilih x-www-form-uriencoded. Masukkan atribut tabel pada kolom KEY
dan nilai data baru di kolom VALUE. Jangan lupa, klik Send

![image](https://github.com/user-attachments/assets/ed6e1507-5479-4bcd-a681-20c9f2514154)

**Menghapus Data**

Pilih method DELETE untuk menghapus data. Lalu, masukkan URL spesifik data mana yang
ingin di hapus. Misalnya, ingin menghapus data nomor 3, maka URL-nya seperti ini:

http://localhost:8080/post/3

Langsung saja klik Send, maka akan mendapatkan pesan bahwa data telah berhasil dihapus dari
database

![image](https://github.com/user-attachments/assets/58b42f9e-c5b1-4bc8-8311-70087016989d)


# Praktikum 11 - VueJS 3

 **Tujuan**
 
  1. Memahami konsep dasar REST API dan integrasi frontend-backend.

  2. Mampu membuat aplikasi frontend menggunakan VueJS 3.

  3. Mampu menghubungkan frontend ke backend CodeIgniter 4 REST API.


**Teknologi yang Digunakan**

  - VueJS 3 (via CDN)

  - Axios untuk komunikasi API (GET, POST, PUT, DELETE)

  - HTML + CSS untuk struktur dan tampilan

  - CodeIgniter 4 sebagai backend REST API

**Struktur Folder**
![image](https://github.com/user-attachments/assets/67718543-7ba5-4127-8d0c-e35dfc722b8f)

**Persiapan**

1. Buat folder lab8_vuejs di dalam htdocs atau direktori root server lokal.

2. Tambahkan VueJS & Axios dari CDN ke dalam file index.html:

![image](https://github.com/user-attachments/assets/93d1e18c-9568-4cad-acd4-9c70dfeda85e)

***index.html***

![image](https://github.com/user-attachments/assets/e5cfb602-9f24-4c57-91a0-02bc62ad1daa)
![image](https://github.com/user-attachments/assets/dd8af383-6a40-4319-8378-10ec674d1975)
![image](https://github.com/user-attachments/assets/e3e7b835-b188-4861-8a1c-35dd4f1d5499)
![image](https://github.com/user-attachments/assets/62765a99-738f-43d5-b4c3-267eb47c2bf8)


***app.js***

![image](https://github.com/user-attachments/assets/ba4fe0e4-982a-46cc-8950-b95cc4b378b0)
![image](https://github.com/user-attachments/assets/3fa3b5c0-88f2-425b-bae5-986376d9a148)
![image](https://github.com/user-attachments/assets/dc82a1b5-06d3-4a8f-9d36-71d617e8863a)


![image](https://github.com/user-attachments/assets/06a32fe1-bf75-445e-8d70-e5bd6a5e6011)

***style.css***

![image](https://github.com/user-attachments/assets/1b3e77dc-7389-4c1f-8988-d3f4bb05d3ce)
![image](https://github.com/user-attachments/assets/9be8750f-0dcc-4be7-a3ce-c58dc33b1477)
![image](https://github.com/user-attachments/assets/be964384-2773-4977-a6bf-513ea53eb1dc)
![image](https://github.com/user-attachments/assets/58304883-6f1d-4cff-995a-40b545af3edb)
![image](https://github.com/user-attachments/assets/e732411f-e2c8-4444-8603-d6bbba99cb9a)

***Hasil Akhir***

![image](https://github.com/user-attachments/assets/8de58b73-c87a-4989-9f69-76d4d85aee6b)

![image](https://github.com/user-attachments/assets/a2338f4d-0aff-48a1-87dc-7a45c8ebdf97)








