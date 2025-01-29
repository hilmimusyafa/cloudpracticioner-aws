## Bab 7 : Pemantauan dan Analitik

### 7.1 Amazon CloudWatch

Amazon CloudWatch merupakan layanan pemantauan sistem AWS yang memantau kesehatan dan kinerja apliaksi serta infrastruktur secara real-time.

Fitur Utama Amazon CloudWatch :

1. Pemantauan Metrik

Melacak metrik seperti penggunaan CPU EC2 instance, permintaan ke S3 bucket, dan lainnya. Metrik adalah variabel yang terkait dengan sumber daya AWS.

2. CloudWatch Alarms

Membuat alarm berdasarkan ambang batas metrik tertentu (misalnya, membersihkan mesin setelah 100 espresso dibuat). Dapat mengirim notifikasi melalui Amazon SNS (Simple Notification Service) seperti SMS atau email.

3. CloudWatch Dashboard 

Panel yang menampilkan metrik dari berbagai sumber daya AWS secara real-time. Memungkinkan visualisasi dan pemantauan proaktif.

Manfaat menggunakan Amazon CloudWatch :

- Akses ke semua metrik dari satu lokasi 
- Visibilitas ke seluruh aplikasi, infrastruktur, dan layanan
- Mengurangi waktu MTTR dan mengurangi TCO
- Mengoptimalkan aplikasi dan sumber daya operasional

### 7.2 AWS CloudTrail

AWS CloudTrail merupakan sebuah layanan yang membantu meningkatkan keamanan di sistem AWS anda. AWS CloudTrail bertugas untuk mencatat seluruh aktivitas pengguna dan panggilan API yang ada di akun AWS Anda.

1. Fungsi AWS CloudTrail

a. Mencatat semua aktivitas API di akun AWS, seperti :

- Meluncurkan EC2 instance.
- Mengubah izin pengguna.
- Menambahkan data ke DynamoDB.

b. Menyimpan informasi seperti :

- Identitas pemanggil API.
- Waktu panggilan.
- Alamat IP pemanggil.

2. Manfaat AWS CloudTrail

- Audit dan Compliance : Membuktikan bahwa tidak ada perubahan yang tidak sah pada konfigurasi sumber daya AWS.
- Penyimpanan Log : Log dapat disimpan tanpa batas waktu di S3 bucket yang aman, bahkan dengan fitur seperti Vault Lock untuk mencegah penghapusan.
- Deteksi Aktivitas Mencurigakan: Fitur CloudTrail Insights secara otomatis mendeteksi aktivitas API yang tidak biasa (misalnya, peningkatan tiba-tiba dalam peluncuran EC2 instance).

3. Contoh kejadian 

Terdapat user baru bernama Stella dibuat tiba tiba, tidak diketahui siapa yang membuat, kapan di buat, atau bagaimana dibuat.

Setelah membukan AWS CloudTrail, dan dicek berdasarkan filter "CreateUser", menemukan bahwa yang membuat adalah :

Nama : Himeko
Waktu : 20 Januari 2025, pukul 12.35
Metode : AWS Console

### 7.3 AWS Trusted Advisor

AWS Trusted Advisor merupakan layanan yang disediakan oleh AWS yang seolah olah menjadi penasehat di sistem AWS. AWS Trusted Advisor akan memberikan rekomendasar secara realtime berdasarkan apa yang ada di sistem.

1. Yang di ecvaluasi oleh AWS Trusted Advisor :

a. Cost optimization (pengoptimalan biaya)
   Contoh : Terdapat EC2 Instance yang tidak terpakai/ jarang terpakai, maka akan di beri rekomendasi oleh AWS, agar tak menjkadi biaya lebih karena layanan terus berjalan tetapi tidak/jarang digunakan
b. Performance (kinerja)
   Contoh : Ada bagian layuanan yang belakangan sedikit ramai atau memiliki beban yang berat, maka AWS akan memberikan saran untuk upscale atau apapun itu untuk dari performa itu.
c. Security (keamanan)
   Contoh : MFA pada root user tidak di aktifkan sehingga AWS akan memberikan saran untuk mengaktifkannya.
d. Fault tolerance (toleransi terhadap kesalahan)
   Contoh : EBS tidak ada backup, hal ini akan berbahhaya jika EBS primary bermasalah, maka dari itu AWS akan menginfokan perlua danya tindakan
e. Service limits (batas layanan)
   Contoh : Kepemilikan VPC per region adalah 5, jika misal user dah mmemiliki 5, maka akan di beri peringatan.

2. Di AWS Trusted Advisor, terdapat 3 bahasa yang mengipretasikan suatu kondisi, yaitu :

- Centang Hijau : suatu hal yang terdeteksi tak ada maslaah.
- Segitiga Oranye : sesuatu yang di sarankan, perlu investigasi.
- Lingkaran Merah : sesuatu perlu tindak lanjut.

3. Manfaat AWS Trusted Advisor 

- To The Point, untuk menyelesaikan maslaah atau suatu rekomendasi langsung muncul dan cepat untuk menentukan solusi.
- Sistem makin Aman dan Optimal, dengan saran saran yang diberikan oleh AWS Trusted Advisor akan meningkatkan keamanan karena memperbarui kondisi.
- Biaya makin terkontrol, dengan sarana dari AWS Trusted Advisor, biaya makin hemat dan terknotrol, karena menghindari infrastruktur yang tidak/jarang digunakan.

