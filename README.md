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

Dan Begini Lah Hasil Akhirnya :)


![image](https://github.com/user-attachments/assets/2d9e1134-1b55-4540-b9ea-7992263b796d)












