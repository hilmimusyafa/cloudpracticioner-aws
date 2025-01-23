## Bab 6 : Keamanan

### 6.1 Shared Responsibility Model

Shared Responsibility Model adalah model tanggung jawab bersama antara AWS dan pelanggan dalam menjaga keamanan cloud. AWS bertanggung jawab atas keamanan infrastruktur cloud (seperti data center, jaringan, dan hypervisor), sementara pelanggan bertanggung jawab atas keamanan apa yang dijalankan di cloud (seperti sistem operasi, aplikasi, dan data).

Seperti gambar berikut di bawah ini :


1. AWS 

Menjamin keamanan infrastruktur fisik, listrik, jaringan, dan hypervisor. AWS juga memastikan kepatuhan keamanan (compliance) melalui audit pihak ketiga.

2. Pelanggan

Bertanggung jawab atas sistem operasi (termasuk patching), aplikasi yang dijalankan, dan data yang disimpan. Pelanggan juga mengontrol siapa yang bisa mengakses data dan apakah data tersebut dienkripsi.

Intinya, AWS memastikan lingkungan cloud aman, sementara pelanggan mengontrol keamanan konten dan aplikasi mereka di dalam cloud. Ini seperti AWS membangun rumah yang kokoh, dan pelanggan bertugas mengunci pintu dan mengamankan isinya.

### 6.2 Perizinan dan Hak Akses Pengguna dengan AWS Identity and Access Management (AWS IAM)

Pada AWS terdapat diberikan fleksibilitas, yang dapat membantu untuk mengelola akses ke layanan dan sumber daya AWS dengan aman, yang dinamakan AWS IAM (AWS Identity and Access Management) fitur IAM AWS di bagi menjadi :

- Root User
- IAM users
- IAM policies
- IAM groups
- IAM roles

Yang dibahas satu per satu di bawah ini :


#### 6.2.1 Root User

Root User adalah pemilik akun AWS dan memiliki akses penuh ke semua layanan dan sumber daya di akun tersebut. Root dapat membuat, mengubah, menghapus, melakukan apapun itu dan apa saja objek yang ingin di modifikasi. 

Karena root user kuat, biasanya disarankan untuk menggunakan MFA (Multi-Factor Authentication) agar lebih aman, dan juga disarankan untuk tidak tidak menggunakan root user untuk aktivitas sehari-hari, melainkan membuat IAM Users dengan izin terbatas sesuai kebutuhan.

#### 6.2.2 IAM Users

IAM Users adalah entitas yang mewakili seseorang atau pengguna yang dapat berinteraksi dengan layanan dan sumber daya AWS. Setiap IAM user secara default tidak memiliki izin apa pun. Untuk memberikan akses, harus secara eksplisit melampirkan IAM Policies ke user tersebut. IAM Users memungkinkan untuk mengelola akses individu dengan lebih terperinci.

#### 6.2.3 IAM Policies

IAM Policies adalah dokumen JSON yang menentukan izin (Allow/Deny) untuk tindakan tertentu pada sumber daya AWS. Misalnya, dapat membuat policy yang mengizinkan user untuk melihat daftar objek di Amazon S3 bucket tertentu. Prinsip least privilege (memberikan izin minimal yang diperlukan) sangat disarankan untuk menjaga keamanan.

#### 6.3 AWS Organizations

IAM Groups adalah kumpulan IAM Users yang memiliki izin yang sama. Dengan mengelompokkan user ke dalam grup,  dapat mengelola izin secara lebih efisien. 

Misalnya, ada peraturan untuk userA dan userB tak boleh hapus instance, dari pada memasukkan satu satu policies ke 2 user, lebih baik membuat grup (contoh grupA) dengan ketentuan grupA tak boleh menghapus instance, dan setelah di buat userA dan userB tinggal masukkan ke grup tersebut (grupA).

#### 6.2.5 IAM Roles

IAM Roles digunakan untuk memberikan izin sementara kepada user, aplikasi, atau layanan AWS. Berbeda dengan IAM Users, roles tidak memiliki kredensial permanen seperti username dan password. Roles sering digunakan untuk memberikan akses temporer, seperti mengizinkan EC2 instance mengakses S3 bucket atau mengintegrasikan kredensial perusahaan eksternal ke akun AWS.

### 6.3 AWS Organizations

AWS Organizations merupakan layanan yang memungkinkan mengelola beberapa akun AWS swcara terpusat. Dengan AWS Organizations dapat melakukan :

- Manajemen Terpusat : Menggabungkan dan mengelola banyak akun AWS dalam satu organisasi.
- Consolidated Billing : Menggabungkan tagihan dari semua akun anggota ke satu akun utama, termasuk diskon massal.
- Pengelompokan Hierarki Akun : Membuat Organizational Units (OU) untuk mengelompokkan akun berdasarkan departemen, keamanan, atau kebutuhan bisnis. Policy yang diterapkan ke OU akan diwarisi oleh semua akun di dalamnya.
- Kontrol Layanan dan API: Menggunakan Service Control Policies (SCP) untuk membatasi layanan AWS dan tindakan API yang dapat diakses oleh akun anggota.

Contoh Kasus :

Jika memiliki akun terpisah untuk departemen Keuangan, IT, HR, dan Hukum. Dengan AWS Organizations :

- Keuangan dan IT dapat dikelola langsung di organisasi tanpa OU.
- HR dan Hukum dikelompokkan dalam OU yang sama, memungkinkan penerapan policy yang seragam untuk keduanya.

Dengan AWS Organizations, dapat menyederhanakan manajemen akun, meningkatkan keamanan, dan mengoptimalkan biaya.

### 6.4 Compliance (Kepatuhan)

Compliance (Kepatuhan) di AWS mengacu pada pemenuhan standar dan regulasi industri yang berlaku, seperti GDPR (Uni Eropa) atau HIPAA (AS). AWS menyediakan infrastruktur yang memenuhi berbagai standar compliance global, regional, dan industri, sehingga dapat fokus pada memenuhi persyaratan compliance di sisi arsitektur aplikasi.

Layanan AWS untuk Compliance 

1. AWS Artifact

Menyediakan akses ke laporan compliance dan perjanjian online yang membuktikan kepatuhan AWS terhadap standar keamanan dan regulasi. AWS Artifact terdiri dari :

- AWS Artifact Agreements : Untuk meninnjau dan mendatangani perjanjian terkait penggunaan layanan AWS.
- AWS Artifact Reports : Menyediakan laporan audit dari pihak ketiga yang memverifikasi kepatuhan AWS.

2. Customer Compliance Center

Menyediakan informasi, contoh kasus, whitepaper, dan checklist audit untuk membantu memahami dan memenuhi persyaratan compliance.

### 6.5 Denial-of-Service

Denial-of-Service atau Distirbuted Denial-of-Service (DDoS) merupakan upaya serangan untuk membuat website atau aplikasi menjadi tidak bekerja dengan optimal bagi pengguna yang dilakukan secara sengaja. 

Biasanya penyerang dengan teknik Denial-of-Service atau Distributed Denial-of-Service akan menggunakan skenario memperbanyak request palsu ke sebuah server, jadi server tersebut akan bekerja lebih untuk melayanai request itu. Padahal request itu palsu, sehingga performa server akan menurun.

Bedanya Denial-of-Service (DoS) dan Distributed Denial-of-Service (DDoS) :

1. DoS (Denial-of-Service) 

Serangan dari satu sumber yang membanjiri aplikasi dengan traffic, membuatnya tidak bisa melayani pengguna asli.

2. DDoS (Distributed Denial-of-Service)

Serangan dari banyak sumber (biasanya menggunakan bot) yang membanjiri aplikasi dengan traffic masif.

Jenis Serangan DDoS :

1. UDP Flood 

UDP Flood merupakan Membanjiri server dengan data besar menggunakan protokol UDP (misalnya, data cuaca palsu).
Solusi: Gunakan Security Group untuk memblokir traffic yang tidak sah.

2. HTTP Level Attack

HTTP Level Attack merupakan penyerang mengirim permintaan HTTP berulang (misalnya, pencarian produk) untuk membebani server.
Solusi: Gunakan AWS WAF (Web Application Firewall) untuk memfilter traffic berbahaya.

3. Slowloris Attack

Slowloris Attack merupakan Penyerang membuat koneksi lambat ke server, menghabiskan kapasitas server.
Solusi: Gunakan Elastic Load Balancer (ELB) untuk menangani traffic dan mencegah server kewalahan.

Solusi AWS untuk sesorang DDoS :

1. AWS Shield

- AWS Shield Standard : Perlindungan dasar DDoS gratis untuk semua pelanggan AWS.
- AWS Shield Advanced: Layanan berbayar untuk perlindungan DDoS yang lebih canggih, termasuk diagnostik dan mitigasi serangan kompleks.

2. Elastic Load Balancer (ELB) 

Menangani traffic secara efisien dan mencegah server kewalahan.

3. AWS MAF 

Memfilter traffic berbahaya dan melindungi aplikasi dari eksploitasi web.

### 6.6 Layanan Tambahan

1. Enkripsi Data

- Enkripsi at Rest : Melindungi data yang disimpan (misalnya, di DynamoDB) dengan mengubahnya menjadi kode yang tidak terbaca. AWS menggunakan AWS Key Management Service (KMS) untuk mengelola kunci enkripsi.

- Enkripsi in Transit : Melindungi data saat berpindah antara layanan AWS dan klien menggunakan protokol seperti SSL/TLS.

2. AWS Key Management Service (KMS)

- Layanan untuk membuat dan mengelola kunci kriptografi yang digunakan untuk enkripsi dan dekripsi data.

- Memungkinkan kontrol akses terhadap kunci, seperti menentukan IAM users/roles yang dapat mengelola kunci atau menonaktifkan kunci sementara.

3. AWS Web Application FIrewall (WAF)

- Melindungi aplikasi web dari serangan dengan memfilter lalu lintas berbahaya.

- Menggunakan Web ACL untuk memblokir atau mengizinkan permintaan berdasarkan aturan yang Anda tentukan, seperti memblokir alamat IP tertentu.

4. Amazon Inspector

- Layanan otomatis yang memindai aplikasi dan infrastruktur untuk menemukan kerentanan keamanan atau penyimpangan dari praktik terbaik.
- Memberikan laporan temuan keamanan yang diprioritaskan beserta rekomendasi perbaikan.

5. Amazon GuardDuty 

- Layanan deteksi ancaman cerdas yang memantau aktivitas jaringan dan akun AWS untuk mengidentifikasi ancaman seperti alamat IP berbahaya atau perilaku mencurigakan.
- Menggunakan machine learning dan threat intelligence untuk memberikan rekomendasi tindakan berdasarkan temuan.

