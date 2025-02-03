## Bab 2 : Perkenalan Amazon Web Service (AWS)

### 2.1 Apa itu Amazon Web Service (AWS)?

Amazon Web Service atau AWS adalah salah satu layanan penyedia komputasi cloud yang merupakan milik perusahaan IT di Amerika, yaitu Amazon. 

Dengan AWS ini, membuat infrastruktur menjadi mudah, bisa menjadi Web Server, Database Server, dan masih banyak lagi.

### 2.2 AWS dan Cloud Computing

Komputasi di awan yang bekerja untuk menjadi server dari aplikasi atau layanan perlu komputasi dengan kemampuan yang cepat, maka dari itu ada AWS EC2.

AWS Elastic Compute Cloud (Amazon EC2) adalah layanan komputasi awan yang disediakan oleh Amazon dengan harapan memberikan kapasitas komputasi untuk menjalankan aplikasi dan menyediakan daya komputasi sesuai kebutuhan bisnis.

Di AWS, server tersebut berbentuk virtual, dan layanan yang dapat di gunakan untuk mendapatkan akses ke server virtual tersebut disebut dengan Amazon EC2. 

Dengan menggunakan layanan EC2, sehingga memiliki kapasitas komputasi yang fleksibel, hemat biaya, dan cepat dibandingkan dengan menjalankan server sendiri di data center on-premise. Bagian virtual pada server tersebutlah disebut Instance.

### 2.3 Tipe Instance Amazon EC2

- General Purpose Instance (Instance Tujuan Umum) : Digunakan untuk berbagai beban kerja umum yang beragam, seperti aplikasi web, dll.
- Compute Optimized Instances (Instance Teroptimasi untuk Komputasi) : biasa di gunakan di HPC (High Performance Computing/ Komputasi Performa Tinggi), atau server game.
- Memmory Computing Instances (Instance Terakselerasi untuk Komputasi) : biasa di gunakan untuk Pemrosesan Grafik, dan Data Pattern Matching. (Pencocokan Pola Data)
- Storage Optimized Instance (Instance Teroptimasi untuk Penyimpanan) : biasa di penyimapanan lokal, dan mennggunakan akses baca (read) dan tulis (write) yang banyak.

### 2.4 Penyesuaian Kapasitas Amazon EC2

Penyesuaian kapasitas Amazon EC2 dilakukan dengan adanya analisa kapasitas tergantung dari banyaknya pengguna atau yang ingin mengakses aplikasi yang ada.

Coba bayangkan, ada sebuah server yang dimana melayani aplikasi belanja (e-commerce) yang dimana melayani klien untuk belanja barang. 

Setelah mendapat data analisis pengunjung website e-commerce tersebut dan dilihat ternyata setiap di tanggal dan bulan yang sama (8.8, 9.9, 10.10, dll.) pengujung naik dan performa server meningkat bahkan hampir overload dikarenakan promo e-commerce yang selalu di adakan di tanggal bulan yang sama.

Dengan ini, kesimpulan didapatkan bahwa perlu adanya ekspansi performa server di setiap promo yang berlangsung, sehingga tidak ada kasus aplikasi lama di akses atau bahkan sampe down.

Nah, jika di skenario tersebut menggunakan data center on-premise, akan ribet untuk ekspansi aplikasi, diperlukan menimbang lagi berapa kapasitas peningkatan secara manual.Tetapi, tidak di AWS karena adanya Amazon EC2 Auto Scaling.

Amazon EC2 Auto Scaling? Apa itu? Ya, Amazon EC2 Auto Scaling adalah fitur AWS yang memudahkan untuk menambah atau menghapus Amazon EC2 instances secara ototmattis sesuai kebutuhan, jadi aplikasi akan selalu ada. 

Contoh skenario yang ada di website e-commerece pada promo tanggal dan bulan sama. Jika server e-commerce itu kewalahan akan melayani client yany banyak, bahkan hingga client merasa website atau aplikasi menunjukkan error atau timeout, nah dengan kasus itu server harus di tingkatkan dengan ekspansi performa, untuk melakukan itu secara mudah, bisa menggunakan Amazon EC2 Auto Scaling, sehingga server otomatis akan terexpand performa dan beban kerjanya.

Pada Amazon EC2 Auto Scaling ada dua pendekatan :
- Dynamic Scaling, yaitu merespons jika ada perubahan permintaan.
- Predictive Scaling, yaitu secara otomatis menjadwalkan jumlah EC2 instances yang tepat berdasarkan prediksi permintaan.

Pada Amazon EC2 Auto Scaling ada 2 pemaknaan, yaitu : 
- Scaling Up
  Pemaknaan Scaling Up adalah penambahan lebih banyak daya pada mesin yang sedang berjalan. Contoh pada kasus e-commerce, server pengatur pembayaran (payment) dengan kemampuan melayani transaksi 20x dalam satu waktu, karena ramai, server tersebut di tambah performa nya agat dapat melakukan transaksi 40x dalam satu waktu.
- Scalling Out
  Untuk Scaling Out adalah menambahkan total mesin atau sistem yang mengerjakan tugas atau komputasi tersebut. Kembali pada kasus e-commerce, server pengatur pembayarannya bukan di tingkatkan performnya, melainkan di tambah jumlahnya, misal yang berawal ada 1 pengatur pembayaran dan itu dia bekerja ekstra, sekarang akan di scaling out sehingga menjadi 3 pengatur pembayaran.

Dan ada juga Auto Scaling Group, Auto Scaling Group? Apa itu? Auto Scaling Group adalah fitur di cloud yang memungkinkan penyesuaian kapasitas komputasi secara fleksibel dengan mengatur kumpulan Amazon EC2 instance. Untuk mengonfigurasinya, perlu ditentukan:

- Minimum Capacity: Jumlah minimum EC2 instance yang selalu berjalan (misalnya, 1 instance).
- Desired Capacity: Jumlah instance yang diinginkan (misalnya, 2 instance), meskipun aplikasi hanya membutuhkan 1. Jika tidak diatur, default-nya adalah minimum capacity.
- Maximum Capacity: Batas maksimum instance yang dapat di-scale (misalnya, 4 instance) saat permintaan meningkat.

Dengan Amazon EC2 Auto Scaling, hanya perlu membayar sesuai penggunaan, sehingga lebih hemat biaya dan memberikan pengalaman terbaik kepada pelanggan.

### 2.5 Load Balancing (Penyeimbang Beban)

Load Balancing atau Penyeimbang beban merupakan sebuah proses untuk membagi atau menyebar beban kerja (permintaan) secara merata ke bebebrapa sistem, sehingga sistem layanan walau dengan banyaknya permintaan yang masuk, akan tetap berjalan dengan optimal karena tidak adanya salah satu yang sibuk sendiri.

Load Balancing berhubungan langsung dengan Scaling Out karena, jika tidak ada Load Balancer pada sistem yang sudah di discaling out, perlakuan Scaling Out itu akan sia-sia karena beban kerja akan terus masuk pada sistem pertama (karena tidak ada load balancing yang membagi pekerjaan ke sistem lain).

AWS memiliki layanan load balncing yang bernama Elastic Load Balancing (ELB) yang berkinerja tinggi, hemat biaya, dan highly available. Ketika traffic aplikasi meningkat (misalnya saat flash sale), EC2 instance akan scale out dan ELB akan mendistribusikan traffic ke instance baru. Saat traffic menurun, instance yang tidak dibutuhkan akan scale in tanpa mengganggu aktivitas pengguna.

### 2.6 Messaging & Queueing

Messaging dan Queueing adalah konsep penting dalam sistem terdistribusi yang memungkinkan komunikasi antar komponen aplikasi secara asinkron (tidak langsung). Ini membantu memastikan bahwa komponen-komponen tersebut dapat bekerja secara independen, meningkatkan skalabilitas, keandalan, dan fleksibilitas sistem.

1. Messaging

Merupakan proses pengiriman pesan antar komponen aplikasi.Bertujuan memungkinkan komponen untuk berkomunikasi tanpa harus terhubung secara langsung (decoupling). Sebagai contoh Aplikasi A mengirim data ke Aplikasi B melalui pesan.

2. Queueing

Penyimpanan sementara pesan dalam antrean (queue) sebelum diproses oleh komponen penerima.Bertujuan Memastikan pesan tidak hilang dan dapat diproses saat komponen penerima siap.
Pesan disimpan dalam antrean sampai Aplikasi B siap memprosesnya.

### 2.7 Komputasi Serverless

Serverless adalah sebuah konsep pengembangan sistem di mana developer atau pengembang hanya fokus pada penulisan kode aplikasi tanpa perlu mengelola atau mengkonfigurasi infrastruktur server secara manual. Dalam arsitektur serverless, penyedia layanan cloud (seperti AWS) bertanggung jawab penuh atas penyediaan, pengelolaan, dan penskalaan infrastruktur yang diperlukan untuk menjalankan kode tersebut. 

Dalam arsitektur serverless, penyedia layanan cloud (seperti AWS, Google Cloud, atau Microsoft Azure) bertanggung jawab penuh atas penyediaan, pengelolaan, dan penskalaan infrastruktur yang diperlukan untuk menjalankan kode tersebut. Beberapa layanan serverless di AWS seperti berikut :

1. AWS Lambda

AWS Lambda adalah layanan komputasi serverless dari AWS yang memungkinkan menjalankan kode tanpa mengelola server. Layanan ini sepenuhnya dikelola oleh AWS, dapat diskalakan otomatis, dan sangat tersedia (highly available).

AWS Lambda dirancang untuk tugas-tugas singkat (kurang dari 15 menit), seperti pemrosesan cepat, web backend, atau penanganan permintaan.

Cara kerja AWS Lambda :
- Unggah Kode
- Konfigurasi Trigger
- Eksekusi Kode
- Pembayaran Sesuai Penggunaan

2. Container 

Container (misalnya Docker) memungkinkan untuk mengemas kode, konfigurasi, dan dependensi aplikasi dalam satu objek yang sudah dibentuk dengan perumpamaan kontainerisasi. Container berjalan di atas EC2 instance dan bekerja secara terpisah satu sama lain.

Untuk menjalankan model sistem kontainer diperlukan Container Orchstration, yang dimana proses mengelola container dalam skala besar, seperti memulai, menghentikan, dan memantau container di beberapa EC2 instance.

Berikut berapa layanan container yang ada di AWS : 

a. Amazon Elastic Container Service (Amazon ECS) 

Layanan orkestrasi container yang mendukung Docker untuk menjalankan dan menskalakan aplikasi berbasis container di AWS. dan menggunakan API untuk meluncurkan dan menghentikan aplikasi Docker. ECS ini berjalan di EC2 AWS.

b. Amazon Elastic Kubernetes Service (Amazon EKS) 

Merupakan layanan terkelola untuk menjalankan Kubernetes di AWS. Kubernetes adalah platform open-source untuk mengelola container dalam skala besar (container orchestartion)/ AWS bekerja sama dengan komunitas Kubernetes untuk memastikan pembaruan fitur. Juga sama, ECS ini berjalan di EC2 AWS.

c. AWS Fargate

Platform komputasi serverless untuk ECS dan EKS. Anda tidak perlu mengelola EC2 instance; AWS Fargate mengelola infrastruktur untuk Anda. Anda hanya membayar sumber daya yang digunakan untuk menjalankan container. Jaddi yang ini seperti Serverless, tapi container-based server.



