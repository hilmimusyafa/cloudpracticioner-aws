## Bab 8 : Harga dan Dukungan AWS

### 8.1 AWS Free Tier

AWS Free Tier merupakan kumpulan layanan AWS yang gratis, entah sepernuhnya gratis, percobaan gratis, atau gratis bersyarat. Free Tier biasanya di dasari ketika user baru menggunakan AWS. Jadi awal ketika user baru mendaftar ke AWS. Jenisnya pun banyak :

a. Always Free

Merupakan layanan meang di sediakan gratis oleh AWS secara gratis tanpa batas dan tersedia untuk seluruh pelanggan.

Contoh : AWS Lambda (Serverless) 

b. 12 Months Free

Beberapa layanan AWS juga diberikan gratis selama 12 bulan, terhitung ketika akun didaftarkan, akan mendapat layanan tersebut selama 12 bulan.

Contoh : AWS EC2 Instance t2.small

c. Free Trials

Dan juga, beberapa layanan AWS di gratiskan dalam jangka waktu terterntu (tergantung layanan) dengan ketentuan di mulai ketika layanan itu pertama kali di aktifkan, setelah durasi masa trial habis, maka akan lanjut dengan pembayaran harga regular.

Contoh : Amazon Inspector (90 hari uji coba gratis)

Untuk melihat lengkap terkait Free Tier, dapat dilihat di website resmi AWS.

### 8.2 AWS Non-Free Tier (Paid)

Konsep harga AWS memiliki beberapa model penagihan : 

- Pay for What You Use :  Di AWS, penagihan berdasarkan seberapa lama layanan/ sumber daya itu digunakan. Penagihan ini sangat strategis, karena tak perlu komitmen jangka panjang, cukup apa yang digunakan saja.

- Pay Less When Your Reverse : Beberpaa layanan menawarkan reservasi (Savings Plans) yang dapat menghemat hingga 72% dibanfingkan tarif on-demand. Cocok untuk beban kerja yang berjalan terus.

- Pay Less with Volume-based Discounts When You Use More : Semakin banyak menggunakan layanan tertent, semakin murah biaya per unitnya. Contoh, misal menggunakan Amazon S3, semakin sering digunakan maka semakin murah biayanya (per unit).

### 8.3 AWS Pricing Calculator 

Jika menggunakan AWS tetapi ingin lebih taktis dalam mengatur biaya infrastruktur, di AWS disediakan layanan untuk menghitung biaya AWS, yaitu AWS Price Calculator.

AWS Pricing Calculator merupakan layanan untuk menjelajahi AWS dan membuat estimasi biaya untuk penggunaan di AWS. Manfaat nya juga dapat membuat gambaran model arsitektur sebelum membuatnya, prediksi perhitungan harga, dan masihbanyak lagi.Fitur ini gratis cukup pakai dari AWS.

### 8.4 Billing Dashboard and Cost Management

AWS Billing Dashboard merupakan menu layanan yang ada di AWS untuk memberitahu tentang penagihan, memantau penggunaan, menganalisis dan mengontrol biaya.

Di Billing Dashboard dapat melihat informasi seperti : 
- Pembelanjaan bulanan.
- Layanan dengan pengeluaran terbsesar.
- Perbandingan pengeluaran bulan sebelumnya, bulan ini, dan  prefisksi bulan depan.
- Statistik penggunaan Free Tier berdasarkan layanan.
- Informasi tagihan yang lebih detail.

### 8.5 Consolidated Billing

Consolidated Billing merupakan fitur AWS Organizations yang memungkinan untuk menggabungkan tagihan dan beberapa akun AWS ke dalam satu tagihan terpusat (mungkin bisa dibilang mirip merge bill). 

Manfaat Consolidated Billing 
- Satu Tagihan Terpusat : Memudahkan pelacakan dan pengelolaan tagihan.
- Diskon Volume : Penggunaan gabungan dari semua akun dapat memenuhi syarat diskon volume, seperti pada Amazon S3.
- Gratis dan Mudah : Fitur ini tidak dikenakan biaya tambahan.

### 8.6 AWS Budgets

AWS Budget merupakan sebuah layanan untuk membatasi dan mengatur anggaran pengeluaran sesuai batas yang di tentukan, dengan adanya AWS budget tidak perlu pusing untuk masalah kelebihan pengekuaran, ketika sudah mencapai pengeluaran tertentu AWS akan memberi tau, bahwa layanan sudah melewati batas budget yang di tentukan.

### 8.7 AWS Cost Explorer

Jika menggunakan AWS, tagihan perbulan atau setiap periode tertentu pasti akan berubah ubah sesuai keadaaan sumber daya, perlu adanya penelusuran tagihan agar semakin tepat.

Maka dari itu, AWS menyediakan layanan AWS Cost Explorer, layanan berbasis konsol yang dapat menhganalisis secara visual pengeluaran di AWS. Dengan layanan ini, dapat :
- Melihat 12 bulan data historis untuk melacak tren pengeluaran.
- Mengidentifikasi layanan dengan biaya terbesar.
- Mengelompokkan pengeluaran berdasarkan atribut seperti layanan, region, tipe instance, atau tag.

### 8.8 AWS Support Plans

Jika bingung untuk menentukan infratruktur layanan AWS, AWS menawarkan 4 paket dukungan untuk memenuhi kebutuhan bisnis, mulai dari skala kecil hingga besar : 

1. Basic Support (Gratis):

- Akses 24/7 ke customer service.
- Dokumentasi, whitepaper, dan forum dukungan.
- AWS Trusted Advisor dan Personal Health Dashboard.

2. Developer Support :

- Semua fitur Basic Support.
- Layanan diagnostik klien, panduan praktik terbaik, dan dukungan arsitektur dasar.
- Respons email dalam 24 jam (kurang dari 12 jam untuk gangguan sistem).

3. Business Support :

- Semua fitur Basic dan Developer Support.
- Akses penuh ke AWS Trusted Advisor.
- Dukungan telepon langsung dengan SLA 4 jam (1 jam untuk sistem down).
- Infrastructure Event Management (biaya tambahan).
- Panduan kasus penggunaan dan dukungan terbatas untuk perangkat lunak pihak ketiga.

4. Enterprise Support :

- Semua fitur paket sebelumnya.
- SLA 15 menit untuk masalah kritis.
- Technical Account Manager (TAM) untuk konsultasi dan pengoptimalan.
- Infrastructure Event Management dan tinjauan Well-Architected Framework.

AWS menyelesaikan masalah sesuai dengan fokus AWS pada 5 pilar : Operational Excellence, Security, Reliability, Performance Efficiency, dan Cost Optimization.

