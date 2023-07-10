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

Sebelumnya Identification and Authentication Failures dikenal sebagai Broken Authentication. Identifikasi dan autentikasi membantu framework digital sebagai pertahanan awal. Identifikasi melibatkan pengatribusian identitas unik setiap pengguna untuk menggunakan layanan aplikasi. Autentikasi memvalidasi sesi pengguna berdasarkan identitas yang ditetapkan dan kredensial akses. Kegagalan identifikasi dan autentikasi terjadi ketika aplikasi gagal menerapkan fungsi yang terkait dengan identitas pengguna, keaslian, dan manajemen sesi dengan benar. Kegagalan seperti ini sering menyebabkan ancaman tingkat sistem yang terus-menerus dieksploitasi oleh aktor jahat untuk mengambil identitas pengguna, pencurian data, atau kompromi seluruh sistem.

### A. Bjoern's Favorite Pet

Pada percobaan satu ini akan mereset password dari akun OWASP Bjoern via Forgot Password dengan menjawab pertanyaan keamanan yang diberikan oleh sistem.

1. Mencari akun dari user Bjoern pada review salah satu produk di Juice Shop website

    ![Screenshot](images/1.png)

2. Setelah alamat email Bjoern dicopy, pindah ke halaman login, dan klik Forgot your password pada login page karena tidak tahu apa password untuk akun ini

    ![Screenshot](images/2.png)

3. Inputkan email bjoern@owasp.org dan akan tampil pertanyaan keamanan dari akun tersebut yaitu nama hewan favorit nya.

    ![Screenshot](images/3.png)

4. Untuk bisa menemukan nama hewan favorit Bjoern, mencoba mencari di internet dengan keyword “Bjoern’s favorite pet” dan hasil teratasnya adalah sebagai berikut.

    ![Screenshot](images/4.png)

5. Setelah diketahui nama hewan favoritnya adalah Zaya, inputkan pada form lupa password. Ketikkan password baru sesuai keinginan dan klik change. Di sini saya menggunakan password baru: Bjoern

    ![Screenshot](images/5.png)

6. Setelah klik change, akan tampil notifikasi berhasil menyelesaikan challenge

    ![Screenshot](images/6.png)

7. Untuk membuktikan berhasil login atau tidak menggunakan password yang baru, Kembali ke halaman login dan masukkan email dan password yang baru

    ![Screenshot](images/7-1.png)
    ![Screenshot](images/7-2.png)
