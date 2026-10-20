# PRAKTIKUM: RAG Sederhana dengan Google Colab dan Gemini API
Mata kuliah: Kecerdasan Buatan | Praktikum mandiri

## Penting: 
praktikum ini menggunakan Gemini API melalui kode Python di Google Colab, BUKAN aplikasi chatbot Gemini di website. API adalah antarmuka yang digunakan program untuk mengirim request ke layanan model Gemini dan menerima response.

## Tujuan: 
mahasiswa memahami perbedaan menjawab tanpa dokumen dan dengan Retrieval-Augmented Generation (RAG), serta dapat menelusuri potongan teks yang digunakan untuk membuat jawaban.
Semua petunjuk ada di notebook ini. Kerjakan dari atas ke bawah. Dokumentasikan hasilnya dalam file Word milik masing-masing mahasiswa. Pada setiap bagian bertanda 📸 Screenshot, ambil tangkapan layar kode/output yang diminta, tempel ke Word, dan beri caption penjelasan 1–3 kalimat tentang apa yang terjadi, bukan sekadar mengulang judul.

# Format Word yang dikumpulkan: 
identitas mahasiswa → screenshot bernomor sesuai tahap + caption → jawaban pertanyaan analisis. Jangan pernah menampilkan API key dalam screenshot.

# Perhatian: 
seluruh data kampus pada latihan ini dokumen dummy sebagai contoh dan bukan aturan resmi kampus mana pun. Pemanggilan API memerlukan internet dan dapat menggunakan kuota/biaya sesuai akun Google AI Studio.

# Aturan belajar bertahap
Jangan gunakan fitur Runtime → Run all. Kerjakan setiap tahap secara mandiri: baca instruksi, prediksi hasilnya, jalankan satu sel kode menggunakan tombol ▶ di kiri sel, amati hasil, lalu dokumentasikan screenshot di Word dengan caption penjelasan. Jangan beralih ke tahap berikutnya sebelum memahami output tahap ini. Jika muncul error, periksa dan perbaiki pada tahap tersebut.

# Bagaimana RAG bekerja?
Tanpa RAG: Kode Python → Gemini API → model Gemini (LLM) → response API → Python (belum tentu tahu dokumen internal).

## Dengan RAG: 
Dokumen → Potongan (chunks) → embedding melalui Gemini API → pencarian potongan relevan di Python → prompt berisi bukti dikirim melalui Gemini API → model Gemini (LLM) → jawaban dan sumber ditampilkan di Python.

## Dalam latihan ini seluruh data disimpan di memori Colab: 
tidak perlu mengunggah dokumen atau membuat vector database. Cosine similarity dipakai untuk mencari potongan yang paling dekat maknanya dengan pertanyaan.