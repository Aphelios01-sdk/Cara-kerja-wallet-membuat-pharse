Berikut adalah penjelasan mengenai cara kerja wallet dalam membuat (create) **seed phrase** dan **private key**, serta teknologi **SHA-256** yang berperan penting dalam proses tersebut.

### 1. **Cara Kerja Wallet dalam Membuat Seed Phrase dan Private Key**

#### a. **Seed Phrase (Mnemonic Phrase)**
- **Seed Phrase** adalah kumpulan kata-kata (biasanya 12, 18, atau 24 kata) yang dihasilkan oleh wallet. Seed phrase ini digunakan untuk menghasilkan private key.
- **Proses:**
  1. **Generasi Entropi:** Wallet pertama kali menghasilkan angka acak (entropi) yang memiliki panjang tertentu, misalnya 128 bit (untuk 12 kata).
  2. **Checksum:** SHA-256 digunakan untuk membuat checksum dari entropi tersebut. Checksum ini ditambahkan ke entropi untuk membuat data lebih panjang yang akan digunakan untuk menghasilkan seed phrase.
  3. **Pemetaan ke Kata-Kata:** Data panjang yang dihasilkan dibagi menjadi beberapa bagian (masing-masing 11 bit). Setiap bagian tersebut dipetakan ke kata tertentu dalam daftar kata BIP-39 (standar Bitcoin Improvement Proposal untuk seed phrase).
  4. **Hasilnya adalah Seed Phrase:** Daftar kata yang dihasilkan adalah seed phrase yang dapat digunakan untuk memulihkan private key dan address.

#### b. **Private Key**
- **Private Key** adalah kunci rahasia yang dihasilkan oleh wallet dan digunakan untuk menandatangani transaksi. Private key harus dirahasiakan, karena siapa pun yang memiliki private key dapat mengakses aset di address yang terkait.
- **Proses:**
  1. **Generasi Entropi:** Sama seperti pembuatan seed phrase, wallet menghasilkan angka acak (entropi) yang akan digunakan untuk membuat private key.
  2. **Penerapan SHA-256:** Entropi ini di-hash menggunakan SHA-256 untuk menghasilkan private key yang memiliki panjang 256 bit.
  3. **Penggunaan dalam Kriptografi:** Private key ini digunakan dengan algoritma kriptografi (seperti Elliptic Curve Digital Signature Algorithm, ECDSA) untuk membuat public key dan, akhirnya, address.

### 2. **Teknologi SHA-256**

#### a. **Apa itu SHA-256?**
- **SHA-256** (Secure Hash Algorithm 256-bit) adalah salah satu algoritma hashing dalam keluarga SHA-2 yang dikembangkan oleh National Security Agency (NSA). Algoritma ini menghasilkan hash sepanjang 256 bit (32 byte).

#### b. **Cara Kerja SHA-256:**
- **Input:** SHA-256 menerima input berupa data dalam bentuk string atau angka berukuran berapa pun.
- **Proses:**
  1. **Padding:** Data yang di-input diubah menjadi multiple of 512-bit dengan menambahkan padding tertentu.
  2. **Pembagian:** Data dibagi menjadi blok-blok berukuran 512-bit.
  3. **Inisialisasi:** Algoritma SHA-256 dimulai dengan delapan nilai hash yang telah ditentukan sebelumnya.
  4. **Kompresi:** Blok-blok data ini diproses melalui beberapa putaran kompresi yang melibatkan perhitungan matematis kompleks, yang menghasilkan hasil intermediate.
  5. **Output:** Hasil akhir setelah semua blok diproses adalah hash sepanjang 256 bit.
  
#### c. **Fitur SHA-256:**
- **Deterministik:** Input yang sama akan selalu menghasilkan hash yang sama.
- **Cepat:** Proses hashing cepat dilakukan oleh SHA-256.
- **Preimage Resistance:** Sulit untuk mendapatkan input asli hanya dari hash yang dihasilkan.
- **Collision Resistance:** Sangat kecil kemungkinan dua input berbeda menghasilkan hash yang sama.

#### d. **Penggunaan SHA-256:**
- SHA-256 digunakan secara luas dalam berbagai aplikasi keamanan, termasuk dalam pembuatan private key, dalam blockchain (seperti Bitcoin), dan untuk verifikasi data digital.

source: Chatgpt4
