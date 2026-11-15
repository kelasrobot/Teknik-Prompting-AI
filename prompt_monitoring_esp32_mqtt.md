# PROJECT: SISTEM MONITORING SUHU DAN KELEMBAPAN ESP32

## 1. TUJUAN

Buatkan program ESP32 untuk membaca suhu dan kelembapan ruangan menggunakan sensor DHT22, kemudian mengirimkan datanya ke MQTT Broker setiap 5 detik.

## 2. SPESIFIKASI PERANGKAT

- **Board:** ESP32 DevKit V1
- **Sensor:** DHT22
- **Pin data sensor:** GPIO 4
- **IDE:** Arduino IDE
- **Bahasa pemrograman:** C++
- **Protokol komunikasi:** MQTT

Library yang digunakan:

- DHT sensor library
- PubSubClient

## 3. KONFIGURASI KONEKSI

**WiFi**

- SSID: `[WIFI_SSID]`
- Password: `[WIFI_PASSWORD]`

**MQTT**

- Broker: `[MQTT_BROKER]`
- Port: `[MQTT_PORT]`
- Username: `[MQTT_USERNAME]`
- Password: `[MQTT_PASSWORD]`
- Topic: `monitoring/ruangan/sensor`

Gunakan nilai placeholder untuk konfigurasi yang belum tersedia. Jangan membuat alamat broker atau kredensial palsu.

## 4. FITUR YANG HARUS DIBUAT

Buat program dengan fungsi berikut:

1. Menghubungkan ESP32 ke jaringan WiFi.
2. Menginisialisasi sensor DHT22.
3. Membaca suhu dalam Celsius dan kelembapan dalam persen.
4. Mengirimkan data ke MQTT Broker setiap 5 detik.
5. Menggunakan format JSON untuk data MQTT.
6. Menghubungkan kembali WiFi secara otomatis jika koneksi terputus.
7. Menghubungkan kembali MQTT secara otomatis jika koneksi terputus.
8. Menampilkan status koneksi dan hasil pembacaan sensor pada Serial Monitor.
9. Menggunakan `millis()` untuk mengatur interval pembacaan dan pengiriman data agar proses tidak terhambat oleh `delay()` yang panjang.

Contoh format payload MQTT:

```json
{
  "temperature": 28.5,
  "humidity": 75.2
}
```

## 5. ATURAN PEMROGRAMAN

- Gunakan Arduino IDE dan library yang kompatibel dengan ESP32.
- Buat kode yang mudah dipahami pemula.
- Pisahkan fungsi koneksi WiFi, koneksi MQTT, pembacaan sensor, dan pengiriman data agar kode mudah dikelola.
- Pastikan proses reconnect tidak dilakukan terus-menerus tanpa jeda.
- Tangani kegagalan pembacaan sensor.
- Jangan mengirimkan data sensor jika hasil pembacaannya tidak valid.
- Jangan menggunakan `delay()` yang menghambat komunikasi MQTT.
- Jangan mengarang konfigurasi yang belum diberikan.

## 6. FORMAT JAWABAN

Berikan hasil dengan urutan berikut:

1. Penjelasan cara kerja sistem.
2. Daftar komponen yang dibutuhkan.
3. Diagram atau tabel koneksi pin.
4. Daftar library dan cara instalasinya.
5. Kode program lengkap yang siap dicoba di Arduino IDE.
6. Penjelasan bagian penting dari kode.
7. Contoh data JSON yang dikirimkan.
8. Cara menguji data MQTT menggunakan MQTT Client.

Gunakan bahasa Indonesia yang sederhana dan mudah dipahami pemula. Jangan memberikan potongan kode yang belum lengkap.

## 7. PEMERIKSAAN HASIL

Sebelum memberikan jawaban akhir, lakukan pemeriksaan terhadap program yang dibuat.

Periksa:

- Kesalahan sintaks dan struktur kode.
- Kesesuaian konfigurasi pin ESP32.
- Inisialisasi dan pembacaan DHT22.
- Koneksi WiFi dan MQTT.
- Format payload JSON.
- Interval pengiriman data setiap 5 detik.
- Mekanisme reconnect.
- Kemungkinan proses blocking.

Jika ditemukan kesalahan, perbaiki terlebih dahulu.

Pisahkan asumsi teknis, potensi masalah, dan hal yang masih perlu diuji langsung pada perangkat.

Pastikan hasil akhir berupa satu program lengkap yang konsisten dengan seluruh spesifikasi di atas.
