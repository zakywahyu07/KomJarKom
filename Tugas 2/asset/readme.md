# Tugas 2: Analisis Koneksi http.cap dengan Wireshark

Tugas ini bertujuan untuk menganalisis komunikasi TCP antara klien dan server berdasarkan file capture Wireshark yang diberikan, yaitu http.cap. Analisis dilakukan untuk memahami alur komunikasi yang melibatkan tahap Establishment Koneksi menggunakan three-way handshaking, Transfer Data, dan Terminasi Koneksi menggunakan three-way handshaking.

Dari total 43 paket yang tercatat dalam file http.cap, hanya 34 paket yang berhasil diproses selama komunikasi TCP antara klien dan server.

## Diagram Urutan TCP:

Pendirian Koneksi (Three-Way Handshaking)

Klien mengirimkan paket SYN untuk memulai proses koneksi.
Server merespons dengan paket SYN + ACK, menandakan bahwa server menerima permintaan dan siap melanjutkan komunikasi.
Klien kemudian mengirimkan paket ACK untuk menyelesaikan proses handshake dan membuka koneksi.
Tahap ini terlihat dalam diagram urutan TCP pada langkah 1 hingga 3.

## Transfer Data

Langkah 4: PSH + ACK
Klien mengirimkan 479 byte data dengan Seq=1 dan Ack=1.

Langkah 5: ACK
Server mengonfirmasi penerimaan data dari klien dengan Seq=1 dan Ack=480, yang menunjukkan bahwa data hingga byte ke-479 telah diterima dan server siap menerima data berikutnya dari byte 480.

Langkah 6: ACK
Server mengirimkan 1380 byte data dimulai dari Seq=1, yang berarti data dimulai dari byte pertama hingga byte ke-1380.

Langkah 7: ACK
Klien mengonfirmasi penerimaan data dari server dengan Seq=480 dan Ack=1381, yang menunjukkan bahwa klien telah menerima data hingga byte ke-1380 dan siap menerima data berikutnya mulai dari byte ke-1381.

Proses transfer data ini terus berlanjut hingga langkah ke-30, dengan urutan Sequence Number dan Acknowledgment Number yang terus disesuaikan untuk memastikan setiap paket data diterima dengan benar. Setelah seluruh data berhasil ditransfer, koneksi akan ditutup dengan paket FIN untuk mengakhiri sesi komunikasi.

## Pengakhiran Koneksi (Three-Way Handshaking)

Langkah 31: Server mengirimkan paket FIN + ACK untuk menandakan bahwa server ingin menutup koneksi.

Langkah 32: Klien merespons dengan paket ACK untuk mengonfirmasi penutupan koneksi.

Langkah 33: Klien mengirimkan paket FIN + ACK untuk menandakan bahwa klien juga ingin menutup koneksi.

Langkah 34: Server mengonfirmasi penutupan koneksi dengan mengirimkan paket ACK.

Demikianlah analisis urutan komunikasi TCP berdasarkan capture http.cap.
