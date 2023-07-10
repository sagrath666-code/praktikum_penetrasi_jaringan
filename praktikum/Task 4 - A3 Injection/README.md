## Cover

<h3 align="center">
    <b>Praktikum Pengujian Penetrasi Jaringan</b><br>
    OWASP Juice Shop<br>
     
</h3>
<br>
<p align="center">
  <img src="../../public/logo_sttal.png" alt="Logo STTAL" width="200">
</p>
<br>
<p align="center">
    Dosen Pembimbing :<br>
    Moh. Iman Prajitno, S.E., M.T.
</p>
<br>
<p align="center">
    Disusun Oleh:<br>
    Dwi Wijayanto (115976)
</p>
<br>
<p align="center">
    <b>
        JURUSAN D3 TEKNIK INFORMATIKA <br>
        KONSENTRASI PERTAHANAN CYBER <br>
        ANGKATAN D3 - 16 <br> 
        SEKOLAH TINGGI TEKNOLOGI ANGKATAN LAUT <br>
        2023
    </br>
</p>
<br>

## Laporan

SQL Injection (SQLi) merupakan jenis serangan injeksi yang memungkinkan untuk mengeksekusi statement SQL yang berbahaya. Statement yang digunakan ini dapat mengontrol server database di belakang aplikasi web.

Hacker dapat melakukan otentikasi dan otorisasi halaman web atau aplikasi web dan mengambil konten dari seluruh database SQL. Mereka juga dapat menggunakan SQL Injection untuk menambah, mengubah, dan menghapus catatan dalam database.

Serangan SQL Injection ini dapat menarget semua website yang memanfaatkan SQL database, seperti MySQL, PostgreSQL, SQL Server, dan lainnya.

### A. Bender Login

Bender login adalah login menggunakan akun email bender@juice-sh.op menggunakan injection

1. Masuk kehalaman login dengan melakukan klik account pada bagian navbar lalu klik login

    ![Screenshot](images/1.png)

2. Selanjutnya pada halaman login ini masukkan email bender@juice-sh.op dan dengan password diisi dengan inputan acak. Untuk melakukan injection tambahkan ' -- yang dimana maksud dari inputan tersebut adalah digunakan untuk menonaktifkan argumen query sql setelahnya atau melakukan comment jadi kita dapat menonaktifkan kondisi pengecekan passwordnya

    ![Screenshot](images/2.png)

3. Submit login form, maka kita akan berhasil masuk sebagai user bender

    ![Screenshot](images/3.png)
    ![Screenshot](images/4.png)


### B. Jim Login

Sama seperti Bender login, Jim Login adalah login menggunakan akun email jim@juice-sh.op menggunakan injection

1. Pada web OWASP Juice Shop, pergi kehalaman customer feedback yang berada pada sidebar menu web

    ![Screenshot](images/1.png)

2. Selanjutnya pada halaman login ini masukkan email jim@juice-sh.op dan dengan password diisi dengan inputan acak. Untuk melakukan injection tambahkan ' OR '1'='1 yang dimana maksud dari inputan tersebut adalah digunakan untuk menambahkan kondisi jika 1=1 maka kondisi return pasti sama dengan true, maka login akan berhasil dilakukan

    ![Screenshot](images/5.png)

3. Submit login form, maka kita akan berhasil masuk sebagai user jim
    ![Screenshot](images/6.png)

