# Tugas 1 : Analisis Komunikasi TCP dengan Socket Programming dan Wireshark

Tugas ini bertujuan untuk mempelajari komunikasi TCP antara klien dan server menggunakan pemrograman soket serta melakukan pemantauan jaringan dengan Wireshark. Proses yang dilakukan meliputi pengiriman data sederhana dan analisis paket TCP untuk memahami urutan komunikasi, termasuk proses Establishment koneksi menggunakan three-way handshaking, Transfer Data, dan Terminasi koneksi menggunakan three-way handshaking.

Pada tugas ini, saya menggunakan pemrograman soket dasar dari repositori GitHub untuk menerapkan komunikasi klien-server. Server dijalankan pada port 8000, dan klien terhubung ke server tersebut. Data yang dikirim berupa karakter 'zakywahyu122400012' dan kemudian dianalisis alur transmisinya menggunakan Wireshark.

Hasil analisis Wireshark digambarkan dalam diagram Urutan TCP, yang menggambarkan komunikasi TCP secara berurutan, mulai dari establishment koneksi hingga terminasi koneksi.

# Diagram Urutan TCP:

Establishment Koneksi (Three-way Handshaking)

Langkah 1: SYN (Synchronize)
Klien mengirimkan paket SYN dengan Seq=0 ke server untuk memulai koneksi.

Langkah 2: SYN-ACK (Synchronize-Acknowledgment)
Server merespons dengan paket SYN+ACK yang berisi Seq=0 dan Ack=1, menunjukkan bahwa server siap menerima komunikasi.

Langkah 3: ACK
Klien mengirimkan paket ACK dengan Seq=1 dan Ack=1 untuk mengonfirmasi bahwa koneksi telah terbentuk.

# Transfer Data

Pada tahap ini, klien dan server saling bertukar data. Proses ini melibatkan penggunaan flag PSH+ACK dan ACK.

Langkah 4: PSH + ACK
Klien mengirimkan data dengan paket Seq=1 dan Ack=1.

Langkah 5: ACK
Server mengonfirmasi penerimaan data dengan paket Seq=1 dan Ack=2.

Langkah 6: PSH + ACK
Server mengirimkan data balik ke klien dengan paket Seq=1 dan Ack=2.

Langkah 7: ACK
Klien mengonfirmasi penerimaan data dengan paket Seq=2 dan Ack=2.

# Termination Koneksi (Three-way Handshaking)

Pada tahap ini, proses untuk menutup koneksi setelah data selesai ditransfer dimulai.

Langkah 8: FIN + ACK
Klien mengirimkan paket FIN dengan Seq=2 dan Ack=2, menandakan bahwa klien ingin mengakhiri koneksi.

Langkah 9: ACK
Server mengonfirmasi permintaan untuk menutup koneksi dengan paket Seq=2 dan Ack=3.

Langkah 10: FIN + ACK
Server mengirimkan paket FIN untuk mengakhiri koneksi dari sisi server, dengan Seq=2 dan Ack=3.

Langkah 11: ACK
Klien mengonfirmasi dengan paket Seq=3 dan Ack=3, yang menandakan bahwa koneksi telah sepenuhnya ditutup.

# Penjelasan Tambahan:

Seq (Sequence Number): Nomor urut yang digunakan untuk melacak byte data yang dikirim.
Ack (Acknowledgment Number): Nomor untuk mengonfirmasi byte data yang telah diterima.
PSH (PUSH): Memberi tahu penerima untuk segera memproses data.
FIN (Final): Digunakan untuk mengakhiri koneksi.
