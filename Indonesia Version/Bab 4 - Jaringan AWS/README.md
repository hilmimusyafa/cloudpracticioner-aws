## Bab 4 : Jaringan di AWS

### 4.1 Macam Konektivias di AWS

#### 4.1.1 Amazon Virtual Private Cloud (Amazon VPC)

Amazon Virtual Private Cloud (Amazon VPC) merupakan jaringan pribadi virtual di AWS yang mengisolasi sumber daya AWS (contoh AWS EC2). Contohnya sesama instance EC2 ingin saling terkoneksi, maka akan menggunakan Amazon Virtual Private Cloud (Amazon VPC).

Untuk fungsi lebih lanjutnya seperti berikut :
- Membuat bagian terisolasi dari AWS Cloud.
- Mengelompokkan sumber daya ke dalam subnet (bagian dari VPC) untuk mengontrol akses (publik atau privat).

Pada Amazon VPC terdapat dua area atau subnet, yaitu :
- Subnet Publik: Untuk sumber daya yang terhubung ke internet (seperti website).
- Subnet Privat: Untuk sumber daya internal (seperti database atau aplikasi HRD).

#### 4.1.2 Internet Gateway (IGW)

Internet Gateway (IGW) merupakan komponen yang memungkinkan traffic internet untuk masuk dan keluar dari VPC. Internet Gateway (IGW) dapat menghubungkan sumber daya di VPC ke internet. Contoh : Jika memiliki website yang perlu diakses publik, IGW memungkinkan traffic internet mengalir ke subnet publik di VPC.

#### 4.1.3 Virtual Private Gateway (VPG)

Virtual Private Gateway (VPG) merupakan gateway yang memungkinkan koneksi aman antara jaringan privat (seperti data center on-premise) dan VPC melalui VPN (Virtual Private Network). VPG Membuat koneksi terenkripsi antara jaringan internal perusahaan dan VPC. Cocok untuk aplikasi yang memerlukan keamanan tinggi.

#### 4.1.4 AWS Direct Connect

AWS Direct Connect merupakan layanan AWS yang menyediakan koneksi fiber privat dan terdedikasi antara data center Anda dan VPC. Jadi, secara langsung terkoneksi ke layanan jaringan AWS. Untuk membangun koneksi tersebut, diperlukan berpartner dengan mitra Direct Connect yang tersedia.

### 4.2 Subnet dan Netwsork Access Control List

#### 4.2.1 Subnet

Subnet merupakan sebuah bagian VPC yang menegelompokkan sumber daya berdsarkan ketentuan atau kebutuhan operasional/ jarigan tertentu. Subnnet di AWS terdapat dua jenis yaitu Publik dan Privat

- Subnet Publik : Merupakan kelompok sumber daya yang bisa di akses oleh jaringan publik (atau mungkin bisa di sebut merupakan kelompok yang sumber dayanya bisa di akses oleh orang luar), Contohnya seperti Website dan Toko Online.
- Subnet Privat : Merupakan kelompok sumber daya yang bisa di akses oleh jaringan khusus, sehingga tidak bisa semabrang di akses oleh beberapa orang (atau hanya beberapa kelompok yang dapat mengakses sumber daya tersebut).

#### 4.2.2 Network Access Control List (Network ACL)

Network Access Control List (Network ACL) merupakan sebuah komponen firewall virtual yang memerilksa izin paket yang akan masuk subnet, apakah paket tersebut memiliki izin untuk masuk ke subnet berdasarkan dari siapa itu paket dan metode komunikasi dengan sumber daya yang ada di subnet.

Jika paket diizinkan maka sistem akan mengarahkan ke subnet yang dituju, jika tidak diizinkan atau ditolak maka paket akan di buang dan proses paket tidak akan di lanjutkan ke sistem.

#### 4.2.3 Security Group

Mirip seprti Network ACL, Security Group merupakan komponen firewall virtual yang memeriksa izin paket yang akan masuk atau keluar, tetapi security group ini berjalan di tingkat instance yang berbeda dengan Network ACL.

Berikut Perbedaannnya : 

| Aspek      |           | Network ACL                                     | Security Group                       |
| ---------------------- | ----------------------------------------------- | ------------------------------------ |
| Cakupan                | Tingkat Subnet                                  | Tingkat instance (misalnya, EC2)     |
| Sifat                  | Stateless(tidak mengingat status paket)         | Stateful (mengingat status paket)    |
| Aturan Default         | Mengizinkan semua traffic                       | Menolak semua traffic masuk          |
| Pemeriksaan Traffic    | Memeriksa setiap paket yang melintas            | Hanya memeriksa traffic masuk        |

### 4.3 Jaringan Global

#### 4.3.1 Amazon Route 53

Amazon Route 53 merupakan Layanan DNS yang highly available (sangat tersedia) dan scalable (dapat diskalakan) di AWS. DNS itu apa? Domain Name System (DNS) merupkana sebuah sistem yang dikhususkan untuk menerjemahkan alamat IP server yang berawal angka menjadi alamat website dengan huruf. 

Sebagai contoh, IP Server memiliki IP Addrerss 89.76.98.112, dibandingkan untuk menghafalkan alamat tersebut, lebih baik menghafalkannya dengan nama contoh example.com, dan disitulah DNS hadir, DNS merubah dari alamat IP (89.76.98.112) menjadi alamat yang mudah diingat (example.com).

Pada Amazon Route 53 mengarahkan traffic ke infrastruktur AWS (seperti EC2 instance, load balancer) atau infrastruktur di luar AWS, dan mendukung berbagai kebijakan perutean (routing policies), seperti:
- Latency-based routing: Mengarahkan traffic ke Region dengan latensi terendah.
- Geolocation DNS: Mengarahkan traffic berdasarkan lokasi geografis pengguna.
- Weighted round robin: Membagi traffic secara proporsional berdasarkan bobot yang ditentukan.

### 4.3.2 Amazon CloudFront

Sebelumnya sudah ada penjelasan terkait Amazon Cloudfront tetapi di ulas kembali karena bagian dari Jaringan Global, yang dimana Amazon CloudFront adalah Layanan Content Delivery Network (CDN) yang mengirimkan konten (seperti data, video, aplikasi, atau API) ke pelanggan di seluruh dunia dengan latensi rendah dan kecepatan tinggi.

Fungsi Amazon CloudFront yaitu menyimpan salinan konten di Edge Locations (lokasi cache yang tersebar di seluruh dunia) dan mengirimkan konten dari Edge Location terdekat ke pengguna, sehingga mengurangi latensi.

