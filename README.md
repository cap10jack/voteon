# Apa itu VoteOn ?


VoteOn merupakan aplikasi e-voting berbasis website yang digunakan untuk pemilihan umum kepala desa dikelurahan putat nutug, ciseeng. aplikasi ini didesain secara baik menggunakan css framework bootstrap, dan juga untuk PHP framework yang digunakan pada aplikasi ini adalah Code Igniter 3.

Role pada aplikasi ini terdapat 2 yaitu :
- Admin
- Warga

Admin disini berfungsi untuk melakukan kontrol dan proses adminitrasi dari pemilihan. seperti penginputan calon kepala desa, penginputan data warga yang memilih, proses perhitungan surat suara, dan proses penginputan token yang digunakan untuk memilih.

Warga adalah user biasa yang melakukan proses pemilihan. 



## Komponen Requirements


Beberapa aplikasi yang harus dimiliki untuk menjalankan website ini :
- XAMPP (versi 3.3.0 atau lebih terbaru direkomendasikan).
- Versi PHP 5.6 atau lebih baru.
- Teks Editor jenis apapun (Rekomendasi : Visual Studio Code)
- Web Browser

Notes : diperlukan internet untuk tampilan desain yang lebih baik (karena menggunakan beberapa komponen bootstrap online)


## Proses Installasi


Silahkan download zip file pada github ini secara langsung atau bisa menggunakan git bash command dengan melakukan git clone pada folder htdocs.
```
git clone https://github.com/cap10jack/voteon.git
```

Jika File didownload secara manual silahkan lakukan ekstrak pada folder htdocs, jika menggunakan git bash maka folder otomatis akan terbuat dengan nama voteon. 
*(NOTES : pastikan nama folder bernama **voteon** jika belum, harap mengganti menjadi **voteon**)*
buka folder voteon atau jika menggunakan command seperti berikut :
```
cd voteon
``` 

selanjutnya silahkan buka teks editor dan buka folder application/config/config.php. ganti base_url sesuai dengan port kalian. jika port defaultnya adalah 80, maka tidak perlu mengganti apapun. contoh jika port default :
```php
26: $config['base_url'] = 'http://localhost/voteon/';
```

jika port diganti menjadi 8080 seperti berikut :
```php
26: $config['base_url'] = 'http://localhost:8080/voteon/';
```

jika sudah mengganti file pada config.php selanjutnya anda pergi ke application/config/database.php dan ganti username serta password sesuai milik kalian. jika menggunakan username dan password default maka biarkan saja (tidak perlu diganti).  
```php
79: 'username' => 'root',
80: 'password' => '',
```

setelah itu silahkan buka browser dan ketik phpmyadmin pada laman url.
```
http://localhost/phpmyadmin/ 
```

selanjutnya buat database dengan nama voteon dan import database yang ada pada direktori dengan nama voteon.sql.

jika proses installasi selesai silahkan buka url untuk membuka halaman utama.
```
http://localhost/voteon
```

## Proses Role Warga

halaman utama diperuntukan untuk warga yang melakukan pemilihan. untuk memilih bisa langsung klik navbar e-voting dan masukan NIK serta token.
untuk akun contoh pemilih :
NIK : 1234567891
token : QO912D0

setelah masuk tinggal klik calon kepala desa yang ingin dipilih dan klik ok.

jika ingin mencoba melakukan pemilihan lain, silahkan masuk ke database dengan tabel data_pemilih dan lihat data NIK pada halaman tersebut dengan status yang masih 0 (belum memilih). jika status 1 artinya sudah memilih dan tidak bisa digunakan kembali.

begitu juga untuk token bisa melihat pada tabel data_suara. gunakan token yang statusnya 0 (belum digunakan). jika statusnya 1 artinya sudah digunakan.

kira-kira seperti ini proses yang terjadi jika diurutkan :
- Warga mendapatkan token, kemudian masuk ke website E-Voting
- Pilih menu E-Voting
![1](https://github.com/cap10jack/voteon/blob/master/assets/images/warga-1.png)
- Masukan NIK dan Token yang telah dibagikan
![2](https://github.com/cap10jack/voteon/blob/master/assets/images/warga-2.png)
- Pilih calon kepala desa
![3](https://github.com/cap10jack/voteon/blob/master/assets/images/warga-3.png)
- Konfirmasi pilihan
![4](https://github.com/cap10jack/voteon/blob/master/assets/images/warga-4.png)
- Selesai
![5](https://github.com/cap10jack/voteon/blob/master/assets/images/warga-5.png)

tata cara untuk proses pemilihan warga dibuatkan video tutorialnya dengan link berikut :
[Tata Cara Pemilihan](https://www.youtube.com/watch?v=gMeFZJldKOs>)


## Proses Role Administrasi

Admin merupakan tim teknis dalam pelaksanaan administrasi dan kontrol pemilihan umum VoteOn. untuk halaman admin dapat diakses melalui :
```
http://localhost/voteon/admin
```
login dengan username admin dan password nimda*

yang bisa dilakukan oleh admin adalah :
- Input calon kepala desa
- Input pemilih (Warga)
- Perhitungan suara
- Reset surat suara
- Reset token

untuk penggunaan token, kami melakukan generate token dan sudah kami siapkan dalam bentuk file csv dengan nama token.csv
jika ingin melihat di database voteon dengan nama tabel data_suara.


Tata cara penggunaan admin dibuatkan video tutorialnya dengan link berikut :
[Tata Cara Penggunaan admin](https://youtu.be/UozJc-4YTOU>)

## Keamanan

Sebuah aplikasi yang membutuhkan proses pertukaran data tidak akan baik jika tidak menggunakan keamanan. karena kami menggunakan framework Code Igniter 3, maka terdapat komponen keamanan penting yang digunakan pada aplikasi ini, yaitu :
- Cross-site request forgery (CSRF)
- Form Input Validation
- Password handling
- Escape data sebelum masuk ke database
- URI Security
- Register_globals

## Manfaat dan kegunaan
Manfaat dari aplikasi ini adalah mengurangi proses fisik pada pemilihan umum. Pada proses fisik pemilihan umum, menggunakan biaya dan tenaga yang sangat besar. Contohnya seperti waktu dan tenaga para pemilih menuju tempat pemilihan, penggunaan kertas dan tinta, serta penggunaan sumber daya manusia. Oleh karena itu dengan penggunaan aplikasi VoteOn ini, segala hal akan menjadi lebih mudah yaitu dapat dengan menggunakan komputer atau smartphone dan dapat dilakukan dimana saja. Selain itu, di saat maraknya wabah Covid-19, kita dapat menggunakan teknologi untuk mempermudah proses pemilu menggunakan aplikasi digital.


## Creator

Creator dalam pembuatan aplikasi ini terdapat 3 orang yaitu : 
- [Adiva Fiqri Nugraha](https://github.com/adivafiqri)
- [Gusti Agung](https://github.com/cap10jack)
- [Shakira Putri](https://github.com/shakiraayunda)

## Release file pada link berikut
[Release Full Installer VoteOn](https://github.com/cap10jack/voteon/releases/tag/1.0.1)