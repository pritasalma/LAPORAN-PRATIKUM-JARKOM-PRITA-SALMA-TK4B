# CONFIGURE INITIAL SWITCH SETTINGS

    1.Berikut ini adalah bentuk rangkaiannya (rangkaian yang terdiri dari dua PC dan dua Switch)

![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/b34e7093-55b8-4d5f-a817-79d4a357d31e)

    2. Sebelum memulai kita reset terlebih dahulu

![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/2af01025-53c9-4053-bf5f-ae36a12a6e22)
![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/61874999-6982-4bc6-bc08-35a1ceae000b)

    4. lakukan instruksi berikut ini pada S1 (Switch 1)

Instruksi

**Bagian 1: Verifikasi Konfigurasi Switch Default**

    Langkah 1: Masuk ke mode privileged EXEC.

Anda dapat mengakses semua perintah switch dari mode privileged EXEC. Namun, karena banyak perintah privileged mengonfigurasi parameter operasi, akses privileged harus dilindungi dengan kata sandi untuk mencegah penggunaan yang tidak sah.

Set perintah privileged EXEC mencakup perintah yang tersedia dalam mode user EXEC, banyak perintah tambahan, dan perintah configure melalui mana akses ke mode konfigurasi diperoleh.

  a. Klik S1 dan kemudian tab CLI. Tekan Enter.

  b. Masuk ke mode privileged EXEC dengan memasukkan perintah enable:

![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/a1e6404d-6809-4dd5-a7f1-81f8790845c2)


Perhatikan bahwa prompt berubah untuk mencerminkan mode privileged EXEC.

    Langkah 2: Periksa konfigurasi switch saat ini.

Masukkan perintah show running-config.

![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/51953aea-be75-483d-87c7-7cfdcf8f50fd)


**Bagian 2: Buat Konfigurasi Switch Dasar**

    Langkah 1: Beri nama pada sebuah switch.

Untuk mengonfigurasi parameter pada sebuah switch, Anda mungkin diminta untuk berpindah antara berbagai mode konfigurasi. Perhatikan bagaimana prompt berubah saat Anda menavigasi melalui switch.

![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/8cc1aa54-62b5-4f8d-8dc1-8ad1b7dfdd29)

    Langkah 2: Akses aman ke baris konsol.

Untuk mengamankan akses ke baris konsol, akses mode config-line dan atur kata sandi konsol.

![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/6a68735f-5ef7-4e97-b1b3-a09de29a4bc5)


    Langkah 3: Verifikasi bahwa akses konsol diamankan.

Keluar dari mode privileged untuk memverifikasi bahwa kata sandi port konsol berlaku.

![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/fd0b8a75-34ae-423e-9eef-db06e5e74ed5)


Catatan: Jika switch tidak meminta kata sandi, maka Anda tidak mengonfigurasi parameter login pada Langkah 2.

    Langkah 4: Akses mode privileged aman.

Atur kata sandi enable dan kata sandi ini melindungi akses ke mode privileged.

![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/3b6de087-938a-4142-b7b7-0125d376fd98)

    Langkah 5: Verifikasi bahwa akses mode privileged aman.

  a. Masukkan kembali perintah exit untuk keluar dari switch.

  b. Tekan <Enter> dan Anda sekarang akan diminta kata sandi:

![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/8e5085cd-c209-4741-b68d-0bb8b19dc3c7)


  c. Kata sandi pertama adalah kata sandi konsol yang Anda konfigurasi untuk baris con 0. Masukkan kata sandi ini untuk kembali ke mode user EXEC.

  d. Masukkan perintah untuk mengakses mode privileged.

  e. Masukkan kata sandi kedua yang Anda konfigurasi untuk melindungi mode privileged EXEC.

  f. Verifikasi konfigurasi Anda dengan memeriksa isi file konfigurasi berjalan:

![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/06b6f574-2cb3-481e-9cb1-3858b0f1e2d2)


Perhatikan bahwa kata sandi konsol dan enable keduanya dalam teks biasa. Ini bisa menjadi risiko keamanan jika seseorang melihat dari belakang atau mendapatkan akses ke file konfigurasi yang disimpan di lokasi cadangan.

    Langkah 6: Konfigurasikan kata sandi terenkripsi untuk mengamankan akses ke mode privileged.

Kata sandi enable harus diganti dengan kata sandi rahasia terenkripsi yang lebih baru menggunakan perintah enable secret. Atur kata sandi rahasia enable menjadi itsasecret.

![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/c29f9b4b-2daf-4cd3-b393-e9cb63984712)


Catatan: Kata sandi rahasia enable menggantikan kata sandi enable. Jika keduanya dikonfigurasi pada switch, Anda harus memasukkan kata sandi rahasia enable untuk masuk ke mode privileged EXEC.

    Langkah 7: Verifikasi bahwa kata sandi rahasia enable ditambahkan ke file konfigurasi.

Masukkan perintah show running-config lagi untuk memverifikasi bahwa kata sandi rahasia enable baru dikonfigurasi.

Catatan: Anda dapat mempersingkat show running-config sebagai

![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/fe7da7bd-21b5-468e-b5b7-3222fc172097)


    Langkah 8: Enkripsi kata sandi enable dan konsol.

Seperti yang Anda perhatikan pada Langkah 7, kata sandi rahasia enable dienkripsi, tetapi kata sandi enable dan konsol masih dalam teks biasa. Sekarang kita akan mengenkripsi kata sandi teks biasa ini menggunakan perintah service password-encryption.

![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/72644d37-636d-4d13-90a1-485b3af06e19)



**Bagian 3: Konfigurasikan Banner MOTD**

    Langkah 1: Konfigurasikan pesan hari ini (MOTD) banner.

Set perintah Cisco IOS mencakup fitur yang memungkinkan Anda mengonfigurasi pesan yang dili
adapun orang yang masuk ke switch melihat. Pesan-pesan ini disebut pesan hari ini, atau banner MOTD. Sisipkan teks banner dalam tanda kutip atau gunakan delimiter yang berbeda dari setiap karakter yang muncul dalam string MOTD.

![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/a946f737-bbfd-4ca7-b7b4-2ce6098a1105)


**Bagian 4: Simpan dan Verifikasi File Konfigurasi ke NVRAM**

    Langkah 1: Verifikasi bahwa konfigurasi akurat menggunakan perintah show run.

Simpan file konfigurasi. Anda telah menyelesaikan konfigurasi dasar switch. Sekarang cadangkan file konfigurasi berjalan ke NVRAM untuk memastikan bahwa perubahan yang dilakukan tidak hilang jika sistem di-boot ulang atau kehilangan daya.

![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/23a8cdef-9378-4f43-bfea-7c7a4eb7b4f1)


**Bagian 5: Konfigurasi S2**

Anda telah menyelesaikan konfigurasi di S1. Sekarang Anda akan mengonfigurasi S2. Jika Anda tidak dapat mengingat perintah-perintahnya, lihat Bagian 1 hingga 4 untuk bantuan.

Konfigurasikan S2 dengan parameter berikut:

Buka Jendela Konfigurasi untuk S2

  a. Nama Perangkat: S2

  b. Lindungi akses ke konsol menggunakan kata sandi letmein.

  c. Konfigurasikan kata sandi enable menjadi c1$c0 dan kata sandi rahasia enable menjadi itsasecret.

  d. Konfigurasikan pesan yang sesuai untuk mereka yang login ke switch.

  e. Enkripsi semua kata sandi teks biasa.

  f. Pastikan konfigurasi benar.

  g. Simpan file konfigurasi untuk menghindari kehilangan jika switch dimatikan.

    5. Setelah kedua PC tersambungkan dengan Switch berikut ini tampilannya

  ![image](https://github.com/pritasalma/PRATIKUM-JARKOM-PRITA-SALMA-TK4B/assets/126141683/2a766277-fd60-44ad-85b9-b68136304d53)

