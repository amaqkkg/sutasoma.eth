---
title: "Web Ini Hidup di IPFS"
description: "Lebih Jauh Tentang Protokol Distribusi File Terbesar di Planet Bumi"
author: Faris Maulana
date: 2021-05-29T21:32:27+07:00
draft: false
---

Istri penulis berpendapat bahwa penulis memang suka melakukan hal yang tidak perlu, seperti menghosting blognya sendiri.

Ya memang benar! Hahahaha. Mungkin istri penulis belum mengerti ya apa sih fungsinya menghosting blog/webiste sendiri. Tulisan ini saya buat bukan sebagai jawaban atas pendapat istri karena memang pendapatnya benar (lagipula wanita selalu benar) namun lebih menuju ke penjelasan, kenapa sih? why gitu loh?
Sebagai seorang penulis di distributed/decentralized website seperti website ini, sangat sulit rasanya jika tidak berbagi tentang hal tersebut.
Selain istri mungkin banyak juga yang bertanya-tanya (asumsi penulis) *sebenarnya apa sih distributed website itu? Apa bedanya sama website biasa? Apa pentingnya desentralisasi dan kenapa saya perlu tahu?*
Sebenarnya pertanyaan terakhir jawabannya **ga perlu tahu juga, tapi ya simak aja yak**.

Kalau kita menilik ke masa lalu, kita akan sadar seberapa jauh manusia berkembang terutama dalam hal teknologi.
Mungkin beberapa dari kita sempat mendengar suara koneksi *dial-up* tiap kali akan terhubung ke internet, dan lihatlah kondisi sekarang dimana internet dan kecepatan tinggi merupakan suatu hal yang menjadi kewajiban dalam berkehidupan sehari-hari. Sangat mencengangkan!

Benar saja, dalam kehidupan manusia saat ini sangat erat hubungannya dengan internet. Tapi ada berapa banyak sih yang mengerti serangkaian teknologi didalam internet tersebut?
*ah yang penting bisa make aja.*
Iya tidak salah memang, namun tidak salah juga kalau kita sedikit tahu kan?

## HyperText Transfer Protocol (HTTP)

HTTP. Internet tidak jauh dari HTTP.

HTTP ini semacam rambu lalu lintas yang ada dijalanan, yang kita sering lihat namun tidak tahu arti dan tujuannya. *Betul?*

HTTP sebenarnya sebuah aturan atau protokol dimana tatacara komunikasi antara *client* dan *host* (server) diatur (komunikasi ini disebut *peer-to-peer*). Ada komunikasi antara *client* yang me-*request* *file/dynamic document* (seperti HTML) via *web browser* dimana agar file tersebut dapat diakses oleh si *client*. Misalnya kita ingin mengakses laman berisi video di youtube, maka dengan *web browser* akan di-*translate* untuk menampilkan konten tersebut dari server youtube. Walaupun terlihat ada komunikasi antara client dan server, protokol ini sangat tergantung terhadap apa yang ada di server. Misalnya saja laman video yang kita request dihapus oleh youtube di servernya, maka saat kita ingin mengaksesnya kembali pasti akan mendapatkan warning bahwa laman video tersebut sudah tidak tersedia. Dari sini terlihat peran server sebagai tempat me-maintain segala jenis file yang dapat diakses di internet. Model HTTP ini sangat tersentralisasi di setiap server yang ada. Belum lagi dengan adanya jarak antara server dengan client, misalnya server ada di Jakarta dan client berada di Hawaii, maka request client ke server dan mengirim hasil request tersebut ke client membutuhkan waktu dan biaya yang lumayan banyak. HTTP memang menunjuk file secara lokasi, baik dari segi geo-location dan juga lokasi file tersebut di server. Metode ini disebut sebagai *Location-Based Addressing*.

### Location-Based Addressing

Studi kasus. Misalnya kita ingin mencari info tentang Istanbul di situs wikipedia berikut:
```
https://id.wikipedia.org/wiki/Istanbul
```
Ketika kita memasukkan URL tersebut di address bar pada browser, perangkat kita akan meminta/*request* salah satu server dari wikipedia yang mungkin ada dibelahan dunia sana untuk menampilkan laman Istanbul.

Atau ketika kita akan mengakses file **budi.xls** di komputer kita, kita bisa mengetik di address bar file explorer dengan merujuk lokasinya. Contoh:
```
F:\data\penting\budi.xls
```
Sebenarnya kita memerintahkan untuk file explorer untuk pergi ke alamat hard disk **drive F**, didalam folder **data**, lalu ke folder **penting** dimana file **budi.xls** berada.
Inilah yang disebut *Location-Based Addressing*.

Sudah dapat gambarannya? dan kenapa ini problem jika dipakai sebagai protokol internet? Mari kita dalami lagi.

Pertama adalah Sentralisasi. Link pada webiste merupakan identifier yang menunjuk sebuah lokasi di internet, yang mana terdapat di server tertentu yang ditunjuk. [Siapapun yang mengontrol lokasi (server) tersebut, juga mengontrol kontennya](https://flyingzumwalt.gitbooks.io/decentralized-web-primer/content/avenues-for-access/lessons/power-of-content-addressing.html). Walaupun ada sekian ratus orang yang sudah men-*download* konten tersebut, dimana artinya konten tersebut berada diratusan lokasi berbeda, Link pada HTTP tetap akan menunjuk dan hanya akan menunjuk satu tempat, yaitu server. Hal ini juga membuat pemilik yang mengontrol lokasi tersebut dapat menentukan siapa saja yang boleh mengakses konten tersebut. Belum lagi jika ternyata konten tersebut merupakan konten yang bertentangan dengan pemerintah yang opresif misalnya, mudah untuk pemerintah turun tangan untuk melakukan sensor ataupun modifikasi konten tersebut, pemerintah hanya perlu mencari pemilik dari server tersebut dan memintanya untuk menghapus/memodifikasi kontennya. Belum lagi jika ada serangan DDoS ke server yang menyebabkan server down, tentunya konten yang ada didalam server tidak bisa disajikan ke khalayak umum lagi kan?

Kedua, Histori dan Biaya (ini kedua dan ketiga harusnya). Kita asumsikan bahwa pemilik konten tersebut akan terus menyimpan dan memberikan akses terhadap kontennya kesiapapun. Namun trend dan juga topik hangat di dunia ini sangat dinamis yang menyebabkan ada bahkan banyak penyedia konten menghapus konten yang sudah basi demi terus meningkatkan traffic kunjungan atau bahkan dikarenakan biaya untuk me-*maintain* server dan memperbaharui infrastruktur yang semakin mahal. Sebuah studi juga menunjukkan rata-rata sebuah laman web hidup selama [100 hari](https://blogs.loc.gov/thesignal/2011/11/the-average-lifespan-of-a-webpage/) saja. Sebuah sarana bernama internet idealnya dapat menyimpan segala jenis sejarah dan histori yang pernah ditulis, sangatlah tidak elok jika tumpuan hidup masa kini rentan terhadap hal ini.

Problem diatas mengisyaratkan kembali, bahwa tidak seharusnya internet tersentralisasi. Internet seharusnya kembali menjadi terdesentralisasi dengan sensor terhadap internet sangat sulit dan informasi yang ada di internet tidak akan mudah hilang dikarenakan server yang tidak berfungsi sebagaimana mestinya.

*Memangnya ada alternatif lain?*

Oh jelas ada! Untuk mengatasi problem tersebut ada sebuah protokol *peer-to-peer* sama seperti HTTP namun bedanya jika HTTP menganut sistem sentralisasi di server tertentu, protokol ini mendistribusi konten tersebut di banyak node-node (ratusan bahkan ribuan). Bisa dianggap node ini seperti server, namun client tidak harus merequest data dari satu server saja. Itulah **IPFS**!

## InterPlanetary File System (IPFS)

Seperti namanya yang diambil sebagai penghormatan terhadap [J.C.R. Licklider](https://en.wikipedia.org/wiki/J._C._R._Licklider#Global_computer_network) dan "*intergalactic computer network*"-nya, IPFS bertujuan untuk merombak kembali internet dengan membuat sebuah protokol *file system* yang menampung semua konten yang ada di muka bumi ini. Berbeda dengan HTTP yang merupakan *Transfer Protocol*, IPFS merupakan *Distribution Protocol* yaitu sebuah aturan untuk mendistribusi file/konten. Masih agak abstrak ya?

Gampangnya begini, web yang tersentralisasi yang sudah disebutkan diatas berbicara tentang lokasi, lokasi dan lokasi. Sedangkan web yang terdistribusi berbicara tentang konten, bukan lokasi. Hal ini disebut sebagai Content Adressing.

*Bedanya?*

Bedanya adalah, Location-Based Addressing memberitahu komputer *dimana* ia akan menemukan file/konten yang ditunjuk, sedangkan IPFS

### Lebih Jauh tentang Content Adressing

### Kelebihan dan Kekurangan IPFS

## Perbedaan HTTP dan IPFS
