## Bab 3 : Infrastruktur Global

### 3.1 Apa itu Infrastuktur Global?

Infrastruktur Global AWS adalah kerangka teknologi yang mendukung layanan cloud AWS di seluruh dunia. Infrastruktur ini dirancang untuk memberikan ketersediaan tinggi, skalabilitas, dan latensi rendah kepada pengguna, terlepas dari lokasi geografis mereka.

Keuntungan Infrastruktur Global AWS :

- Ketersediaan Tinggi: Dengan multiple AZ, aplikasi tetap berjalan meskipun satu AZ mengalami masalah.
- Kepatuhan Regulasi: Data disimpan sesuai dengan hukum lokal, memastikan kepatuhan terhadap regulasi.
- Skalabilitas Global: AWS memungkinkan Anda melayani pelanggan di seluruh dunia dengan latensi rendah.
- Biaya Efisien: Anda hanya membayar sumber daya yang digunakan, dan dapat memilih Region dengan biaya operasional terbaik.

#### 3.1.1 AWS Region

Region adalah kumpulan data center yang terletak di lokasi geografis tertentu (misalnya, Tokyo, Paris, atau Ohio). Data yang disimpan di suatu Region tidak akan meninggalkan Region tersebut kecuali secara eksplisit diizinkan. Ini memastikan kepatuhan terhadap regulasi lokal (data sovereignty).

Ada 4 faktor utama untuk memilih Region
- Compliance (Kepatuhan): Pastikan Region memenuhi persyaratan hukum dan regulasi lokal.
- Proximity (Kedekatan): Pilih Region yang dekat dengan basis pelanggan untuk mengurangi latensi.
- Feature Availability (Ketersediaan Fitur): Beberapa layanan AWS mungkin hanya tersedia di Region tertentu.
- Pricing (Harga): Biaya operasional bisa berbeda antar Region karena faktor seperti pajak dan biaya infrastruktur.

#### 3.1.2 Availability Zones (AZ)

Availability Zone adalah satu atau sekelompok data center yang terpisah secara fisik dalam suatu Region. Setiap AZ memiliki daya, jaringan, dan konektivitas independen. AZ dirancang untuk memastikan ketersediaan tinggi (high availability). Jika satu AZ mengalami kegagalan, aplikasi tetap berjalan di AZ lain. Selalu jalankan aplikasi di setidaknya 2 AZ untuk memastikan ketahanan terhadap bencana atau kegagalan.

#### 3.1.3 High Availability dan Skalabilitas

Beberapa layanan AWS (seperti Elastic Load Balancing) beroperasi di level Region dan sudah dirancang untuk high availability tanpa biaya tambahan. AWS memungkinkan Anda untuk menyesuaikan kapasitas sesuai kebutuhan, baik dengan menambah EC2 instance di AZ yang sama atau di AZ lain.

### 3.2 Edge Locations

Edge Locations adalah Lokasi cache yang tersebar di seluruh dunia, terpisah dari AWS Regions. Edge Locations menyimpan salinan data sementara (cache) untuk mempercepat pengiriman konten ke pelanggan.

Edge Locations muncul karena adanya masalah seperti skenario berikut : jika pelanggan berada di lokasi yang jauh dari Region terdekat (misalnya, pelanggan di Jakarta mengakses data di Tokyo), latensi akan tinggi. Maka dari itu ada Edge Locations. Di AWS terdapat layanan yang menggunakan Edge Locations :

#### 3.2.1 Amazon CloudFront

Amazon CloudFront yang merupakan Layanan Content Delivery Network (CDN) AWS yang menggunakan Edge Locations untuk mengirimkan data, video, aplikasi, atau API ke pelanggan dengan latensi rendah dan kecepatan tinggi.

Sebagai contoh, Pelanggan di Jakarta mengakses data dari Edge Location di Singapura, bukan langsung dari Region Tokyo, sehingga akses lebih cepat.

#### 3.2.2 Amazon Route 53

Layanan DNS (Domain Name System) AWS yang mengarahkan pelanggan ke lokasi terdekat dengan latensi rendah. Berfungsi memastikan pengguna mengakses server atau aplikasi terdekat untuk pengalaman yang lebih cepat.

#### 3.2.3 AWS Outposts

Meripkan solusi AWS yang memungkinkan menjalankan layanan AWS langsung di data center milik sendiri. Cocok untuk perusahaan yang perlu mempertahankan data atau aplikasi di lokasi tertentu karena alasan kepatuhan atau keamanan. AWS menginstal "Region mini" di data center Anda, yang sepenuhnya dioperasikan oleh AWS.

### 3.3 Interaksi Layanan AWS

#### 3.3.1 AWS Management Console

AWS Management Console merupakan aplikasi berbasis browser untuk mengkases dan mengelola layanan AWS. Aplikasi yang dapat mengelola sumber daya AWS secara visual yang mudah dipahami.

Memiliki beberapa kelebihan :
- Cocok untuk pemula yang ingin mempelajari AWS.
- Memungkinkan pencarian layanan, pembangunan lingkungan pengujian, pemantauan sumber daya, dan manajemen tagihan.
- Tersedia versi aplikasi seluler untuk memantau sumber daya dan melihat alarm.
- Mudah digunakan dan ramah pengguna.

#### 3.3.2 AWS Command Line Interface (CLI)

AWS Command Line Interface (CLI) merupakan antarmuka yang berberntuk alat baris perintah untuk mengontrol layanan AWS melalui skrip atau perintah.

Memiliki bebrapa kelebihan :
- Menghindari kesalahan manusia (human error) yang mungkin terjadi saat menggunakan antarmuka visual.
- Memungkinkan otomatisasi tugas, seperti meluncurkan EC2 instance, dengan menjalankan skrip yang sama berulang kali.
- Efisien untuk lingkungan produksi dan dapat dijadwalkan atau dipicu oleh proses lain.

#### 3.3.3 AWS Software Development Kit (SDK)

AWS Software Development Kit (SDK) Kumpulan alat untuk berinteraksi dengan AWS menggunakan berbagai bahasa pemrograman (seperti Python, Java, JavaScript, dll.).

Memiliki beberapa kelebihan :
- Memudahkan developer untuk membuat program di AWS tanpa harus menggunakan API tingkat rendah.
- Menyediakan dokumentasi dan sampel kode untuk memudahkan pengembangan.
- Cocok untuk developer yang ingin mengintegrasikan AWS ke dalam aplikasi mereka.

#### 3.3.4 AWS Elastic Beanstalk

AWS Elastic Beanstalk adalah layanan yang dapat membantu menyediakan lingkungan berbasis Amazon EC2. Untuk membuat EC2 instance dengan AWS Elastic Beanstalk juga lebuh mudah dibanding dengan cara sebelumnya.

Memiliki beberapa kelebihan :
- Mengotomatiskan penyediaan infrastruktur seperti EC2 instance, load balancing, auto-scaling, dan pemantauan kesehatan aplikasi.
- Anda hanya perlu mengunggah kode aplikasi, dan Elastic Beanstalk akan mengurus infrastrukturnya.
- Cocok untuk developer yang ingin fokus pada aplikasi tanpa mengelola infrastruktur.

#### 3.3.5 AWS CloudFormation

Layanan Infrastructure as Code (IaC) yang memungkinkan mendefinisikan sumber daya AWS menggunakan template berbasis JSON atau YAML.

Memiliki beberapa kelebihan :
- Membuat dan mengelola sumber daya AWS secara otomatis dan berulang.
- Menghindari human error karena semua proses dijalankan secara otomatis.
- Dapat digunakan untuk membuat lingkungan yang identik di beberapa akun atau Region
- Sangat cocok untuk deployment yang kompleks dan berulang.