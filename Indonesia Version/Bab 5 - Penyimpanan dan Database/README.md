## Bab 5 : Penyimpanan dan Database

### 5.1 Instance Store dan Amazon Elastic Block Store (Amazon EBS)

Di AWS, disaat menjalankan aplikasi, EC2 instance memerlukan akses ke penyimpanan berbassis blok level (block-level storage), yaitu penyimpanan tingkat blok layaknya HDD. Terdapat dua jenis penyimpananu utama, yaitu :

#### 5.1.1 Instance Store

Instance Store adalah penyimpanan block-level storage sementara yang terpasang langsung ke host fisik tempat EC2 instance berjalan. Ketika Instance berjalan, sistem dapat melakukan proses write (menulis) data padanya seperti hard drive pada umumnya.

Namun, jika menghentikan atau mengakhiri sebuah instance, semua data di sana akan terhapus. Karena jika memulai instance dari status stop kemungkinan EC2 instance akan berjalan di host lain, yang dimana instance store volume tersebut berbeda.

#### 5.1.2 Amazon Elastic Block Store (Amazon EBS)

EBS adalah layanan penyimpanan block-level yang persisten dan terpisah dari EC2 instance. EBS volume dapat dipasang ke EC2 instance seperti hard drive virtual. Mirip seperti instance store, tetapi perbedaannya data akan tetap tersedia apabila istance EC2 dimatikan.

Sehingga bisa di simpulkan seperti di bawah ini :

| Fitur                  | Instance Store                                  | Amazon EBS                               |
| ---------------------- | ----------------------------------------------- | ---------------------------------------- |
| Sifat Penyimpanan      | Sementara                                       | Persisten                                |
| Ketahanan Data         | Hilang saat instance dihentikan                 | Tetap ada meskipun instance dihentikan   |
| Penggunaan             | Cache, file sementara                           | Data penting, database, aplikas          |
| Backup                 | Tidak tersedia                                  | Tersedia (EBS Snapshot)                  |

### 5.2 Amazon Simple Storage (Amazon S3)

Amazon S3 merupakan layanan penyimpanan oleh AWS dengan sistem object-level storage yang dirancang untuk menyimpan dan mengambil data dalam jumlah tak terbatas. Pada Amazon S3, data disimpan sebagai objek (file) dalam bentk bucket (direktori). Setiap objek terdiri dari data, metadata, dan key (pengenal unit) dengan ukuran maksimum objek 5 TB.

Fitur - fitur Amazon S3 :
- Versioning: Menyimpan versi sebelumnya dari objek.
- Permission: Mengatur izin akses ke bucket dan objek.
- Object-Level Storage: Saat file diubah, seluruh objek diperbarui (tidak seperti lock-level storage yang hanya memperbarui bagian yang berubah).

Kelas Penyimpanan (Storage Classes) :

a. S3 Standard : Daya tahan tinggi (99.999999999%) dan cocok untuk data yang sering diakses (website, distribusi konten, analitik).
b. S3 Standard-IA (Infrequent Access) : Untuk data yang jarang diakses tetapi memerlukan akses cepat (backup, disaster recovery).
c. S3 One Zone-IA : Menyimpan data di satu Availability Zone (lebih murah, cocok untuk data yang mudah diproduksi ulang).
d. S3 Intelligent-Tiering : Secara otomatis memindahkan objek antara S3 Standard dan S3 Standard-IA berdasarkan pola akses.
e. S3 Glacier : Untuk pengarsipan data dengan akses dalam hitungan menit hingga jam dan Cocok untuk data audit atau compliance.
f. S3 Glacier Deep Archive : Biaya terendah, akses dalam 12-48 jam dan Ideal untuk pengarsipan jangka panjang.

Di Amazon S3, terdapat peraturan yaitu Amzon S3 Lifecycle Policies, yang berisi emungkinkan pemindahan data otomatis antar kelas penyimpanan berdasarkan aturan yang ditentukan. Contoh: Data dipindahkan dari S3 Standard ke S3 Glacier setelah 90 hari.

Dan jika diperhatikan, Amazon S3 terlihat mirip dengan Amazon EBS, tetapi tetap saja berbeda, bisa di perhatiin tabel perbedaan di bawah ini :

| Amazon S3	                                          | Amazon EBS                                                |
| --------------------------------------------------- | --------------------------------------------------------- |
| Object-level storage.	                              | Block-level storage.                                      |
| Cocok untuk file lengkap (gambar, video, dokumen).  |	Cocok untuk data yang sering diubah (database, aplikasi). |
| Skalabilitas tak terbatas.	                      | Ukuran maksimum 16 TB per volume.                         |
| Serverless (tidak perlu EC2 instance).	          | Harus dipasang ke EC2 instance.                           |
| Biaya lebih hemat untuk penyimpanan besar.          |	Biaya lebih tinggi untuk penyimpanan besar.               |

### 5.3 Amazon Elastic File System (Amazon EFS)

Amazon EFS adalah sistem file yang dapat di kelola dan di skalakan, digunakan oleh layanan AWS Cloud dan sumber daya di data center on-premise. Amazon EFS memungkinkan beberapa klien (seperti pengguna, aplikasi, atau server) untuk mengakses data yang sama secara bersamaan. Ini adalah solusi penyimpanan file yang ideal untuk kasus penggunaan di mana banyak sumber daya perlu mengakses data yang sama pada waktu yang bersamaan.

Amazon EFS adalah sistem file yang memungkinkan banyak instance (seperti EC2) mengakses data yang sama secara bersamaan. Kapasitas penyimpanan dapat menyesuaikan secara otomatis (scaling up dan down) sesuai kebutuhan, bahkan hingga petabyte. Data disimpan di beberapa Availability Zone (AZ) dalam satu Region, memastikan ketersediaan dan keandalan tinggi.

Perbedaan dengan Amazon EBS

a. Amazon EBS

- Adalah block storage yang dilampirkan ke satu EC2 instance.
- Hanya tersedia di satu Availability Zone (AZ).
- Tidak dapat diakses oleh beberapa instance secara bersamaan.
- Tidak melakukan scaling otomatis; kapasitas harus disesuaikan manual.

b. Amazon EFS

- Adalah file storage yang dapat diakses oleh banyak instance secara bersamaan.
- Tersedia di beberapa AZ dalam satu Region.
- Melakukan scaling otomatis sesuai kebutuhan.
- Cocok untuk penggunaan bersama (shared access).

### 5.4 Amazon Relational Database Service (Amazon RDS)

Amazon Relational Database Service (Amazon RDS) adalah layanan database terkelola (managed database service) yang disediakan oleh AWS. Layanan ini memudahkan pengguna untuk menyiapkan, mengoperasikan, dan mengelola database relasional di cloud. 

Amazon RDS adalah layanan yang terkelola dan mendukung 6 (enam) mesin database, di antaranya:

- Amazon Aurora
- PostgreSQL
- MySQL
- MariaDB
- Oracle Database
- Microsoft SQL Server

Fitur fitur yang ada di Amazon RDS :

- Automated patching : memperbaiki masalah dengan memperbarui program
- Backup : pencadangan.
- Redundancy : memiliki lebih dari satu instance untuk berjaga-jaga jika instance utama gagal beroperasi.
- Failover : instance lain akan mengambil alih saat instance utama mengalami kegagalan.
- Disaster recovery : memulihkan pascabencana.
- Encryption at rest : enkripsi data saat disimpan.
- Encryption in-transit : enkripsi data saat sedang dikirim dan diterima.

### 5.5 Amazon DynamoDB

Amazon DynamoDB adalah layanan database NoSQL terkelola dan serverless yang dirancang untuk kinerja tinggi, skalabilitas otomatis, dan ketersediaan tinggi. Jadi, mirip seperti Anazon RDS tetapi jika RDS menggunakan sistem SQL, di Amazon DynamoDB menggunakan NoSQL.

Berikut perbedaannya dengan Database Relasional (Amazon RDS)

a. Amazon RDS

- Menggunakan model relasional (SQL) dengan skema tetap.
- Cocok untuk analisis data kompleks dan hubungan antar tabel.
- Memerlukan manajemen skema dan scaling manual.

b. Amazon DynamoDB

- Menggunakan model NoSQL (key-value) tanpa skema tetap.
- Ideal untuk data fleksibel dan aplikasi yang membutuhkan kinerja tinggi.
- Scaling otomatis dan tidak perlu manajemen infrastruktur.

### 5.6 Amazon Redshift

Amazon Redshift adalah layanan data warehouse terkelola oleh AWS yang dirancang untuk analitik big data. Data Warehouse adalah tempat yang dirancang khusus untuk analitik historis dan big data.

Mungkin bertanya, mengapa tidak menggunakan relasional, mungkin bia dilihat perbedaan dengan Amazon RDS :

a. Database Relasional (RDS)

- Cocok untuk operasi read/write real-time.
- Tidak ideal untuk analitik historis atau big data.

b. Amazon Redshift

- Dirancang untuk analitik big data dan business intelligence.
- Menangani kueri kompleks pada data historis yang tidak berubah.

### 5.7 AWS Database Migration Service

AWS Database Migration Service merupakan layanan AWS yang bisa digunakan apabila sebelumnya sudah memiliki database on-premise atau priovider cloud lain dan ingin migrasi dari sistem on-premise atau provider cloud lain ke sistem AWS. AWS Database Migration Service mendukung sistem SQL (relasional), dan NoSQL (non relasional).

Dengan menggunakan AWS Database Migration Service, dapat diperhatikan :

- Database sumber tetap beroperasi selama proses migrasi.
- Downtime diminimalkan untuk aplikasi yang bergantung pada database tersebut.
- Database sumber dan target tidak harus bertipe sama.

Pada AWS Database Migration Service memiliki beberapa jenis migrasi :

a. Migrasi Homogen

- Database sumber dan target bertipe sama (contoh: MySQL ke Amazon RDS for MySQL).
- Prosesnya mudah karena struktur skema dan tipe data sama.

b. Migrasi Heterogen

- Database sumber dan target bertipe berbeda (contoh: Oracle ke Amazon Aurora).
- Menggunakan AWS Schema Conversion Tool untuk mengubah skema dan tipe data sebelum migrasi.

Dan dengan menggunakan migrasi AWS, anda bisa mendapat keunggulan AWS DMS berupa :
- Migrasi Aman dan Cepat : Proses migrasi berjalan lancar dengan downtime minimal.
- Replikasi Berkelanjutan: Mendukung replikasi data untuk disaster recovery atau pemisahan geografis.
- Fleksibilitas: Bisa digunakan untuk migrasi, konsolidasi database, atau replikasi.

### 5.8 Layanan AWS Lainnya

1. Amazon DocumentDB

Layanan database dokumen yang kompatibel dengan MongoDB, cocok untuk manajemen konten, katalog, atau profil pengguna.

2. Amazon Neptune

Layanan graph database untuk aplikasi dengan data yang sangat terhubung, seperti jejaring sosial, rekomendasi, atau deteksi penipuan.

3. Amazon Managed Blockchain

Layanan untuk membuat dan mengelola jaringan blockchain terdesentralisasi, ideal untuk rantai pasokan atau catatan finansial yang aman.

4. Amazon Quantum Ledger Database (Amazon QLDB)

Database ledger terpusat yang tidak dapat diubah, cocok untuk audit transaksi yang dapat diverifikasi.

5. Amazon ElastiCache

Layanan caching untuk meningkatkan performa baca database dengan Redis atau Memcached.

6. Amazon DynamoDB Accelerator (DAX) 
 
1Lapisan caching khusus untuk DynamoDB yang mempercepat waktu baca data nonrelasional.