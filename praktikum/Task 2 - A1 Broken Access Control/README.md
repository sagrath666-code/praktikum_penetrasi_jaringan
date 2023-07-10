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

34 Common Weakness Enumerations (CWEs) memetakan Broken Access Control lebih banyak terjadi pada aplikasi dibandingkan kategori lainnya. Penyerang dan peretas dapat mengakses sebuah sistem ketika autentikasi dan pembatasan akses tidak diterapkan dengan baik. Dengan kata lain, Broken Access Control memungkinkan entri yang tidak sah yang dapat mengakibatkan kerentanan data dan file yang bersifat sensitif. Kontrol akses yang lemah terkait manajemen kredensial dapat dihindari dengan metode coding yang unik dan tindakan khusus seperti mematikan akun administratif dan penggunaan autentikasi multi-faktor.

![Screenshot](images/0.png)

Gambar diatas menjelaskan bahwa user dapat mengakses pribadi pada server dengan Access Control List. Tetapi jika Access Control List tersebut tidak menghandle beberapa enpoint, maka orang lain atau hacker dapat mengakses data user tersebut pada server. 

### A. Forged Feedback   

Kita akan menambahkan feedback kepada toko dengan username sebagai pengguna lain

1. Pergi kehalaman feedback /#/contract untuk memberikan feedback dan submit feedback tersebut

    ![Screenshot](images/1.png)

2. Pergi ke burp suite, pada tab proxy > HTTP History, cari endpoint dengan methode POST yang digunakan untuk mengupdate data feedback

    ![Screenshot](images/2.png)

    Perhatikan data response pada endpoint tersebut bahwa terdapat “UserId” dengan data null, yang menandakan bahwa user yang membuat feedback adalah user anonymous.

3. Langkah selanjutnya, klik kanan pada request, lalu klik send to repeater

    ![Screenshot](images/3.png)

4. Selanjutnya, pergi ke tab repeater, lalu tambahkan data baru Bernama “UserId” dan berikan angka pada data “UserId” tersebut lalu klik tombol send

    ![Screenshot](images/4.png)

5. Muncul pesan response success dengan “UserId” orang lain tanpa login

    ![Screenshot](images/5.png)

### B. Forged Feedback   

Posting ulasan produk sebagai pengguna lain atau edit ulasan pengguna yang sudah ada

1.	Login as admin first using injection

    ![Screenshot](images/6.png)

2.	Review produk

    ![Screenshot](images/7.png)

3.	Buka burp suite lalu check endpoint terakhir pada HTTP History dengan method PUT dan kirim ke repeater

    ![Screenshot](images/8.png)

4.	Ubah request body, dengan mengubah “author” menjadi email pengguna lain yang terdaftar lalu submit

    ![Screenshot](images/9.png)

5.	Muncul pesan berhasil menambahkan review product menggunakan user lain

    ![Screenshot](images/10.png)
    <br>
    ![Screenshot](images/11.png)

### C. Manipulate Basket

Masukkan produk tambahan ke keranjang belanja pengguna lain

1.	Register a new user account

    ![Screenshot](images/12.png)

    Belum ada produk pada basket

    ![Screenshot](images/13.png)

2.	Login sebagai user lain selain yang kita daftar sebelumnya semisal admin

3.	Tambahkan 1 produk ke keranjang
    
    ![Screenshot](images/14.png)

4.	Buka burp suite dan check endpoint terakhir untuk mengupdate keranjang lalu kirim ke repeater
    
    ![Screenshot](images/15.png)

5.	Pada repeater ubah request body data “BasketId” menjadi double, lalu klik tombol send, maka akan muncul response berhasil menambahkan ke keranjang dengan “BasketId” 6
    
    ![Screenshot](images/16.png)
    <br>
    ![Screenshot](images/17.png)

### D. Product Tempering

1.	Login sebagai admin terlebih dahulu menggunakan injection

2.	Buka burb suite dan cari endpoint search product dan kirim ke repeater

    ![Screenshot](images/18.png)

3.	Endcode “OWASP SSL Advanced Forensic Tool (O-Saft)” sebagai url lalu masukan kedalam url parameter pada repeater yang baru kita kirimkan sebelumnya. Setelah itu klik tombol send

    ![Screenshot](images/19.png)
    <br>
    ![Screenshot](images/20.png)

4.	Dengan menggunakan langkah sebelumnya, kita akan mendapatkan “id” dari produk “OWASP SSL Advanced Forensic Tool (O-Saft)”. Setelah itu, kita buat repeater baru dari repeater search produk ini. Kita ubah url nya, menambahkan header Content-Type dan request body untuk mengupdate deskripsi produk yang memiliki “id” 9. Selanjutnya kita klik tombol send, maka akan muncul response berhasil dan deskripsi yang telah berubah.

    ![Screenshot](images/21.png)
    <br>
    ![Screenshot](images/22.png)
    <br>
    ![Screenshot](images/23.png)