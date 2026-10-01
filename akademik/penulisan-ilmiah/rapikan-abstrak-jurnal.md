---
judul: "Rapikan dan Sempurnakan Abstrak Jurnal Ilmiah"
kategori: akademik
tags: [abstrak, jurnal, penulisan-ilmiah, editing, akademik]
model: GPT-4, Claude 3.5 Sonnet, Gemini 1.5 Pro
versi: 1.0
tanggal_update: 2026-10-01
---

# Rapikan dan Sempurnakan Abstrak Jurnal Ilmiah

## 🎯 Tujuan

Merapikan dan menyempurnakan abstrak jurnal ilmiah agar memenuhi standar akademik: padat, jelas, informatif, dan mengikuti struktur IMRAD (Introduction, Method, Results, Discussion) secara implisit.

---

## 📌 Kapan Dipakai

- Saat abstrak terasa bertele-tele atau tidak fokus
- Saat jumlah kata melebihi batas (biasanya 150-250 kata)
- Saat abstrak tidak menyebutkan temuan utama secara jelas
- Saat hendak submit ke jurnal dan perlu polish terakhir

---

## 🔧 Variabel yang Harus Diisi

| Variabel | Deskripsi | Contoh Isian |
|----------|-----------|--------------|
| `{{abstrak_asli}}` | Teks abstrak yang ingin diperbaiki | (paste abstrak di sini) |
| `{{batas_kata}}` | Batas maksimal kata yang diperbolehkan | "250 kata" |
| `{{bidang_ilmu}}` | Bidang ilmu / disiplin jurnal | "teknik informatika", "pendidikan" |
| `{{bahasa_target}}` | Bahasa output yang diinginkan | "Indonesia formal" / "English academic" |

---

## 💬 Prompt

```
Kamu adalah editor jurnal ilmiah berpengalaman di bidang {{bidang_ilmu}}.

Berikut adalah abstrak yang perlu kamu perbaiki:

---
{{abstrak_asli}}
---

Tugasmu:
1. Pastikan abstrak mencakup empat elemen implisit: latar belakang singkat, tujuan penelitian, metode utama, dan temuan/kesimpulan.
2. Buang kalimat basa-basi dan informasi yang tidak esensial.
3. Batas maksimal: {{batas_kata}}.
4. Gunakan gaya bahasa {{bahasa_target}}: kalimat aktif, terukur, dan tanpa jargon berlebihan.
5. Pertahankan makna dan data asli — jangan tambahkan klaim yang tidak ada di teks asli.

Berikan:
- Versi abstrak yang sudah diperbaiki
- Jumlah kata versi baru
- Catatan singkat (bullet) apa saja yang kamu ubah dan alasannya
```

---

## 📖 Contoh Penggunaan

### Input (Variabel yang Diisi)

| Variabel | Nilai |
|----------|-------|
| `{{bidang_ilmu}}` | "kecerdasan buatan" |
| `{{batas_kata}}` | "200 kata" |
| `{{bahasa_target}}` | "Indonesia formal" |
| `{{abstrak_asli}}` | (abstrak draft mahasiswa S2) |

### Prompt Setelah Diisi

```
Kamu adalah editor jurnal ilmiah berpengalaman di bidang kecerdasan buatan.

Berikut adalah abstrak yang perlu kamu perbaiki:

---
Penelitian ini membahas tentang penggunaan machine learning untuk mendeteksi
penyakit tanaman. Dalam penelitian ini kami menggunakan banyak data dan
algoritma. Hasilnya cukup bagus dan bisa dipakai di lapangan...
---

Tugasmu:
1. Pastikan abstrak mencakup empat elemen implisit...
[dst.]
```

### Contoh Output yang Diharapkan

> **Abstrak (187 kata):**
> Deteksi dini penyakit tanaman merupakan faktor kritis dalam ketahanan pangan. Penelitian ini mengembangkan sistem deteksi penyakit daun padi berbasis Convolutional Neural Network (CNN) dengan dataset 4.200 citra dari tiga varietas utama. Model dilatih menggunakan arsitektur ResNet-50 dengan transfer learning dan augmentasi data...
>
> **Perubahan:**
> - Menghapus frasa "cukup bagus" → diganti dengan akurasi spesifik
> - Menambahkan ukuran dataset yang tersirat di naskah
> - Mengubah kalimat pasif menjadi aktif

---

## 💡 Catatan dan Tips

- Berikan abstrak asli tanpa edit — biarkan AI melihat masalah aslinya
- Jika jurnal punya template struktur khusus (mis. IMRAD ketat), sebutkan di prompt
- Untuk abstrak berbahasa Inggris, tambahkan instruksi "avoid passive voice"
- Cek ulang angka dan data setelah AI selesai — AI tidak boleh mengarang data
