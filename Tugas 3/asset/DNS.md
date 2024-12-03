# Proses Resolusi DNS (Domain Name System)

Dokumen ini menjelaskan secara terperinci proses resolusi DNS, mulai dari pengguna mengetikkan nama domain hingga browser berhasil memuat halaman yang diminta.

---

## 1. Langkah-Langkah Resolusi DNS
Berikut adalah langkah-langkah utama dalam proses resolusi DNS:

1. **Resolusi Dimulai oleh Klien**
   - Pengguna mengetikkan URL seperti `www.example.com` di browser.
   - Browser mengirimkan permintaan DNS ke resolver (Local DNS Server).

2. **Pemeriksaan Cache oleh Resolver**
   - Resolver memeriksa cache lokal.
   - Jika alamat IP ditemukan, hasil langsung dikembalikan ke browser.
   - Jika tidak, proses dilanjutkan ke langkah berikutnya.

3. **Permintaan Recursive Query ke Root Server**
   - Resolver mengirimkan **recursive query** ke **Root DNS Server** untuk informasi domain.

4. **Arah ke TLD Server**
   - Root server mengarahkan resolver ke server TLD yang bertanggung jawab, seperti `.com`.

5. **Permintaan ke Authoritative Name Server**
   - Resolver menghubungi authoritative server yang menyimpan catatan DNS untuk domain tersebut.

6. **Resolver Mengembalikan Alamat IP ke Browser**
   - Resolver memberikan alamat IP ke browser dan menyimpan hasil di cache.

7. **Koneksi HTTP/HTTPS**
   - Browser menggunakan alamat IP untuk terhubung ke server tujuan dan memuat halaman.

---

## 2. Diagram Resolusi DNS
Berikut adalah ilustrasi visual dari proses resolusi DNS:

![image](https://github.com/user-attachments/assets/a95cf345-b0d9-4673-bfac-be0c0ee7cd0f)

---

## 3. Penjelasan Elemen DNS
### a. Recursive Query
Permintaan yang dilakukan resolver untuk mencari informasi hingga menemukan hasil akhir dan mengembalikannya ke klien.

### b. Iterative Query
Permintaan bertahap yang dilakukan resolver ke Root Server, TLD Server, dan Authoritative Server.

### c. Cache dan TTL
- **Cache:** Menyimpan informasi DNS sementara untuk mempercepat pencarian.
- **TTL:** Waktu hidup data cache sebelum harus diperbarui.

### d. Jenis Catatan DNS
- **A Record:** Alamat IPv4.
- **AAAA Record:** Alamat IPv6.
- **CNAME Record:** Alias domain.
- **MX Record:** Mail server untuk domain tertentu.

---

## 4. Protokol Keamanan DNS
- **DNSSEC (DNS Security Extensions):** Menjamin integritas data DNS dengan tanda tangan digital.
- **DNS over HTTPS (DoH):** Mengamankan permintaan DNS dengan mengenkripsi melalui protokol HTTPS.
- **DNS over TLS (DoT):** Menggunakan TLS untuk mengenkripsi permintaan DNS.

---

## 5. Contoh Permintaan DNS
1. Browser mengirimkan permintaan untuk `www.example.com`.
2. Resolver melakukan pencarian iteratif melalui:
   - Root Server → TLD Server → Authoritative Server.
3. Alamat IP dikembalikan ke browser.
4. Browser membuat koneksi ke server tujuan.

---

## 6. Kesimpulan
Proses resolusi DNS melibatkan banyak komponen (Root Server, TLD Server, Authoritative Server) untuk menerjemahkan nama domain menjadi alamat IP, yang memungkinkan browser memuat halaman web.

---

