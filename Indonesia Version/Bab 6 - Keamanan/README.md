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



### 6.4 Compliance (Kepatuhan)

### 6.5 Denial-of-Service

