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





