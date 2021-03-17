---
author: "Chrisdion Andrew"
title: "Amazon Ec2"
description: 
date: 2021-03-16T17:49:20+07:00
tags: []
categories: []
series: []
aliases: []
image: 
draft: false
---

### Tipe Instance Amazon EC2

Setiap tipe instance dikelompokkan dalam satu instance family (keluarga instance) dan dioptimalkan untuk jenis tugas tertentu. Tipe instance menawarkan berbagai kombinasi dari kapasitas CPU, memori, penyimpanan, jaringan, serta memberi Anda fleksibilitas untuk memilih kombinasi sumber daya yang sesuai untuk aplikasi Anda.

Instance family di Amazon EC2 memiliki fungsi yang berbeda-beda. Di antaranya ada *general purpose, compute optimized, memory optimized, accelerated computing* (komputasi terakselerasi), dan *storage optimized*.

- General purpose instances (Instance tujuan umum)
Tipe ini memberikan keseimbangan yang baik dari segi sumber daya komputasi, memori, dan jaringan. Selain itu, opsi ini juga dapat digunakan untuk berbagai beban kerja yang beragam seperti server aplikasi web atau repositori kode.

- Compute optimized instances (Instance teroptimasi untuk komputasi)
Tipe yang satu ini ideal untuk tugas komputasi yang intensif dan berpusat pada prosesor dengan performa tinggi, seperti server game, HPC (high-performance computing/komputasi dengan performa tinggi), atau bahkan pemodelan ilmiah.

Anda juga bisa menggunakan tipe compute optimized instances untuk beban kerja batch processing yang membutuhkan banyak proses transaksi di satu grup.

- Memory optimized instances (Instance teroptimasi untuk memori)
Opsi ini didesain untuk memberikan performa tinggi untuk beban kerja yang memproses kumpulan data besar di dalam memori, seperti relasional dan nonrelasional database atau HPC (high-performance computing).

- Accelerated computing instances (Instance terakselerasi untuk komputasi)
Tipe ini menggunakan perangkat keras akselerator untuk menjalankan beberapa fungsi secara lebih efisien dibandingkan dengan perangkat lunak yang berjalan pada CPU. Contohnya adalah penghitungan bilangan floating-point, pemrosesan grafik, dan data pattern matching (pencocokan pola data).

- Storage optimized instance (Instance teroptimasi untuk penyimpanan)

Opsi ini didesain untuk beban kerja yang membutuhkan akses read (baca) dan write (tulis) yang tinggi dan berurutan untuk kumpulan data yang besar di penyimpanan lokal.

Contoh beban kerja yang sesuai untuk tipe ini mencakup sistem file terdistribusi, aplikasi data warehousing (gudang data), dan sistem online transaction processing (OLTP) berfrekuensi tinggi.

Dalam komputasi, istilah input/output operation per second (IOPS) adalah metrik yang mengukur kinerja perangkat penyimpanan. Ini menunjukkan berapa banyak operasi input atau output yang dapat dilakukan oleh perangkat dalam satu detik.


### Harga Amazon EC2
AWS memiliki beberapa pilihan penagihan terkait Amazon EC2. Di antaranya adalah:

- On-Demand (Sesuai Permintaan)
Opsi ini adalah yang paling dikenal, yaitu On-Demand. Anda hanya membayar selama instance berjalan--bisa per jam atau per detik--tergantung pada tipe instance dan sistem operasi yang Anda pilih.

On-Demand sangat ideal untuk penggunaan jangka pendek, pengembangan dan pengujian aplikasi, serta beban kerja yang tidak dapat diprediksi dan diinterupsi. Selain itu, model harga ini juga biasa digunakan untuk yang baru memulai, menguji beban kerja, sekadar bereksperimen, atau mendapatkan rata-rata dasar pemakaian instance.

- Savings Plans (Rencana Tabungan)
Savings Plans memungkinkan Anda mengurangi biaya komputasi dengan berkomitmen terhadap jumlah dolar per jam yang keluar dan penggunaan komputasi yang konsisten untuk jangka waktu 1 atau 3 tahun. Setiap penggunaan di luar itu akan dikenakan tarif On-Demand biasa.

- Reserved Instances (Instance Terpesan)
Reserved Instances menawarkan diskon penagihan yang diterapkan untuk instance On-Demand dengan berkomitmen terhadap tingkat penggunaan untuk jangka waktu 1 atau 3 tahun.

Ada beberapa opsi yang tersedia: Standard Reserved dan Convertible Reserved Instances (Instance Terpesan Standar dan Terpesan Konvertibel) untuk jangka waktu 1 atau 3 tahun. Dan juga tersedia Scheduled Reserved Instance (Instance Terpesan Terjadwal) untuk jangka waktu 1 tahun saja.

Opsi ini cocok untuk beban kerja dengan kondisi yang stabil atau dapat diprediksi.

- Spot Instances (Instance Spot)

Spot Instances menggunakan kapasitas komputasi Amazon EC2 yang tak terpakai dan menawarkan penghematan biaya hingga 90% dari harga On-Demand. Opsi ini sangat ideal untuk beban kerja dengan waktu mulai dan akhir yang fleksibel dan tak masalah dengan interupsi.

- Dedicated Hosts (Host Khusus)
Dedicated Hosts merupakan server fisik dari kapasitas Amazon EC2 instance yang didedikasikan sepenuhnya untuk Anda gunakan.
Opsi ini biasanya digunakan untuk memenuhi persyaratan compliance (kepatuhan) tertentu dan tidak ada orang lain yang akan berbagi sewa dari server fisik tersebut.


Jika Anda ingin menjalankan aplikasi dan menginginkan akses penuh ke sistem operasinya seperti Linux atau Windows, Anda bisa menggunakan Amazon EC2.
Jika Anda ingin menjalankan fungsi yang berjalan singkat, aplikasi berbasis kejadian, dan Anda tak ingin mengelola infrastrukturnya sama sekali, gunakanlah layanan AWS Lambda.
Jika Anda ingin menjalankan beban kerja berbasis Docker container di AWS, langkah yang perlu Anda lalui adalah:
Anda harus memilih layanan orkestrasinya terlebih dahulu. Anda bisa menggunakan Amazon ECS atau Amazon EKS.
Setelah memilih alat orkestrasinya, kemudian Anda perlu menentukan platformnya. Anda dapat menjalankan container pada EC2 instance yang Anda kelola sendiri atau dalam lingkungan serverless seperti AWS Fargate yang dikelola oleh AWS.

----

Ada 4 faktor bisnis yang menentukan pemilihan suatu Region.

- 
Compliance (Kepatuhan)
Sebelum faktor lainnya, Anda harus terlebih dahulu melihat compliance requirement (persyaratan kepatuhan) Anda. Titik. Opsi lainnya menjadi tidak penting saat Anda memiliki persyaratan kepatuhan.

Misalnya, jika Anda memiliki persyaratan bahwa data Anda harus tinggal di perbatasan negara Inggris, maka pilihlah Region London. Atau jika Anda harus masuk ke dalam perbatasan negara Cina, maka Anda bisa memilih salah satu Region Cina.

Namun, sebagian besar perusahaan tidak diatur oleh regulasi yang ketat semacam itu. Jadi, jika Anda tidak memiliki kontrol kepatuhan atau regulasi yang mewajibkan penentuan Region, maka Anda dapat mempertimbangkan faktor lain.
Proximity (Kedekatan)
Memilih region yang paling dekat dengan basis pelanggan akan membantu Anda untuk mengirimkan konten lebih cepat kepada mereka.

Katakanlah suatu perusahaan berlokasi di Washington, DC, namun kebanyakan pelanggannya tinggal di negara Singapura. Nah, untuk kasus ini, solusi yang tepat adalah dengan menjalankan infrastruktur di Region Northern Virginia agar dekat dengan lokasi perusahaan dan menerapkan aplikasi dari Region Singapura.

Dengan begitu, latensi (waktu yang diperlukan untuk mengirim dan menerima data) bisa semakin kecil dan pengiriman konten ke pelanggan menjadi lebih cepat.
Feature Availability (Ketersediaan Fitur)
Adakalanya, Region terdekat mungkin tidak memiliki semua fitur AWS yang Anda inginkan. Namun, AWS terus berinovasi untuk pelanggan. Setiap tahun, AWS merilis ribuan fitur dan produk baru secara spesifik untuk menjawab permintaan dan kebutuhan pelanggan.

- Proximity (Kedekatan)
Memilih region yang paling dekat dengan basis pelanggan akan membantu Anda untuk mengirimkan konten lebih cepat kepada mereka.

Katakanlah suatu perusahaan berlokasi di Washington, DC, namun kebanyakan pelanggannya tinggal di negara Singapura. Nah, untuk kasus ini, solusi yang tepat adalah dengan menjalankan infrastruktur di Region Northern Virginia agar dekat dengan lokasi perusahaan dan menerapkan aplikasi dari Region Singapura.

Dengan begitu, latensi (waktu yang diperlukan untuk mengirim dan menerima data) bisa semakin kecil dan pengiriman konten ke pelanggan menjadi lebih cepat.

- Feature Availability (Ketersediaan Fitur)
Adakalanya, Region terdekat mungkin tidak memiliki semua fitur AWS yang Anda inginkan. Namun, AWS terus berinovasi untuk pelanggan. Setiap tahun, AWS merilis ribuan fitur dan produk baru secara spesifik untuk menjawab permintaan dan kebutuhan pelanggan.

Tapi, terkadang layanan baru tersebut membutuhkan banyak perangkat keras fisik baru yang harus AWS bangun agar dapat beroperasi. Dan terkadang, itu berarti AWS harus membangun layanan di satu Region pada satu waktu.

- Pricing (Harga)
Meskipun spesifikasi perangkat keras pada suatu Region setara dengan Region lain, namun beberapa lokasi bisa lebih mahal pengoperasiannya.

Misal negara Brasil, struktur pajak di sana memiliki tatanan sedemikian rupa sehingga biaya AWS bisa jauh lebih mahal untuk mengoperasikan layanan yang sama persis dibandingkan dengan negara lain. Pengoperasian beban kerja yang sama persis di kota Sao Paulo mungkin bisa 50% lebih mahal daripada di kota Oregon di negara Amerika Serikat.

Harga dapat ditentukan oleh banyak faktor dan AWS akan transparan mengenai hal tersebut.

---

Region adalah wilayah yang terisolasi secara geografis di mana Anda dapat mengakses layanan yang diperlukan untuk menjalankan segala macam kebutuhan.
Region terdiri dari Availability Zone yang memungkinkan Anda untuk menjalankan seluruh bangunan data center yang terpisah secara fisik dengan jarak puluhan mil sambil menjaga aplikasi Anda tetap bersatu secara logis. Availability Zone membantu Anda untuk dapat mencapai high availability (ketersediaan tinggi) dan disaster recovery (pemulihan bencana) tanpa upaya apa pun dari Anda.
AWS Edge locations digunakan untuk menjalankan Amazon CloudFront sehingga dapat memperdekat konten kepada pelanggan Anda di mana pun mereka berada.