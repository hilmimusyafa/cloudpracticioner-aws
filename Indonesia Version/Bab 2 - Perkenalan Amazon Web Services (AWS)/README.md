## Bab 2 : Perkenalan Amazon Web Service (AWS)

### 2.1 Apa itu Amazon Web Service (AWS)?

Amazon Web Service atau AWS adalah salah satu layanan penyedia komputasi cloud yang merupakan milik perusahaan IT di Amerika, yaitu Amazon. 

Dengan AWS ini, membuat infrastruktur menjadi mudah, bisa menjadi Web Server, Database Server, dan masih banyak lagi.

### 2.2 AWS dan Cloud Computing

Cloud computing memungkinkan aplikasi atau layanan berjalan di server dengan daya komputasi yang cepat dan fleksibel. Layanan Primer untuk komputasi yang berkerja baik telah disediakan oleh Amazon berupa AWS EC2 (Elastic Compute Cloud).

AWS Elastic Compute Cloud (Amazon EC2) adalah layanan komputasi awan yang disediakan oleh Amazon dengan tujuan memberikan kapasitas komputasi untuk menjalankan aplikasi dan menyediakan daya komputasi sesuai kebutuhan bisnis.

Dengan menggunakan layanan EC2, sehingga memiliki kapasitas komputasi yang fleksibel, hemat biaya, dan cepat dibandingkan dengan menjalankan server sendiri di data center on-premise. Bagian virtual pada server tersebutlah disebut Instance.

### 2.3 Tipe Instance Amazon EC2

- General Purpose Instance (Instance Tujuan Umum) : Digunakan untuk berbagai beban kerja umum yang beragam, seperti aplikasi web, dll.
- Compute Optimized Instances (Instance Teroptimasi untuk Komputasi) : biasa di gunakan di HPC (High Performance Computing/ Komputasi Performa Tinggi), atau server game.
- Memmory Computing Instances (Instance Terakselerasi untuk Komputasi) : biasa di gunakan untuk Pemrosesan Grafik, dan Data Pattern Matching. (Pencocokan Pola Data)
- Storage Optimized Instance (Instance Teroptimasi untuk Penyimpanan) : biasa di penyimapanan lokal, dan mennggunakan akses baca (read) dan tulis (write) yang banyak.

### 2.4 Penyesuaian Kapasitas Amazon EC2 (Amazon EC2 Auto Scaling)

Amazon EC2 Auto Scaling adalah fitur AWS yang memungkinkan penyesuaian kapasitas server secara otomatis sesuai kebutuhan. Dengan fitur ini, sistem dapat menambah atau mengurangi jumlah instance EC2 tanpa intervensi manual, sehingga menghindari downtime dan meningkatkan efisiensi biaya.

Pendekatan dalam Amazon EC2 Auto Scaling, bisa tergantung 2 dasar, yaitu :
- Dynamic Scaling: Menyesuaikan jumlah instance berdasarkan perubahan permintaan secara real-time.
- Predictive Scaling: Memprediksi tren permintaan dan menjadwalkan jumlah instance yang optimal sebelum lonjakan trafik terjadi.

Metode Scaling pun bermacam-macam : 
- Scaling Up : Meningkatkan daya komputasi dari instance yang sudah berjalan agar dapat menangani beban kerja yang lebih tinggi.
- Scaling Out : Menambah jumlah instance untuk mendistribusikan beban kerja secara lebih efektif.

Di AWS, juga terdapat auto scaling group. Auto Scaling Group mengatur kumpulan instance EC2 dengan konfigurasi berikut:
- Minimum Capacity : Jumlah minimum instance yang selalu berjalan.
- Desired Capacity : Jumlah instance yang diinginkan untuk menjaga performa.
- Maximum Capacity : Batas maksimum instance saat permintaan meningkat.

Manfaat menggunakan EC2 Auto Scaling pada AWS, adalah :
- Meningkatkan ketersediaan layanan tanpa downtime.
- Mengoptimalkan biaya dengan menyesuaikan kapasitas sesuai kebutuhan.
- Memastikan performa aplikasi tetap stabil meskipun terjadi lonjakan trafik.

### 2.5 Komputasi Serverless

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

### 2.6 Load Balancing (Penyeimbang Beban)

Load Balancing atau Penyeimbang beban merupakan sebuah proses untuk membagi atau menyebar beban kerja (permintaan) secara merata ke bebebrapa sistem, sehingga sistem layanan walau dengan banyaknya permintaan yang masuk, akan tetap berjalan dengan optimal karena tidak adanya salah satu yang sibuk sendiri.

Load Balancing berhubungan langsung dengan Scaling Out karena, jika tidak ada Load Balancer pada sistem yang sudah di discaling out, perlakuan Scaling Out itu akan sia-sia karena beban kerja akan terus masuk pada sistem pertama (karena tidak ada load balancing yang membagi pekerjaan ke sistem lain).

AWS memiliki layanan load balncing yang bernama Elastic Load Balancing (ELB) yang berkinerja tinggi, hemat biaya, dan highly available. Ketika traffic aplikasi meningkat (misalnya saat flash sale), EC2 instance akan scale out dan ELB akan mendistribusikan traffic ke instance baru. Saat traffic menurun, instance yang tidak dibutuhkan akan scale in tanpa mengganggu aktivitas pengguna.

### 2.7 Messaging & Queueing

Messaging dan Queueing adalah konsep penting dalam sistem terdistribusi yang memungkinkan komunikasi antar komponen aplikasi secara asinkron (tidak langsung). Ini membantu memastikan bahwa komponen-komponen tersebut dapat bekerja secara independen, meningkatkan skalabilitas, keandalan, dan fleksibilitas sistem.

1. Messaging

Merupakan proses pengiriman pesan antar komponen aplikasi.Bertujuan memungkinkan komponen untuk berkomunikasi tanpa harus terhubung secara langsung (decoupling). Sebagai contoh Aplikasi A mengirim data ke Aplikasi B melalui pesan.

2. Queueing

Penyimpanan sementara pesan dalam antrean (queue) sebelum diproses oleh komponen penerima.Bertujuan Memastikan pesan tidak hilang dan dapat diproses saat komponen penerima siap.
Pesan disimpan dalam antrean sampai Aplikasi B siap memprosesnya.

