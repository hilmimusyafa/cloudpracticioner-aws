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

Amazon EFS adalah sistem file yang memungkinkan banyak instance (seperti EC2) mengakses data yang sama secara bersamaan.

### 5.4 Amazon Relational Database Service (Amazon RDS)

Amazon Relational Database Service (Amazon RDS) adalah layanan database terkelola (managed database service) yang disediakan oleh AWS. Layanan ini memudahkan pengguna untuk menyiapkan, mengoperasikan, dan mengelola database relasional di cloud. 

Amazon RDS adalah layanan yang terkelola dan mendukung 6 (enam) mesin database, di antaranya:
- Amazon Aurora
- PostgreSQL
- MySQL
- MariaDB
- Oracle Database
- Microsoft SQL Server

