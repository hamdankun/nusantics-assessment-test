# Nusantics — Technical Test Engineering Lead

## Jawaban

1. **[Code Review](test-1-code-review/review.md)**
   Kode sekarang belum aman dijalankan di banyak server. Solusinya: buat prosesnya atomik di database dengan row lock, baru setelah itu tambah server secara bertahap.

2. **[Infrastructure Decision](test-2-infrastructure/plan.md)**
   Notifikasi status sampel memakai Server-Sent Events dan PostgreSQL `LISTEN/NOTIFY`. Sederhana, satu arah, dan tidak butuh infrastruktur baru.

3. **[One Shot Situation](test-3-one-shot/decision-lead.md)**
   Masalahnya ada di nama token yang kurang bagus. Perbaiki dulu tampilannya, analisa dampaknya, lalu cegah supaya tidak terulang lewat ESLint di pipeline dan dokumentasi token.

Nomor baris di Tes 1 merujuk ke file `culturePoolAssignment.js` dari Nusantics. File itu sengaja tidak disertakan di repo karena bersifat privat.

## Prinsip

Saya memakai KISS, YAGNI, DRY, SOLID, dan Clean Architecture, secukupnya. Pilih solusi paling sederhana yang sudah cukup, pakai teknologi yang sudah ada, dan tulis kapan solusi itu perlu ditingkatkan.

## Cara saya memakai AI

Saya mengerjakan tes ini bersama **Claude Code** sebagai rekan kerja.

- **AI** membantu membaca kode, menyusun draft, dan me-review ulang jawaban terhadap brief. Untuk Tes 1, AI juga membuat prototype kecil yang dites ke PostgreSQL sungguhan. Dari situ ketahuan bahwa sampel juga perlu dikunci, bukan hanya rak dan jatahnya.
- **Saya** menentukan arah, mengambil keputusan, mempertanyakan hasil AI (misalnya membandingkan SSE dengan WebSocket), dan memangkas jawaban supaya singkat dan langsung ke inti.

Semua keputusan di sini sudah saya pahami dan bisa saya jelaskan.
