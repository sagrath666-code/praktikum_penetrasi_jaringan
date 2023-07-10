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
    Dwi Wijayanto (119319)
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

Security Misconfiguration keamanan adalah kelemahan yang paling sering terjadi di antara kelemahan lain di daftar ini. Biasanya kesalahan terjadi jika Anda hanya menggunakan default konfigurasi tanpa melihat kebutuhan website.

### A. Error Handling

memunculkan error, tetapi error yang ditampilkan tidak secara bagus dan konsisten.

1. Nyalakan Burp Suite terlebih dahulu

    ![Screenshot](images/1.png)

2. Selanjutnya buka browser dan pergi ke halaman utama website OWASP Juice Shop

    ![Screenshot](images/2.png)

3. Buka kembali Burp Suite maka akan muncul request baru yaitu /rest/product/search

    ![Screenshot](images/3.png)

4. Masukkan payload /rest/product/search tadi ke repeater lalu ubah enpointnya menjadi text random lalu klik tombol send

    ![Screenshot](images/4.png)

    maka yang terjadi adalah response error 500 atau internal server error yang disini terlihat terdapat error message yang begitu panjangnya dan tidak tertata


### B. Deprecated Interface

Menggunakan antarmuka B2B usang yang tidak dimatikan dengan benar.

1. Pada halaman utama, klik tombol menu di pojok kiri atas untuk memunculkan sidebar. Setelah itu klik complaint

    ![Screenshot](images/5.png)

2. Setelah sudah masuk ke halaman complaint, isikan form yang ada, dan masukkan file dengan format xml

    ![Screenshot](images/6.png)

3. Setelah itu akan muncul challange Deprecated Interface berhasil di selesaikan seperti ini

    ![Screenshot](images/7.png)

4. Jika kita lihat di proxy history pada burp suite, akan muncul error panjang seperti ini

    ![Screenshot](images/8.png)

