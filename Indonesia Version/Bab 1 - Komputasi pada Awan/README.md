## Bab 1 : Komputasi pada Awan

### 1.1 Apa itu Cloud Computing?

// Image 1

Sebelum masuk ke AWS lebih enaknya paham terkait Cloud COmputing dahulu.

Cloud Computing (Komputasi Awan) adalah layanan komputasi awan yang dapat digunakan dan di bentuk sesuai kebutuhan. Konsedp Cloud Computing juga dihargai sesuai dengan pemakaian (pay-as-you-go).

AWS disini menggenkan konsep Komputasi Awan yang kental, dengan didukung banyak hal. Karakteristik Cloud Computing :

1. On-Demand Self-Service : Pengguna dapat mengakses dan mengelola sumber daya komputasi secara mandiri tanpa interaksi langsung dengan penyedia layanan.
2. Broad Network Access : Layanan dapat diakses dari mana saja melalui jaringan (internet) menggunakan berbagai perangkat (laptop, smartphone, dll.).
3. Resource Pooling : Sumber daya komputasi (seperti penyimpanan, memori, dan CPU) dikumpulkan bersama dan dialokasikan secara dinamis ke banyak pengguna.
4. Rapid Elasticity : Kemampuan untuk menambah atau mengurangi sumber daya secara cepat sesuai kebutuhan.
5. Measured Service : Penggunaan sumber daya dipantau dan diukur, memungkinkan model pembayaran "pay-as-you-go" (bayar sesuai pemakaian).

### 1.2 Manfaat Menggunakan Cloud Computing 

- Biaya Efisien : Mengurangi biaya infrastruktur fisik (seperti server dan pusat data) dengan model pembayaran "pay-as-you-go" (bayar sesuai pemakaian).
- Skalabilitas : Mudah menambah atau mengurangi sumber daya sesuai kebutuhan bisnis.
- Fleksibilitas : Akses layanan dari mana saja dan kapan saja melalui internet.
- Kecepatan dan Agilitas : Penyediaan sumber daya secara instan untuk mendukung inovasi dan pengembangan aplikasi lebih cepat.
- Keandalan (Reliability): Layanan cloud menawarkan cadangan data, pemulihan bencana, dan uptime yang tinggi.
- Keamanan : Penyedia cloud menawarkan fitur keamanan canggih untuk melindungi data dan aplikasi.
- Pemeliharaan Otomatis : Penyedia cloud mengelola pembaruan, pemeliharaan, dan peningkatan infrastruktur.
- Kolaborasi yang Lebih Baik: Memungkinkan tim bekerja bersama secara real-time dari lokasi yang berbeda.
- Ramah Lingkungan : Mengurangi jejak karbon dengan mengoptimalkan penggunaan sumber daya.

### 1.4 Cloud Computing vs On-Premise (Tradisional)
 
| **Aspek**                     | **Cloud Computing**                                                             | **On-Premise (Tradisional)**                                          |
| ----------------------------- | ------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| **Biaya Awal**                | Rendah, berbasis **Pay-as-you-go**                                              | Tinggi, perlu investasi hardware & software                           |
| **Biaya Operasional**         | Dibayar sesuai pemakaian, bisa lebih murah dalam jangka panjang                 | Biaya tetap tinggi (pemeliharaan, listrik, staf IT)                   |
| **Skalabilitas**              | **Mudah & cepat**; bisa menambah/mengurangi sumber daya sesuai kebutuhan        | **Terbatas**; perlu membeli dan memasang perangkat keras baru         |
| **Kecepatan Implementasi**    | **Cepat**, layanan bisa di-deploy dalam hitungan menit                          | **Lambat**, perlu pemasangan dan konfigurasi manual                   |
| **Aksesibilitas**             | Bisa diakses dari mana saja dengan internet                                     | Hanya bisa diakses dalam jaringan lokal                               |
| **Keamanan**                  | Penyedia cloud memiliki keamanan tinggi & kepatuhan regulasi                    | Keamanan dikelola sendiri, risiko lebih tinggi jika kurang pengawasan |
| **Manajemen Infrastruktur**   | Dikelola oleh penyedia cloud                                                    | Harus dikelola sendiri (server, storage, jaringan)                    |
| **Pemulihan Bencana**         | Biasanya tersedia opsi backup & recovery otomatis                               | Harus mengatur sendiri sistem backup & recovery                       |
| **Performa**                  | Bisa dioptimalkan dengan otomatisasi & load balancing                           | Bergantung pada kapasitas hardware yang dimiliki                      |
| **Pembaruan & Pemeliharaan**  | Dikelola oleh penyedia layanan cloud                                            | Harus dilakukan manual oleh tim IT internal                           |

Dengan adanya Cloud Computing ini, dapat terbantu dalam menentukan membuat infrastruktur, hanya Luncurkan, Hubungkan, dan Gunakan.

### 1.4 Model Layanan Cloud : IaaS, PaaS, CaaS dan SaaS

Cloud computing memiliki tiga model layanan cloud utama: IaaS (infrastructure as a service), PaaS (platform as a service), dan SaaS (software as a service). Apa itu? Menurut Google, ketiga itu adalah :

1. Infrastructure as a Service (IaaS)

Infrastructure as a Service, atau IaaS, memberikan resource infrastruktur on-demand kepada organisasi melalui cloud, seperti komputasi, penyimpanan, jaringan, dan virtualisasi. 

Pelanggan tidak perlu mengelola, memelihara, atau mengupdate infrastruktur pusat data mereka sendiri, tetapi bertanggung jawab atas sistem operasi, middleware, virtual machines, dan aplikasi atau data apa pun.  

2. Platform as a Service (PaaS)

Platform as a service, atau PaaS, memberikan dan mengelola semua resource hardware dan software untuk mengembangkan aplikasi melalui cloud. 

Developer dan tim operasi IT dapat menggunakan PaaS untuk mengembangkan, menjalankan, dan mengelola aplikasi tanpa harus membangun dan memelihara infrastruktur atau platform sendiri. 

Pelanggan tetap harus menulis kode serta mengelola data dan aplikasi mereka, tetapi lingkungan untuk membangun dan men-deploy aplikasi dikelola dan dipelihara oleh penyedia layanan cloud. 

3. Software as a Service (SaaS)

Software as a service, atau SaaS, menyediakan keseluruhan stack aplikasi, yang mengirimkan seluruh aplikasi berbasis cloud yang dapat diakses dan digunakan pelanggan. 

Produk SaaS dikelola sepenuhnya oleh penyedia layanan dan siap digunakan, termasuk semua update, perbaikan bug, dan pemeliharaan secara keseluruhan. 

Sebagian besar aplikasi SaaS diakses langsung melalui browser web, yang berarti pelanggan tidak perlu mendownload atau menginstal apa pun di perangkat mereka. 

### 1.5 Model Penyebaran untuk Komputasi Awan 

1. Public Cloud

Menurut Microsoft, Cloud Public adalah jenis penyebaran komputasi awan yang paling umum. Sumber daya cloud (seperti server dan penyimpanan) dimiliki dan dioperasikan oleh penyedia layanan cloud pihak ketiga dan dikirim melalui internet. 

Dengan Cloud Public, semua perangkat keras, perangkat lunak, dan infrastruktur pendukung lainnya dimiliki dan dikelola oleh penyedia cloud.

2. Private Cloud

Menurut Microsoft juga, Cloud Private terdiri dari sumber daya komputasi awan yang digunakan secara eksklusif oleh satu bisnis atau organisasi. 

Cloud Private dapat secara fisik terletak di pusat data organisasi di tempat, atau dapat diselenggarakan oleh penyedia layanan pihak ketiga. 

Tetapi di Cloud Private, layanan dan infrastruktur selalu dikelola di jaringan pribadi dan perangkat keras dan perangkat lunak didedikasikan hanya untuk organisasi Anda.

3. Hybrid Cloud

Lagi-lagi dari Microsoft, Hybrid Cloud adalah jenis komputasi awan yang menggabungkan Private Cloud dengan Public Cloud. Hybrid Cloud memungkinkan data dan aplikasi bergerak di antara kedua lingkungan.

Banyak organisasi memilih pendekatan Hybrid Cloud karena keharusan bisnis seperti memenuhi persyaratan peraturan dan kedaulatan data, mengambil keuntungan penuh dari investasi teknologi di tempat, atau menangani masalah latensi rendah.